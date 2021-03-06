---
layout: page
title: "Q272656: How to Create a File Viewer By Using ASP"
permalink: /kb/272/Q272656/
---

## Q272656: How to Create a File Viewer By Using ASP

{% raw %}

	Article: Q272656
	Product(s): Internet Information Server
	Version(s): 4.0,5.0
	Operating System(s): 
	Keyword(s): kbIIS
	Last Modified: 13-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Internet Information Server version 4.0 
	- Microsoft Internet Information Services version 5.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article describes how to use Microsoft Active Server Pages (ASP)
	technologies to create a generic file viewer by using the
	Scripting.FileSystemObject.
	
	Important Note:
	
	If you use the code in this article improperly, the code can be used to view
	folders outside of a Web site. For additional information on preventing this,
	click the article numbers below to view the articles in the Microsoft Knowledge
	Base:
	
	  Q184717 AspEnableParentPaths MetaBase Property Should Be Set To False
	
	  Q276548 ASP Error 0131 When Browsing to Database Results Region ASP Page
	
	MORE INFORMATION
	================
	
	General Disclaimer:
	
	Microsoft provides programming examples for illustration only, without warranty
	either expressed or implied, including, but not limited to, the implied
	warranties of merchantability and/or fitness for a particular purpose. This
	article assumes that you are familiar with the programming language being
	demonstrated and the tools used to create and debug procedures. Microsoft
	support professionals can help explain the functionality of a particular
	procedure, but they will not modify these examples to provide added
	functionality or construct procedures to meet your specific needs. If you have
	limited programming experience, you may want to contact a Microsoft Certified
	Partner or the Microsoft fee-based consulting line at (800) 936-5200. For more
	information about Microsoft Certified Partners, please visit the following
	Microsoft Web site:
	
	  http://www.microsoft.com/partner/referral/
	
	For more information about the support options that are available and about how
	to contact Microsoft, visit the following Microsoft Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	Page Viewer Example Code:
	
	Use the following steps to create the page viewer ASP page.
	
	NOTE: You must have Basic/Clear Text, Integrated/NTLM, or Digest authentication
	enabled to use this example.
	
	1. Open Notepad on a Web server that is running Microsoft Internet Information
	  Server version 4.0 or Internet Information Services version 5.0.
	
	2. Run the following ASP code:
	
	  <% @Language="VBScript" %>
	  <%  
	    On Error Resume Next ' don't worry about errors
	
	    ' turn on buffering
	    Response.Buffer = True
	
	    ' make sure that client is authenticated
	    If Len(Trim(CStr(Request.ServerVariables("LOGON_USER")))) = 0 Then
	      Response.Status = "401 Access Denied"
	      Response.End
	    End If
	  %>
	  <html>
	  <head>
	  <title>File Viewer</title>
	  </head>
	  <body>
	
	  <h2>File Viewer</h2>
	
	  <!-- show a form to allow users to specify a file -->
	  <form action="<%=Request.ServerVariables("URL")%>" method="POST">
	  <input type="text" name="FILE" value="<%=Request.Form("FILE")%>">
	  <input type="submit" value="View File">
	  </form>
	
	  <pre>
	  <%
	    ' was it a POST request?
	    If UCase(Request.ServerVariables("HTTP_METHOD")) = "POST" Then
	
	      ' create object for file I/O
	      Set objFSO = Server.CreateObject("Scripting.FileSystemObject")
	      ' open the specified file
	      Set objFILE = objFSO.OpenTextFile(Request.Form("FILE"))
	      
	      ' output message if an error has occured
	      If Err.Number <> 0 Then
	
	        Response.Write "Error trying open the file """ & _
	            Request.Form("FILE") & """" & vbCrLf & _
	            "Error Number = " & Err.Number & vbCrLf & _
	            "Error Description = " & Err.Description & vbCrLf
	
	      ' otherwise show the file
	      Else
	
	        ' show the page start
	        Response.Write "----- START OF PAGE -----" & vbCrLf
	      
	        ' loop through the page contents
	        While Not objFILE.AtEndOfStream
	          Response.Write Server.HTMLEncode(objFILE.ReadLine) & vbCrLf
	        Wend
	
	        ' show the page end
	        Response.Write "----- END OF PAGE -----" & vbCrLf
	
	        ' close the specified file
	        objFILE.Close
	        ' discard the file I/O object
	        Set objFSO = Nothing
	
	      End If
	
	    End If
	  %>
	  </pre>
	  </body>
	  </html>
	
	3. Save the page as "Viewer.asp"in the root folder of your Web site.
	
	4. Browse to the page through HTTP, and then enter the path of the directory
	  that you want to view. The folder's contents should display.
	
	REFERENCES
	----------
	
	For additional information on this topic, click the article numbers below to view
	the articles in the Microsoft Knowledge Base:
	
	  Q218606 HOWTO: ASP and Scripting FileSystemObject to Create Dynamic TOC
	
	  Q224364 Creating a Directory Browsing Page Using ASP
	
	  Q201133 Scripting Change Occurs When Upgrading from IIS 3.0
	
	Additional query words: iis
	
	======================================================================
	Keywords          : kbIIS 
	Technology        : kbiisSearch kbiis500 kbiis400
	Version           : :4.0,5.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
