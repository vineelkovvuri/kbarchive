---
layout: page
title: "Q259062: Contents Are Lost Saving Management Agent Scripts or Templates"
permalink: /kb/259/Q259062/
---

## Q259062: Contents Are Lost Saving Management Agent Scripts or Templates

{% raw %}

	Article: Q259062
	Product(s): Microsoft Windows NT
	Version(s): 2.1
	Operating System(s): 
	Keyword(s): kbenv kbtool
	Last Modified: 20-MAY-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Metadirectory Services 2.1 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you are saving management agent (MA) templates or scripts, or the advanced
	attribute flow, the contents of the templates are lost when you click OK. When
	you later view the templates, they are blank.
	
	CAUSE
	=====
	
	All the MA templates and scripts are stored as directory attributes. By default,
	these attributes have a storage type of Normal. The current size limit for
	normal storage is 20 KB; if you exceed the 20-KB attribute limit, the contents
	of the attribute are lost.
	
	RESOLUTION
	==========
	
	To work around this behavior, change the storage type from Normal to Large
	Object:
	
	1. Determine the name of the attribute by pressing and holding down the CTRL key
	  while you right-click the item.
	
	2. Using Compass, search for the attribute in the directory.
	
	3. Double-click the attribute to view its properties.
	
	4. Click the Storage tab.
	
	5. Click Large Object, and then click OK.
	
	The storage type defines how the attribute's value is stored in the directory
	database. There are several attribute storage types:
	
	- Normal: A field up to 20 KB is stored "as is."
	
	- Large Object: Attribute values larger than 20 KB in size (file-based
	  attributes) that are stored in the directory database.
	
	- Transient File: Attribute values contained in external files (log files, for
	  example) that are therefore "transient." You must use this with a file
	  control attribute.
	
	- File Control: An attribute value containing the path to a transient file. If
	  you use this storage type, you must also specify the associated transient
	  file attribute.
	
	- Translation: ASN.1 translation.
	
	- Variable Size: An attribute value that can be under or over 20 KB in size;
	  its storage method changes, depending on its size.
	
	- Virtual: An attribute with no stored value; its value is created dynamically
	  by a plug-in when the attribute is accessed.
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in the Microsoft products that
	are listed at the beginning of this article.
	
	
	Additional query words: Zoomit Via MA zscript genlogs attributes
	
	======================================================================
	Keywords          : kbenv kbtool 
	Technology        : kbMMSSearch kbMMS210
	Version           : :2.1
	Issue type        : kbbug
	Solution Type     : kbpending
	
	=============================================================================
	

{% endraw %}
