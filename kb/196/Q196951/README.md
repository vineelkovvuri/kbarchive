---
layout: page
title: "Q196951: WD97: Using Headers and Footers with Master Documents"
permalink: /kb/196/Q196951/
---

## Q196951: WD97: Using Headers and Footers with Master Documents

{% raw %}

	Article: Q196951
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbdta word97
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	
	SUMMARY
	=======
	
	By using the master document feature in Word, you can have many subdocuments
	contained within a master document. This article has some examples that show the
	possible combinations of headers and footers in master documents and
	subdocuments and how they interact with each other.
	
	MORE INFORMATION
	================
	
	Document Design Example 1
	-------------------------
	
	Master Document:
	
	- Different First Page: selected
	- First Header: "master first header"
	- First Footer: "master first footer"
	- Header: "master header"
	- Footer: "master footer"
	
	Subdocument 1:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: blank
	- Footer: blank
	
	Subdocument 2:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: blank
	- Footer: blank
	
	Result:
	
	  |----------|   |----------|
	  | master   |   | master   |
	  | first    |   | header   |
	  | header   |   |          |
	  |          |   |          |
	  | master   |   |          |
	  | first    |   | master   |                        Master Document
	  | footer   |   | footer   |
	  |----------|   |----------|
	     page 1         page 2
	
	  |----------|   |----------|   |----------|
	  | master   |   | master   |   | master   |
	  | first    |   | header   |   | header   |
	  | header   |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 1
	  | master   |   |          |   |          |
	  | first    |   | master   |   | master   |
	  | footer   |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	
	     page 3        page 4          page 5
	
	  |----------|   |----------|   |----------|
	  | master   |   | master   |   | master   |
	  | first    |   | header   |   | header   |
	  | header   |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 2
	  | master   |   |          |   |          |
	  | first    |   | master   |   | master   |
	  | footer   |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	     page 6        page 7          page 8
	
	Explanation:
	
	If the subdocuments do not have headers, footers, first headers, or first
	footers, the corresponding elements of the master document will appear. For
	example, the first header of the subdocument is the same as the first header of
	the master document.
	
	The header of the subdocument is the same as the header of the master document.
	The first footer of the subdocument is the same as the first footer of the
	master document, and the footer of the subdocument is the same as the footer of
	the master document.
	
	Document Design Example 2
	-------------------------
	
	Master Document:
	
	- Different First Page: selected
	- First Header: "master first header"
	- First Footer: "master first footer"
	- Header: "master header"
	- Footer: "master footer"
	
	Subdocument 1:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 1 header"
	- Footer: blank
	
	Subdocument 2:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 2 header"
	- Footer: blank
	
	Result:
	
	  |----------|   |----------|
	  | master   |   | master   |
	  | first    |   | header   |
	  | header   |   |          |
	  |          |   |          |
	  | master   |   |          |
	  | first    |   | master   |                        Master Document
	  | footer   |   | footer   |
	  |----------|   |----------|
	
	     page 1         page 2
	
	  |----------|   |----------|   |----------|
	  | master   |   | SubDoc 1 |   | SubDoc 1 |
	  | first    |   | header   |   | header   |
	  | header   |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 1
	  | master   |   |          |   |          |
	  | first    |   | master   |   | master   |
	  | footer   |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	
	     page 3        page 4          page 5
	
	  |----------|   |----------|   |----------|
	  | master   |   | SubDoc 2 |   | SubDoc 2 |
	  | first    |   | header   |   | header   |
	  | header   |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 2
	  | master   |   |          |   |          |
	  | first    |   | master   |   | master   |
	  | footer   |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	
	     page 6        page 7          page 8
	
	Explanation:
	
	The same basic rules apply as in example 1, except that if the subdocument has
	any headers or footers, those headers or footers specific to that subdocument
	take precedence over the master document headers and footers. Any headers or
	footers that remain blank in the subdocument take on the attributes of the
	corresponding master document header, footer, first header, or first footer.
	
	Document Design Example 3
	-------------------------
	
	Master Document:
	
	- Different First Page: selected
	- First Header: "master first header"
	- First Footer: "master first footer"
	- Header: none
	- Footer: none
	
	Subdocument 1:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 1 header"
	- Footer: blank
	
	Subdocument 2:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 2 header"
	- Footer: blank
	
	Result:
	
	  |----------|
	  | master   |
	  | first    |
	  | header   |
	  |          |
	  | master   |
	  | first    |                                       Master Document
	  | footer   |
	  |----------|
	
	     page 1
	
	  |----------|   |----------|   |----------|
	  | master   |   | SubDoc 1 |   | SubDoc 1 |
	  | first    |   | header   |   | header   |
	  | header   |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 1
	  | master   |   |          |   |          |
	  | first    |   |          |   |          |
	  | footer   |   |          |   |          |
	  |----------|   |----------|   |----------|
	
	     page 2        page 3          page 4
	
	  |----------|   |----------|   |----------|
	  | master   |   | SubDoc 2 |   | SubDoc 2 |
	  | first    |   | header   |   | header   |
	  | header   |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 2
	  | master   |   |          |   |          |
	  | first    |   |          |   |          |
	  | footer   |   |          |   |          |
	  |----------|   |----------|   |----------|
	
	     page 5        page 6          page 7
	
	Explanation:
	
	In the subdocuments, the first headers are the same as the master document's
	first header since the subdocuments do not have a first header. The same is true
	of the subdocument's first footer.
	
	Each of the subdocuments has a header, so the individual subdocument header takes
	precedence and becomes the header for subdocument it appears in. The
	subdocuments do not have footers, so the master document's footer should appear,
	but it doesn't exist (and is therefore blank).
	
	Document Design Example 4
	-------------------------
	
	Master Document:
	
	- Different First Page: not selected
	- First Header: doesn't exist
	- First Footer: doesn't exist
	- Header: "master header"
	- Footer: "master footer"
	
	Subdocument 1:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 1 header"
	- Footer: blank
	
	Subdocument 2:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 2 header"
	- Footer: blank
	
	Result:
	
	                 |----------|
	                 | master   |
	                 | header   |
	                 |          |
	                 |          |
	                 |          |
	                 | master   |                        Master Document
	                 | footer   |
	                 |----------|
	                    page 1
	
	  |----------|   |----------|   |----------|
	  |          |   | SubDoc 1 |   | SubDoc 1 |
	  |          |   | header   |   | header   |
	  |          |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 1
	  |          |   |          |   |          |
	  |          |   | master   |   | master   |
	  |          |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	
	     page 2        page 3          page 4
	
	  |----------|   |----------|   |----------|
	  |          |   | SubDoc 2 |   | SubDoc 2 |
	  |          |   | header   |   | header   |
	  |          |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 2
	  |          |   |          |   |          |
	  |          |   | master   |   | master   |
	  |          |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	
	     page 5        page 6          page 7
	
	Explanation:
	
	The subdocuments do not have a first header, so the first header of the master
	document should appear, but the first header doesn't exist (and is therefore
	blank). The same is true of the subdocument's first footers.
	
	Since the subdocuments have individual headers, the headers take precedence and
	become the headers for the subdocuments they appear in. Since the subdocuments
	do not have footers, the footer of the master document appears in the
	subdocuments.
	
	Document Design Example 5
	-------------------------
	
	Suppose you have the document configuration shown in example 4. You might assume
	that the master document acts like a "container" document, and any blank footers
	in the subdocuments will get the master document's footer whether the footers in
	the subdocument are footers or first footers. This will not happen. You will get
	the results shown in example 4.
	
	If you have a one-page master document, and you have subdocuments with Different
	First Pages, and you want all of the pages to have the master document's footer,
	follow these steps:
	
	1. Create a two-page master document.
	
	2. In the master document, select Different First Page.
	
	3. Enter the desired headers in the first header and the header of the master
	  document.
	
	4. Enter the desired footers in the first footer and the footer of the master
	  document.
	
	5. Delete the page break in the master document, making it one page. The master
	  document will show the first header and first footer information, but the
	  header and footer information will still remain, even though it is not shown.
	
	This is the document configuration:
	
	Master Document:
	
	- Different First Page: selected
	- First Header: "master header"
	- First Footer: "master footer"
	- Header: "master header" (although there is no second page)
	- Footer: "master footer" (although there is no second page)
	
	Subdocument 1:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 1 header"
	- Footer: blank
	
	Subdocument 2:
	
	- Different First Page: selected
	- First Header: blank
	- First Footer: blank
	- Header: "SubDoc 2 header"
	- Footer: blank
	
	Result:
	
	  |----------|
	  | master   |
	  | header   |
	  |          |
	  |          |
	  |          |
	  | master   |                                       Master Document
	  | footer   |
	  |----------|
	
	     page 1
	
	  |----------|   |----------|   |----------|
	  | master   |   | SubDoc 1 |   | SubDoc 1 |
	  | header   |   | header   |   | header   |
	  |          |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 1
	  |          |   |          |   |          |
	  | master   |   | master   |   | master   |
	  | footer   |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	
	     page 3        page 4          page 5
	
	  |----------|   |----------|   |----------|
	  | master   |   | SubDoc 2 |   | SubDoc 2 |
	  | header   |   | header   |   | header   |
	  |          |   |          |   |          |
	  |          |   |          |   |          |         Subdocument 2
	  |          |   |          |   |          |
	  | master   |   | master   |   | master   |
	  | footer   |   | footer   |   | footer   |
	  |----------|   |----------|   |----------|
	
	     page 6        page 7          page 8
	
	Explanation:
	
	Because there is no first header for the subdocument, the first header of the
	master document appears in the subdocument. The first header of the master
	document is not shown, but it still exists, so it becomes whatever the first
	header of the master document was. The same is true of the first footer of the
	master document.
	
	Because the subdocument has a header, it takes precedence over the master
	document header. Because the subdocument has no footer, the master document's
	footer appears in the subdocument. The effect of the master document's footer
	appearing throughout the document occurs because the master document's first
	footer and footer contain the same text.
	
	Additional query words: insert
	
	======================================================================
	Keywords          : kbdta word97 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
