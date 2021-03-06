---
layout: page
title: "Q258855: Windows Services for UNIX Version 2.0 Readme.txt File"
permalink: /kb/258/Q258855/
---

## Q258855: Windows Services for UNIX Version 2.0 Readme.txt File

{% raw %}

	Article: Q258855
	Product(s): Microsoft Windows NT
	Version(s): 2.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 28-JUL-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows Services for UNIX, version 2.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article contains the text from the Readme.txt file that is included with
	Windows Services for UNIX version 2.0.
	
	MORE INFORMATION
	================
	
	**********************************************************************
		Microsoft(R) Windows(R) Services for UNIX Version 2
				  Release Notes
				  April 2000
	**********************************************************************
		(c) Microsoft Corporation, 2000. All rights reserved.
	
	Please read the following important information before you install 
	and use Microsoft Windows Services for UNIX.
	
	======================================================================
	HOW TO VIEW AND PRINT THIS DOCUMENT
	======================================================================
	
	To view the release notes file in Windows Notepad, maximize the
	Notepad window. On the Edit or Format menu (depending on which 
	version of Notepad you are using), click Word Wrap. 
	
	To print the release notes file, open it in Notepad or another word-
	processing program, and then, on the File menu, click Print.
	
	======================================================================
	FOR MORE TECHNICAL INFORMATION
	======================================================================
	For more information about Windows Services for UNIX, please refer 
	to the white papers and technical walkthroughs on 
	http://www.microsoft.com/windows/sfu. 
	
	======================================================================
	CONTENTS
	======================================================================
	
	1.   SPECIAL REQUIREMENTS AND ALERTS
	2.   INSTALLING AND UNINSTALLING WINDOWS SERVICES FOR UNIX
	3.   INSTALLING MKS DEMOWARE
	4.   SERVER FOR NFS
	5.   GATEWAY FOR NFS
	6.   CLIENT FOR NFS
	7.   SERVER FOR NIS
	8.   USER NAME MAPPING
	9.   PASSWORD SYNCHRONIZATION
	10.  TELNET
	11.  ADMINISTERING WINDOWS SERVICES FOR UNIX
	12.  USING UNIX UTILITIES
	
	======================================================================
	SPECIAL REQUIREMENTS AND ALERTS
	======================================================================
	
	* You can install Windows Services for UNIX on computers 
	 running Windows 2000 or Windows NT 4.0 with Service Pack 4. 
	 If you have an older version of Windows NT, you must upgrade your 
	 system before you install Windows Services for UNIX.
	
	* Be sure to install this software in a directory that does not 
	 include a space in its name. If you do install this software in
	 a directory that has a space in its name, some shortcuts will not 
	 work correctly. In addition, you might experience problems with 
	 Network File System (NFS), some UNIX utilities, and scripts. 
	
	* Windows Services for UNIX requires Microsoft Internet Explorer 4.01
	 or later. If you have an older version of Internet Explorer, you 
	 must upgrade before you install Windows Services for UNIX. 
	
	* If you already have a third-party Telnet server installed on your 
	 computer, you must remove it before installing the version of 
	 Telnet Server provided with Microsoft Windows Services for 
	 UNIX.
	
	* Upgrades from Intergraph DiskAccess and DiskShare 3.0 do not work 
	 with Windows Services for UNIX.
	
	* Windows Services for UNIX supports Solaris 2.6 and later, HP-UX 10.2 
	 and later, AIX 4.2 and later, Tru64 UNIX 5.0 and later, and Redhat 
	 Linux 5.1 and later. Windows Services for UNIX Telnet and 
	 NFS components should also work with other operating systems or 
	 products that use these protocols. 
	
	* Extended-character user names are not supported.
	
	* You may see blank lines in list boxes when you open Services for 
	 UNIX Administration. If this happens, close and reopen Services 
	 for UNIX Administration, and then maximize it.
	
	* Because of a known problem with the Microsoft Management Console 
	 running on Windows NT 4.0 Terminal Server, if you attempt to view 
	 Help in Windows Services for UNIX Administration, an error message
	 will appear, and the Help index and search tabs will not work.
	 To use these features, start Help from the Windows Services for 
	 UNIX program group. 
	
	* Double-Byte Character Set (DBCS) is not allowed for computer 
	 names, domain names, host names, and user names. DBCS is the 
	 character set used for languages such as Japanese, Korean, and
	 Chinese.
	
	* Windows Services for UNIX causes a conflict with the Windows
	 find command. When you install Windows Services for UNIX, the 
	 command path is modified to place the %SFUDIR%\common directory 
	 before other directories. As a result, the Windows Services for UNIX 
	 find command will be run instead of the Windows find command 
	 unless the path to the Windows find command is specified on 
	 the command line. For example, to ensure that the Windows find 
	 command is run, use the following syntax: 
	
	   %WINDIR%\SYSTEM32\FIND
	
	 As an alternative, you can rename the find.exe file in the 
	 %SFUDIR%\common directory. 
	
	======================================================================
	INSTALLING AND UNINSTALLING WINDOWS SERVICES FOR UNIX
	======================================================================
	
	You can install Windows Services for UNIX from Windows or from a 
	command line. Windows Services for UNIX includes the following 
	components:
	
	* Server for NFS
	* Client for NFS
	* Gateway for NFS
	* Server for PCNFS
	* User Name Mapping
	* Server for NFS Authentication
	* Server for NIS
	* Telnet Client
	* Telnet Server
	* Password Synchronization
	* ActiveState ActivePerl
	* UNIX Utilities
	
	----------------------------------------------------------------------
	Before You Install 
	----------------------------------------------------------------------
	
	* Before you install Server for NIS, make sure you are a member of the 
	 Schema Admins group. This will ensure that Windows Services for UNIX
	 Setup can modify the Active Directory schema with NIS-specific 
	 information. Otherwise, the schema upgrade will fail.
	
	 For a single-domain enterprise, the domain administrator is a member
	 of the Schema Admins group. For a domain tree, only the root-level
	 domain administrator will be the member of the Schema Admins group.
	
	* Do not install version 1 of Windows Services for UNIX after you
	 install version 2. If you do, the version 2 components will be 
	 overwritten. 
	
	----------------------------------------------------------------------
	Upgrading from Earlier Versions of Windows Services for UNIX
	----------------------------------------------------------------------
	
	If you already have Windows Services for UNIX version 1, use Setup
	to upgrade to Windows Services for UNIX version 2.
	
	Before you upgrade, note the following:
	
	* Do not install both version 1 and version 2 of Windows Services for 
	 UNIX on the same computer or mix components from the two different 
	 versions.
	
	* Version 2 requires encryption during password synchronizations. 
	 Thus, if you have been using rlogin to synchronize passwords in 
	 version 1, you will no longer be able to do so. Instead, you must
	 install the Single Sign-On daemon (SSOD) component on your 
	 UNIX computers. 
	
	* You might need to restart your computer after you finish installing 
	 components, depending on which components you install.
	
	* If you are running Server for NIS from a beta 1 copy of Windows 
	 Services for UNIX version 2, you must uninstall Windows Services
	 for UNIX and run dcpromo twice (to remove the domain controller
	 and then reinstall it) before you install Server for NIS.
	
	----------------------------------------------------------------------
	Installing from a Command Line
	----------------------------------------------------------------------
	
	The first time you install Windows Services for UNIX on a computer
	running Windows NT 4.0 (Service Pack 4 or Service Pack 5), you must 
	install it from Windows. You cannot install from a command line for 
	the first installation. 
	
	To install Windows Services for UNIX version 2 from a command line, 
	use the following syntax: 
	
	msiexec /i <full path to sfusetup.msi> ADDLOCAL="<component1> 
	[,<component2>...]" PIDKEY="<key>" SFUDIR="<location>" [/qb|/q]
	
	Where: 
	
	* The components to be installed are specified as a comma-separated  
	 list parameter to ADDLOCAL. (These component names are case 
	 sensitive and must be enclosed in quotation marks.)
	    Complete feature-set:
	       * NFSServer 
	       * NFSServerAuth 
	       * Pcnfsd
		* Mapsvc
	       * NFSClient
	       * NFSGateway
	       * NIS
	       * PasswdSync
		* Perl
	       * TelnetClient
	       * TelnetServer
	       * UnixUtilities
		* CronSvc
		* RshSvc
	* PIDKEY is the 25-character product identification code. Do not type
	 hyphens in the PIDKEY.
	* /qb specifies a basic user interface.
	* /q specifies a silent installation.
	* SFUDIR specifies the location where Windows Services for UNIX will 
	 be installed.
	* The parameter following /i lists the full path to sfusetup.msi.
	
	Notes: 
	*  On a computer that is not a domain controller, both NFSServer 
	  and NFSServerAuth must be installed. On a domain controller, 
	  there is no such restriction.
	*  NFSClient and NFSGateway cannot be installed on the same computer.
	*  NFSGateway can only be installed on a server.
	*  NIS can only be installed on a Windows 2000 domain controller.
	
	Example:
	
	msiexec /i d:\temp\SfuV2\Sfusetup.msi ADDLOCAL="TelnetClient,
	TelnetServer,NFSClient" PIDKEY="A9RE3RTWE9SR97WKPOI2UJ54J" 
	SFUDIR="C:\sfu" /qb                   
	
	The options are case sensitive. 
	
	----------------------------------------------------------------------
	Starting Installation from Windows Explorer Fails When Terminal Server
	Is Installed 
	----------------------------------------------------------------------
	
	On a computer running Windows 2000 and Terminal Server, if you begin 
	installation by clicking the Setup.exe icon in Windows Explorer, 
	installation fails and the following message appears: 
	
		Terminal Server Install Failure
	
	A terminal server must be in install mode before you can install a 
	program. Using Add/Remove Programs in Control Panel to install a 
	program automatically puts a terminal server in install mode.
	
	>>>To install Windows Services for UNIX in this situation:
	
	  1. In Control Panel, click Add/Remove Programs. 
	  2. Click Add New Programs.
	  3. Click CD or Floppy. 
	  4. Follow the instructions in the Install Program From Floppy 
	     Disk or CD-ROM wizard.
	
	----------------------------------------------------------------------
	Installing Windows Services for UNIX over Existing Rsh Service
	----------------------------------------------------------------------
	
	If you have installed rsh service from a Windows resource kit and 
	you install Windows Services for UNIX v2, Windows Services for UNIX 
	will overwrite the rsh service. If you then uninstall Windows 
	Services for UNIX, the rsh service will also be removed. The version
	of the rsh service that you installed from the resource kit will not
	be restored.
	
	----------------------------------------------------------------------
	Installing Windows Services for UNIX on Windows NT 4 Domain 
	Controllers
	----------------------------------------------------------------------
	
	If you are installing Server for NFS Authentication or Password 
	Synchronization from Windows Services for UNIX on a Windows NT 4 
	domain controller (either a primary domain controller or a backup 
	domain controller) or on a Windows 2000 domain controller, you should 
	also install Windows Services for UNIX on all other Windows NT 4 
	domain controllers. Not doing so will cause features such as Server
	for NFS Authentication and Password Synchronization to work 
	incorrectly.
	
	----------------------------------------------------------------------
	Restoring Telnet After Uninstalling Windows Services for UNIX
	----------------------------------------------------------------------
	
	When you uninstall Windows Services for UNIX from a computer that uses
	Windows 2000, setup attempts to restore the original Windows 2000 
	Telnet files. If it is unsuccessful, an error results. In that case, 
	restore the Telnet files from the Windows 2000 CD. 
	
	For example, here are the commands you would use to restore the 
	required files if C:\WINNT is the system folder and D is the 
	Source CD: 
	
	  C:\>copy D:\I386\telnet.exe C:\WINNT\SYSTEM32
	  C:\>expand -r D:\I386\tlntsvr.ex_ C:\WINNT\SYSTEM32
	  C:\>expand -r D:\I386\tlntsvrp.dl_ C:\WINNT\SYSTEM32
	  C:\>expand -r D:\I386\tlntsess.ex_ C:\WINNT\SYSTEM32
	
	======================================================================
	INSTALLING MKS DEMOWARE
	======================================================================
	
	To install Mortice Kern System (MKS) Demoware, click Start, point to 
	Programs, point to Windows Services for UNIX, point to Demoware, and 
	then click Install MKS Demoware from Services for UNIX CD. 
	
	You can also manually install the MKS Demoware from a command line
	using \3rdparty\mks\x86\setup.exe.
	
	To install MKS Demoware, you must be a member of the local 
	Administrators group. Otherwise, MKS Demoware might not install 
	correctly.
	
	Mortice Kern Systems has provided this trial product as a courtesy 
	to Windows Services for UNIX customers. Microsoft does not provide 
	support for the MKS Demoware product. 
	
	======================================================================
	SERVER FOR NFS
	======================================================================
	
	There are known problems in connecting to shares with double-byte 
	character set (DBCS) names on Server for NFS. A UNIX client might not
	be able to connect to a share with a DBCS name. 
	
	======================================================================
	GATEWAY FOR NFS
	======================================================================
	
	----------------------------------------------------------------------
	Gateway for NFS on Terminal Server
	----------------------------------------------------------------------
	
	There are known problems on Gateway for NFS on Terminal Server. There 
	may be problems in sharing or deleting drives on Terminal Server.
	
	To delete gateway shares remotely, use Telnet, and not Terminal 
	Services Client, to connect to the remote server.
	
	----------------------------------------------------------------------
	Restoring the Favorite LAN Icon
	----------------------------------------------------------------------
	
	If the Favorite LAN icon is missing from the NFS Network, create the 
	following registry entries:  
	
	HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Client for 
	NFS\NFS LANs\Favorite LAN 
	
	HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Client for 
	NFS\NFS LANs\Favorite LAN\Configure Mode
	
	Use 1 for the value(DWORD).
	
	======================================================================
	CLIENT FOR NFS
	======================================================================
	
	----------------------------------------------------------------------
	Mounting a Root Directory
	----------------------------------------------------------------------
	
	When a root directory ("/") on a UNIX computer is shared, Client for
	NFS will not be able to mount it using the regular syntax of 
	"net use * \\<server>\"  or "net use <server>:/".
	
	To mount the root directory, use: 
	
		net use * \\<server>\! 
	
	The share name must be an exclamation mark (!). 
	
	----------------------------------------------------------------------
	Using the PCNFS Daemon for Authentication
	----------------------------------------------------------------------
	
	With Client for NFS, you can use the PCNFS daemon (PCNFSD) to 
	authenticate Windows users to access NFS resources on other UNIX NFS
	servers. To use PCNFSD servers for authentication, you must use the 
	mount command. The net command does not support PCNFSD authentication.
	The syntax of the mount command is augmented to include another
	option. 
	
	mount [-o <options>] [-u:<username>] [-p:{<password> | *}]
	[\\<computername>\<sharename> {<devicename> | *}]
	
	-o rsize  =       [READ BUFFER SIZE (in KB)] Sets the size of the 
	                 read buffer.
	-o wsize  =       [WRITE BUFFER SIZE (in KB)] Sets the size of the 
	                 write buffer.
	-o timeout=       [TIMEOUT (in sec)] Sets the time-out value for a 
	                 remote procedure call (RPC). 
	-o retry  =       [RETRY VALUE] Sets the number of retries for a 
	                 soft mount.
	-o mtype  =       [SOFT | HARD] Sets the mount type.
	-o lang   =       EUC-JP Mounts from a Japanese EUC server.
	-o anon           Mounts as an anonymous user.
	-o nolock         Disables locking.
	-o pcnfs = server Specifies that the PCNFS daemon be used for 
	                 authenticating the user. You must specify the name 
	                 of the user and password with this option. If you 
	                 specify * as the password, you will be prompted to 
	                 provide the password.
	
	----------------------------------------------------------------------
	Erroneous Event Viewer Message
	----------------------------------------------------------------------
	
	The Service Control Manager may display an event in the Event Viewer 
	with the following message: 
	
	    The NfsRdr service failed to start due to the following error: 
	    The system cannot find the file specified.
	
	If this message appears, check to see if the nfsrdr service has 
	started. If it has started, you can ignore the above event. If it has 
	not started, use net start nfsrdr to start the nfsrdr service. 
	
	======================================================================
	SERVER FOR NIS
	======================================================================
	
	----------------------------------------------------------------------
	Maps and Mixed Case
	----------------------------------------------------------------------
	
	If a map contains keys in mixed case, YPMATCH from the HP-UX computer
	might fail when using Server for NIS. HP-UX converts all keys to 
	lowercase before sending the NIS request. This is an issue with HP-UX
	that is beyond the control of Server for NIS. In this situation, 
	convert keys to lowercase before migrating them.
	
	----------------------------------------------------------------------
	Server for NIS Does Not Support YPXFRD
	----------------------------------------------------------------------
	
	Server for NIS does not support YPXFRD, which might lead some UNIX 
	subordinate (slave) NIS servers to display warning messages. The 
	warning messages originate in YPINIT and do not indicate errors. 
	Some UNIX subordinate NIS servers use YPXFRD running on the master 
	NIS server to replicate NIS maps. If they fail to connect to YPXFRD, 
	they obtain copies of NIS maps using yp_all.  
	
	----------------------------------------------------------------------
	Period Not Supported in Non-Standard Maps
	----------------------------------------------------------------------
	
	Server for NIS does not support the use of the period (.) in 
	non-standard maps. For example, "phone.byname" is not supported; 
	use "phone" instead. 
	
	----------------------------------------------------------------------
	Migration of Passwd and Group Maps from NIS Server to Active Directory
	----------------------------------------------------------------------
	
	During migration of passwd and group maps from a UNIX NIS server 
	to Server for NIS, you must migrate the passwd map before migrating 
	the group map. 
	
	----------------------------------------------------------------------
	Migrating Shadow Maps
	----------------------------------------------------------------------
	
	If the NIS domain that you are migrating uses a shadow-enabled passwd
	file, you must migrate the passwd map first, and then migrate the 
	shadow maps, or UNIX user authentication will not work. 
	
	----------------------------------------------------------------------
	Shadow Maps Should Be Included in List of Standard Maps
	----------------------------------------------------------------------
	
	The list of standard maps in Windows Services for UNIX Help should 
	include shadow maps. 
	
	----------------------------------------------------------------------
	Migrating Netmasks and Networks Maps from NIS Server to Active 
	Directory
	----------------------------------------------------------------------
	
	During migration of netmasks and networks maps from a UNIX NIS server 
	to Server for NIS, you must migrate the networks map before migrating 
	netmasks.
	
	----------------------------------------------------------------------
	Migrating Maps to Non-Default Containers
	----------------------------------------------------------------------
	
	If you migrate passwd, groups, or host maps to a container other 
	than the default container (CN=users,..), some migrated entities 
	will not appear by default in Windows 2000 Active Directory Users 
	and Computers. 
	
	>>>To view all objects:
	  
	  1. Click Start, Point to Programs, point to Administrative Tools,
	     and then click Active Directory Users and Computers.
	  2. If a domain is not already selected, select the one you want.
	  3. On the View menu, click Advanced Features.
	
	----------------------------------------------------------------------
	Changing Your Password
	----------------------------------------------------------------------
	
	Do not use the nismap utility to change your password. Use net.exe or
	the Windows interface (CTRL+ALT+DELETE) instead. 
	
	The nismap utility will fail if you edit the passwd entry (using the 
	nismap mod command) where the password field is different from the 
	current value. This value is the encrypted string of the user's 
	password. If you need to edit the passwd entry, use ypcat or ypmatch 
	to retrieve the user's current passwd entry to ensure that the 
	password field is identical. 
	
	----------------------------------------------------------------------
	First Request to Server for NIS May Fail
	----------------------------------------------------------------------
	
	The very first client request to Server for NIS for a large user base 
	(around 10,000 users) might result in a remote procedure call (RPC) 
	time-out because of the time it takes for the service to fetch the 
	data from Active Directory. Subsequent requests will succeed. 
	
	----------------------------------------------------------------------
	Modifying Mail Aliases
	----------------------------------------------------------------------
	
	If you try to modify a mail alias using nismap mod, Server for NIS 
	adds the new alias to the original one instead of replacing it. 
	
	To change the alias, first use nismap del to delete the original 
	alias, and then use nismap add to add the modified alias. 
	
	----------------------------------------------------------------------
	List Ypservers in Ypservers Map
	----------------------------------------------------------------------
	
	The ypservers map should contain a list of ypservers, each one listed 
	on a separate line. The following list is an example of a valid 
	ypservers map:
	
	  ypserver_1
	  ypserver_2
	  ypserver_3
	  .
	  .
	  .
	
	If your ypservers map contains aliases, edit the ypservers map to 
	contain only host names of the ypservers, one per line.
	
	----------------------------------------------------------------------
	Users Do Not Appear in Primary Group List
	----------------------------------------------------------------------
	
	When you migrate passwd and group maps to Server for NIS, users will 
	not be shown to be members of their primary group. For users to show 
	as members of their primary group, you must add them to that group 
	manually.
	
	----------------------------------------------------------------------
	Modifying Properties of Special Users and Groups
	----------------------------------------------------------------------
	
	Do not use the Active Directory Users and Computers snap-in to 
	modify attributes of special users and groups--those with user 
	identifiers (UIDs) or group identifiers (GIDs) of less than 100. 
	If you use the Active Directory snap-in, the data  returned by 
	Serverfor NIS will be incorrect for those users and groups. Use 
	nismap to modify the attributes. 
	
	======================================================================
	USER NAME MAPPING
	======================================================================
	
	----------------------------------------------------------------------
	Clicking Reload After Saving a Map
	----------------------------------------------------------------------
	
	If you click Reload immediately after creating and saving a map, the 
	new map is not shown. Maps are saved to the registry, which notifies 
	User Name Mapping of the new map. Because this process takes about 30 
	seconds, if you click Reload during that time, you will not see 
	current data. 
	
	----------------------------------------------------------------------
	Setting User Name Mapping for Remote Shell Service
	----------------------------------------------------------------------
	
	To set User Name Mapping for Remote Shell Service (RshSvc) after 
	installing Windows Services for UNIX, follow these steps:
	
	1. Stop the service using net stop rshsvc.
	2. Restart the service with this command: 
	
	  rshsvc -start  -m <User Name Mapping computer>
	
	You can then specify the mapping server used by RshSvc. Note 
	that if you specify a mapping server name in this way, the mapping
	server will not be set for other services in Windows Services for
	UNIX.
	
	----------------------------------------------------------------------
	Backup Requires Full Path
	----------------------------------------------------------------------
	
	The backup function in User Name Mapping requires the full path 
	of the file in which the map data is to be stored. 
	
	----------------------------------------------------------------------
	Cannot Use NIS and PCNFS Simultaneously for Creating Maps.
	----------------------------------------------------------------------
	
	Do not use both NIS and PCNFS to create advanced maps. If you 
	want to add advanced maps using NIS, first remove maps that were 
	created using PCNFS. Similarly, if you want to add advanced maps using 
	PCNFS, first remove advanced maps created using NIS.
	
	----------------------------------------------------------------------
	Setting a Primary Map When Adding a Second Map
	----------------------------------------------------------------------
	
	If you use Windows Services for UNIX Administration to add an advanced 
	map, and you map multiple Windows users or groups to a single UNIX 
	user or group, no map is marked as primary by default. You must select
	one of the maps and mark it as primary. 
	
	When you use mapadmin to create multiple maps for a UNIX user, you 
	must use the -setprimary option to specify the primary map. You cannot 
	use the mapadmin command-line utility to change which map is the 
	primary map. You can, however, use Windows Services for UNIX 
	Administration to set the primary map.
	
	----------------------------------------------------------------------
	Help for Mapadmin Does Not Appear
	----------------------------------------------------------------------
	
	If you have not installed User Name Mapping on a computer, you cannot
	view help for mapadmin by typing mapadmin /?. You can still use 
	mapadmin to administer a remote computer where User Name Mapping is 
	installed. To get help for the command, open Help in the Windows 
	Services for UNIX program group.  
	
	======================================================================
	PASSWORD SYNCHRONIZATION
	======================================================================
	
	----------------------------------------------------------------------
	Configuration Files for UNIX-to-Windows Password Synchronization
	----------------------------------------------------------------------
	
	The following lists specify which configuration file to use for the 
	pluggable authentication module (PAM), depending on which operating 
	system you are using: 
	
	Operating system               Configuration file
	
	Solaris and HP                 pam.conf 
	Linux                          pam.d/passwd 
	Digital Equipment Corporation  matrix.conf (for the SIA module)
	
	----------------------------------------------------------------------
	Configuration File for Windows-to-UNIX Password Synchronization
	----------------------------------------------------------------------
	
	You can specify whether Password Synchronize will ignore differences 
	in uppercase and lowercase letters in user names when it compares 
	Windows and UNIX user names. To do this, set the CASE_IGNORE_NAME 
	value in Sso.conf. To allow case-insensitive comparisons, set this 
	entry to 1 (the default). To force Password Synchronization to use 
	case-sensitive comparisons, set this entry to 0.
	
	----------------------------------------------------------------------
	Source Files for the Password Synchronization Daemon
	----------------------------------------------------------------------
	
	If the computer on which you want to install the Password 
	Synchronization daemon is running Compaq Tru64 UNIX version 5.0 or 
	later, the source binary file name is ssod.d40. 
	
	If the computer is running Sun Microsystems Solaris version 2.6 or 
	version 7, the source binary file name is ssod.so7. 
	
	If the computer is running IBM AIX version 4.2, the source binary file 
	name is ssod.a42. 
	
	(Support for Windows-to-UNIX synchronization with computers running 
	IBM AIX version 4.2 was added after the Windows Services for UNIX Help 
	was completed.)
	
	----------------------------------------------------------------------
	Characters Not Allowed in Encryption Keys
	----------------------------------------------------------------------
	
	Encryption keys may not contain a left parenthesis "(", right 
	parenthesis ")", or comma ",".  
	
	----------------------------------------------------------------------
	Only Crypt Method Works for Encryption
	----------------------------------------------------------------------
	
	The Windows Services for UNIX Single Sign-On Daemon (SSOD) supports 
	only the crypt method for encryption of passwords on UNIX computers. 
	
	======================================================================
	TELNET
	======================================================================
	
	----------------------------------------------------------------------
	Some Drive Letters Are Unavailable to Some Telnet Users Under Some 
	Conditions
	----------------------------------------------------------------------
	
	If a local Windows user connects to one or more network drives 
	using drive letters, other users who connect to that user's 
	computer through Telnet will not be able to access those drives. 
	
	Similarly, drive letters used by one Telnet user are unavailable 
	to other Telnet users or to local users. 
	
	----------------------------------------------------------------------
	Changing the Default Shell for Telnet
	----------------------------------------------------------------------
	
	To install the Korn shell as the default for all users, the registry 
	value HKEY_LOCAL_MACHINE/Software/Microsoft/TelnetServer/1.0/Shell 
	should have sh.exe as the data.
	
	----------------------------------------------------------------------
	Accessing Network Resources in a Telnet Session
	----------------------------------------------------------------------
	
	If you authenticate your Telnet session using NTLM, you will be able
	to access only the resources on the computer to which you are 
	connected. Because of NTLM limitations, it might not be possible to 
	access network resources or connect to another computer without 
	providing your user name and password again during the session. 
	To maintain your ability to access network resources during a Telnet 
	session, log on with your user name and password. 
	
	----------------------------------------------------------------------
	Realigning the Cursor with the Prompt
	----------------------------------------------------------------------
	
	If you interrupt and then reconnect a Telnet session that is being 
	conducted from a UNIX computer to a Windows computer, the cursor might
	lose alignment with the prompt. To recover alignment, type the 
	Windows command for "clear screen":
	
		cls 
	
	----------------------------------------------------------------------
	Support for the Euro Symbol Over Telnet
	----------------------------------------------------------------------
	
	Microsoft Windows NT 4.0 Service Pack 4 supports the Euro symbol if 
	Service Pack 4 is installed on both the server and the client. To use
	the Euro symbol, Telnet users must use a TrueType font, such as 
	Lucida Console, during their Telnet sessions.
	
	Before starting Telnet, change the code page to 1252 by typing 
	chcp 1252 at the command prompt. After you connect to the remote 
	Windows NT computer, use chcp 1252 to set the code page of the remote
	session to 1252. 
	
	----------------------------------------------------------------------
	Other Issues
	----------------------------------------------------------------------
	
	* If you start Windows interface applications on a Windows computer 
	 through Telnet, the applications start but do not display their 
	 user interface on the Telnet server. When the Telnet session is
	 disconnected, the applications are closed. To close them before
	 disconnecting, use Task Manager or other utilities such as ps or
	 kill.
	
	* Windows Services for UNIX does not support Input Method Editor 
	 (IME) on Telnet Server. As a result, most 16-bit applications
	 will not accept Japanese input.
	
	* In Help for Telnet Client, the topic "Set Telnet options" does not 
	 include the options bsasdel, crlf, delasbs, or mode. These options
	 are described in Help for UNIX Shell and Utilities under UNIX 
	 utilities. 
	
	* Some of the tips in the Troubleshooting section of Help for Telnet 
	 Client actually pertain to Client for NFS and can be ignored.
	
	----------------------------------------------------------------------
	Screen Problems in Telnet Client	
	----------------------------------------------------------------------
	
	If you experience corruption (misaligned characters and lines) on the 
	Telnet Client display when connecting to Windows Services for UNIX 
	Telnet Server, the problem might be caused by a mismatch between the 
	size of the Telnet Client window and the maximum size of the command 
	window that Telnet Server can support. Try reducing the size of the 
	Telnet Client window before reconnecting. 
	
	======================================================================
	ADMINISTERING WINDOWS SERVICES FOR UNIX
	======================================================================
	
	----------------------------------------------------------------------
	Remote Administration
	----------------------------------------------------------------------
	
	You can use Windows Services for UNIX Administration to administer 
	components on remote computers. However, some administration features
	for Server for PCNFS (passwd and group files) might not work.
	
	----------------------------------------------------------------------
	Administering a Remote Computer
	----------------------------------------------------------------------
	
	In addition to the methods described in Windows Services for UNIX Help
	for connecting to a remote computer, you can also connect to a remote 
	computer by typing the following at a command line:
	
	runas /profile /u:<domainuser>\<remoteadmin> "cmd.exe"  
	
	You can then run tnadmin or any other command-line utility to manage 
	the remote server.
	
	----------------------------------------------------------------------
	A Command Fails in Remote Administration 
	----------------------------------------------------------------------
	
	When you are administering a Windows Services for UNIX service on a 
	remote computer and you send a command to start, stop, pause, or 
	continue, you might get a message that the command completed 
	successfully when it did not. If that happens, use Telnet to connect
	to the computer you want to administer remotely, and run the command
	on that computer.
	
	----------------------------------------------------------------------
	Connecting to NFS Shares Using Dfs
	----------------------------------------------------------------------
	
	You can connect to NFS shares through a Distributed file system (Dfs)
	server by using Client for NFS on each client computer. However, 
	before accessing the Dfs link, you must connect to the NFS shares 
	using the net command on the computer that is the Dfs server.
	
	----------------------------------------------------------------------
	Microsoft Office 2000 Installer Appears When Starting 
	Windows Services for UNIX Administration
	----------------------------------------------------------------------
	
	If you install Microsoft Office 2000 on a computer and then install 
	Windows Services for UNIX, the Microsoft Office 2000 installer might
	appear when you try to start Windows Services for UNIX Administration
	while logged on as a different user from the one who installed 
	Microsoft Office 2000. This is because Microsoft Office 2000 must 
	complete the installation for the new user. 
	
	To prevent this problem, the first time you log on as a user other
	than the one who installed Microsoft Office 2000, open a Microsoft 
	Office 2000 application first and allow Microsoft Office 2000 to 
	complete its setup. From then on, you will be able to start 
	Windows Services for UNIX  Administration without the 
	Microsoft Office 2000 installer appearing. 
	
	---------------------------------------------------------------------
	Index and Search for Windows Services for UNIX Does Not Appear 
	Within Microsoft Management Console
	---------------------------------------------------------------------
	
	When you use Windows Services for UNIX on a computer that is running
	Windows NT 4.0, the index and search features associated with Windows
	Services for UNIX will not appear when you open Help from the 
	Microsoft Management Console snap-in, Windows Services for UNIX
	Administration. To view the Help index and search features on 
	Windows NT 4.0, open Help for Services for UNIX from the Windows 
	Services for UNIX program group.
	
	---------------------------------------------------------------------
	Using Nisadmin to Manage Server for NIS on a Remote Computer
	---------------------------------------------------------------------
	
	To use nisadmin to manage Server for NIS on a remote computer, you 
	must type \\ in front of the name of the computer. For example, to 
	synchronize the updates to maps with all subordinate servers on all 
	domains, you would type:
	
		nisadmin -s \\remtedc syncall 
	
	======================================================================
	USING UNIX UTILITIES
	======================================================================
	
	----------------------------------------------------------------------
	Running Cron Jobs After Date or Time Change
	----------------------------------------------------------------------
	
	If the system date or time is changed when the cron service is 
	running, restart the cron service to ensure that the scheduled 
	jobs run correctly. 
	
	----------------------------------------------------------------------
	Kill -TERM Does Not Work on Linux 5.2.
	----------------------------------------------------------------------
	
	kill -TERM <ssod PID> does not work on Linux 5.2. 
	Instead, to stop ssod, use:
	
	kill -9 <ssod PID>
	
	----------------------------------------------------------------------
	Deleting Persistent Connections
	----------------------------------------------------------------------
	
	If you make a persistent connection with mount.exe, you must use 
	umount.exe to delete the connection. Net use and Windows Explorer 
	will not delete the connections. 
	
	----------------------------------------------------------------------
	Correction for -p Option in Rshsvc
	----------------------------------------------------------------------
	
	The reference page description of the -p option for rshsvc is 
	incorrect. The correct description is: 
	
	  -p:   Do not use passwords stored locally for users. (Passwords 
	        for individual users can be stored by running the rshpswd 
	        command.)
	
	----------------------------------------------------------------------
	Tar Removed from Windows Services for UNIX Utilities
	----------------------------------------------------------------------
	
	The tar.exe utility has been removed from Windows Services for UNIX. 
	Disregard information about tar in Windows Services for UNIX Help. 
	
	Additional query words: sfu solar coaster solarcoaster
	
	======================================================================
	Keywords          :  
	Technology        : kbWinServiceUNIX200 kbWinServiceUNIXSearch
	Version           : :2.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
