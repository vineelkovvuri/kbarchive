---
layout: page
title: "Q267548: Cluster IP Resource Fails After Network Change"
permalink: /kb/267/Q267548/
---

## Q267548: Cluster IP Resource Fails After Network Change

{% raw %}

	Article: Q267548
	Product(s): Microsoft Windows NT
	Version(s): 2000,4.0
	Operating System(s): 
	Keyword(s): kberrmsg kbtool
	Last Modified: 25-APR-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server, Enterprise Edition version 4.0 
	- Microsoft Windows 2000 Advanced Server 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When you attempt to start Cluster Administrator, you may receive the following
	error message:
	
	  An error occurred trying to open the cluster at <Clustername>.
	
	  The RPC Server is unavailable
	
	  Error ID: 1722 (000006ba)
	
	Also, the following errors may appear in the cluster node System Event Log:
	
	  Event ID: 1069
	  Source: ClusSvc
	  Description: Cluster resource 'Cluster IP Address' failed.
	
	  Event ID: 1048
	  Source: ClusSvc
	  Description: Cluster IP Address resource <resource name> cannot be
	  brought online because the adapter name parameter is invalid. Please check
	  your network configuration.
	
	CAUSE
	=====
	
	This issue can occur if you have replaced your network adapter, or have changed
	the IP address of your public network adapter.
	
	RESOLUTION
	==========
	
	To resolve this issue:
	
	NOTE: The following steps must be performed from one of the cluster nodes. These
	steps will not work from a computer that is not a member of the cluster.
	
	1. Click Start, and then click Run.
	
	2. In the Open box, type "cluadmin /noreconnect" (without the quotation marks),
	  and then press ENTER.
	
	3. When you receive the prompt for the cluster name, enter a period "." (without
	  the quotes), and then click Open.
	
	4. Under the Groups item, click Cluster Group.
	
	5. In the right-side pane, double-click Cluster IP Address.
	
	6. Click the Parameters tab.
	
	7. In the Network box, choose the name of your Public network adapter, for
	  example, "Public(1)", and then click OK.
	
	8. Repeat steps 5-7 for any other virtual IP Address resources that are not
	  working in all of the groups on your cluster.
	
	9. Right-click the Cluster Group, and then click Bring Online. Repeat this step
	  for all groups.
	
	Another solution to this issue is:
	
	1. Click Start, and then click Run.
	
	2. In the Open box, type "cluadmin" (without the quotation marks), and then
	  press ENTER.
	
	3. When you are prompted to start the Cluster Service, click No.
	
	4. Click File|Open.
	
	5. Enter a period "." (without the quotation marks) in the Network textbox.
	
	6. Under the Groups item, click Cluster Group.
	
	7. In the right-side pane, double-click Cluster IP Address.
	
	8. Click the Parameters tab.
	
	9. In the Network box, choose the name of your Public network adapter, for
	  example, "Public(1)", and then click OK.
	
	10. Repeat steps 7-9 for any other virtual IP Address resources that are not
	  working, and then continue to the next step.
	
	11. Right-click the Cluster Group, and then click Bring Online. Repeat this step
	  for all groups.
	
	MORE INFORMATION
	================
	
	When the IP address for the public network adapter is changed, or the network
	card is replaced, the network adapter is detected as a new network. When this
	change occurs, IP Address resources in Cluster Administrator are not
	automatically associated with the new network adapter.
	
	REFERENCES
	==========
	
	For additional information about how to change the IP address of network
	adapters in Cluster Server, click the article number below to view the article
	in the Microsoft Knowledge Base:
	
	  Q230356 Changing the IP Address of Network Adapters in Cluster Server
	
	Additional query words: MSCS W2000MSCS NIC
	
	======================================================================
	Keywords          : kberrmsg kbtool 
	Technology        : kbWinNTsearch kbWinNT400search kbwin2000AdvServ kbwin2000AdvServSearch kbWinNTSsearch kbWinNTSEntSearch kbWinNTSEnt400 kbWinNTS400search kbwin2000Search kbWinAdvServSearch
	Version           : :2000,4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
