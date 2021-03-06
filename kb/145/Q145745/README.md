---
layout: page
title: "Q145745: INFO: Function Differences Between Asc/AscB/AscW and Chr/ChrB/Ch"
permalink: /kb/145/Q145745/
---

## Q145745: INFO: Function Differences Between Asc/AscB/AscW and Chr/ChrB/Ch

{% raw %}

	Article: Q145745
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:4.0,5.0,6.0
	Operating System(s): 
	Keyword(s): KbVBA kbVBp kbVBp400 kbVBp500 kbVBp600 kbGrpDSVB kbDSupport
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, versions 5.0, 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, versions 5.0, 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, versions 5.0, 6.0 
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	For years, BASIC programmers have been using the Asc and Chr functions to access
	and manipulate the ASCII character set. With the advent of Unicode acceptance in
	mainstream operating systems and applications, the need for improved versions of
	the Asc and Chr functions has developed. To meet this demand, Microsoft Visual
	Basic (4.0 and higher) for Windows includes the AscB/ChrB and AscW/ChrW
	functions.
	
	MORE INFORMATION
	================
	
	Unicode is a standard that is designed to replace the ANSI standard for encoding
	characters in a numeric form. Because the ANSI standard only uses a single byte
	to represent each character, it is limited to a maximum of 256 different
	characters. While this is sufficient for the needs of an English speaking
	audience, it falls short when the worldwide software market is considered. With
	the Unicode standard, each character is represented by two bytes, so that the
	entire Unicode character set includes 65,536 possible locations.
	
	Microsoft Windows NT, Microsoft Windows 2000, and Microsoft OLE 2.0 are entirely
	Unicode based, and Visual Basic (4.0 and higher) represents all strings
	internally in Unicode format. The AscW and ChrW functions allow access to the
	full range of Unicode characters. These functions work in the same way as the
	original Asc and Chr functions except that they support arguments from 0 to
	65,535 instead of just from 0 to 255. Many Visual Basic objects (such as the
	debug window and the label and text box) return a "?" when these objects do not
	know how to display an Unicode character.
	
	Because all strings are now represented internally in Unicode format, it is not
	as simple as it used to be to represent binary data in a string. Using the Chr
	function to assign data to a string does not result in the same behavior as
	before. For example:
	
	     stringvar = Chr(65)
	
	results in a two-byte long string, where byte 1 has a value of 65 and byte 2 has
	a value of 0 (this is the Unicode representation of the letter "A"). Be sure to
	keep in mind that converting from ANSI to Unicode does not always entail just
	adding a second byte with a value of zero as it does in this case. For example,
	most of the ANSI character codes in the range 130-159 have completely different
	Unicode values. Try executing a 'Debug.Print AscW(Chr(130))' and you a value of
	8218 is displayed.
	
	Currently, Microsoft Windows requires a little endian processor, which means that
	in a multiple byte entity the first byte is the least significant, and
	significance increases in successive bytes. This explains why the Unicode
	character "A" is represented internally as the following:
	
	  -------------------
	  |   65   |    0   |
	  -------------------
	    byte 0     byte 1
	
	The AscB and ChrB functions can be used to replicate what used to be accomplished
	by the Asc and Chr functions, because these functions allow the manipulation of
	single byte quantities. If you would like a four-byte string that has the binary
	values of 65, 66, 67, and 68 consecutively then using the Chr function will not
	work. You must instead use the ChrB function. For example:
	
	     stringvar = ChrB(65) & ChrB(66) & ChrB(67) & ChrB(68)
	
	Alternatively, you can use the ability to create arrays of the new byte data type
	and manipulate your binary data that way.
	
	Listed below is an explanation of the results of some simple uses of these
	functions to further clarify this information.
	
	Print Asc(Chr(255)) --> "255"
	
	Nothing new here, except that the Chr function is returning a Unicode character
	that occupies two bytes instead of a one-byte ANSI character.
	
	Print Asc(ChrB(255)) --> 5 - Invalid procedure call.
	
	This usage returns an error because the Asc function always expects at least a
	two-byte parameter and the ChrB function is only returning a single byte.
	
	Print Asc(Chr(256)) --> 5 - Invalid procedure call.
	
	Although the Chr function returns a two-byte Unicode character, it still only
	takes numbers between 0 and 255 for its argument (note that on a DBCS enabled
	system, Asc/Chr handle two-byte DBCS characters, converting them to and from
	Unicode). Using the ChrW function allows access to the full 65,536 Unicode
	character locations.
	
	Print AscW(ChrW(256)) --> "256"
	
	This is the new version of the first statement in this section. The ChrW function
	takes a value from 0 to 65,536 and returns that character (on 32-bit systems).
	The AscW function interprets this two-byte character as a Unicode character and
	returns the correct Unicode value for that character.
	
	Print Asc(ChrW(256)) --> "65"
	Print Asc(ChrW(5000)) --> "63"
	
	What is happening here is that the ChrW function is being evaluated first.
	ChrW(256) is the character "A", and so the function reduces to Asc("A"), and the
	Unicode (and ANSI) number for "A" is 65. Because Visual Basic does not know how
	to display the character represented by Chr(5000) it just displays a "?", and as
	expected, the Unicode and ANSI value for "?" is 63.
	
	Print AscB(Chr(65)) --> "65"
	Print AscB(ChrW(256)) --> "0"
	Print AscB(ChrW(257)) --> "1"
	Print AscB(ChrW(555)) --> "43"
	Print AscB(ChrW(65535)) --> "255"
	
	All of these return values can be explained by understanding how each character
	is represented internally (see the little-endian reference above) and by the
	fact that the AscB function looks only at the first byte of the character it
	receives. Visually it looks like the following diagram:
	
	            -------------------
	  Chr(65)   |   65   |    0   |
	            -------------------
	  Chr(256)  |    0   |    1   |
	           -------------------
	  Chr(257)  |    1   |    1   |
	            -------------------
	  Chr(555)  |   43   |    1   |
	            -------------------
	  Chr(65535)|   255  |  255   |
	            -------------------
	              byte 0    byte 1
	
	The AscB function just returns whatever the first byte of the character is.
	
	Print ChrB(65) --> ""
	
	Visual Basic prints nothing for this call to the ChrB function because the ChrB
	function is only returning a one-byte string. One byte strings like this mean
	nothing to Visual Basic because they do not constitute a valid Unicode character
	(or series of characters).
	
	Print ChrB(65) & ChrB(0) --> "A"
	
	In this case, we are concatenating two one-byte strings into a single two-byte
	string. Because the resulting bit pattern is the same as the bit pattern for the
	Unicode "A", that is what Visual Basic prints.
	
	Additional query words:
	
	======================================================================
	Keywords          : KbVBA kbVBp kbVBp400 kbVBp500 kbVBp600 kbGrpDSVB kbDSupport 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVBA500 kbVBA600 kbVB500 kbVB600 kbVB400Search kbVB400 kbVB16bitSearch
	Version           : WINDOWS:4.0,5.0,6.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
