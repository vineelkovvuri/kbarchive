---
layout: page
title: "Q216555: How to Allow Web Access to Large User Groups"
permalink: /kb/216/Q216555/
---

## Q216555: How to Allow Web Access to Large User Groups

{% raw %}

	Article: Q216555
	Product(s): Internet Information Server
	Version(s): winnt:4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 20-FEB-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Internet Information Server 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	When you use Internet Information Server (IIS), you may need to grant access to
	a restricted Web site to a large group of users without having each user
	prompted for credentials. Normally, you would use NTFS permissions on files to
	grant access to each individual user; however, with large groups of users this
	is a time consuming task.
	
	MORE INFORMATION
	================
	
	The best way to accomplish this is to create a group that has access to the
	resource through NTFS permissions and remove the Everyone group from these
	permissions. Be sure to give Administrators and System the appropriate
	permissions as well.
	
	The typical permissions will look similar to the following:
	
	  Your Group (R)
	  Administrators (FULL)
	  System (FULL)
	
	Within this group, place the users that need access to the restricted resources
	on the Web site. You can do this by adding the group(s) in which they belong, or
	by adding the users one at a time to this group (this can be time consuming, but
	not as much as on a per-file basis).
	
	In order for the user to avoid being prompted, make sure that Windows NT
	Challenge/Response is selected. It is important to note that this type of
	authentication will not work through a Proxy Server. Internet Explorer version
	2.0 and later is the only browser that supports this method of authentication,
	which makes this part of the setup valid only in an intranet environment.
	
	This method should save you considerable administrative overhead. You may even
	find that the users needing the resources on the Web site are already in groups,
	which is typical). This also allows you to add additional users or groups that
	may need access to these resources in a less time consuming manner.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbiisSearch kbiis400
	Version           : winnt:4.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
