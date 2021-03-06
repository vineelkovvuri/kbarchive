---
layout: page
title: "Q100770: HOWTO: Use Accelerator Keys with Modal Dialog Box Main Window"
permalink: /kb/100/Q100770/
---

## Q100770: HOWTO: Use Accelerator Keys with Modal Dialog Box Main Window

{% raw %}

	Article: Q100770
	Product(s): Microsoft C Compiler
	Version(s): 2.0,2.1,4.0,5.0,6.0
	Operating System(s): 
	Keyword(s): kbui kbGrpDSMFCATL kbVC100 kbVC150 kbVC151 kbVC152 kbVC200 kbVC210 kbVC400 kbVC500 kbVC
	Last Modified: 26-JUL-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- The Microsoft Foundation Classes (MFC), used with:
	   - Microsoft Visual C++ 
	   - Microsoft Visual C++, 32-bit Editions, versions 2.0, 2.1, 4.0, 5.0, 6.0 
	   - Microsoft Visual C#.NET (2002) 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Many applications use a modal dialog box as the main application window.
	Applications that use this technique may also include a main menu on the dialog
	box. Typically, one or more of the menu items has a keyboard accelerator
	associated with it. This article describes the steps that are required to add a
	menu and keyboard accelerators to an MFC Application Wizard dialog box-based
	application.
	
	MORE INFORMATION
	================
	
	A typical application that is developed for the Microsoft Windows operating
	system by using Visual C++ and the Microsoft Windows Software Development Kit
	(SDK) and that uses keyboard accelerators calls the TranslateAccelerator()
	function in its main message loop. However, when you use a modal dialog box as
	the main window, the application does not have a main message loop; instead, the
	application uses the dialog box manager message loop (built into Windows) to
	translate and dispatch messages. Of course, because this message loop is not
	designed to process accelerators, it does not call the TranslateAccelerator()
	function.
	
	To process accelerator keys in a modal dialog box in MFC, you must override the
	CWinApp::ProcessMessageFilter() function. The framework calls
	ProcessMessageFilter() before it processes a message.
	
	To modify an MFC Application Wizard dialog box-based application type in Visual
	C++ .NET to correctly process accelerator keys, follow these steps:
	
	1. In Visual Studio .NET, create a new MFC application. In the left pane of the
	  MFC Application Wizard, click Application Type, and then make sure that
	  Application type is set to Dialog based.
	
	2. In Resource view, double-click the dialog resource to open the dialog
	  resource editor. The resource ID of the dialog resource is similar to
	  IDD_<MYPROJECT>_DIALOG (where <MYPROJECT> is the name that you
	  gave your application project when you created it).
	
	3. With the dialog resource open in the dialog resource editor, locate the
	  Properties window. Edit the dialog box Border property and specify the Thin
	  border style. This step is required for a dialog box that contains a menu.
	
	4. Create a new menu resource that contains a top-level entry named &File
	  and a menu item named &Exit\tCTRL+E (CTRL+X is usually associated with
	  cutting text, so CTRL+E is used instead).
	
	5. In the menu editor, click the newly created Exit menu item. In the Properties
	  window, make sure that the ID property for the Exit menu item is set to
	  ID_FILE_EXIT.
	
	6. Associate the new menu with the dialog box by entering the menu ID in the
	  dialog resource Menu property. Open the dialog editor for the dialog resource
	  and find the Menu property in the Properties window. Set it to the resource
	  ID that you created for the menu in step 4. To do this, click the drop-down
	  list in the Menu property row, and then click to select the resource ID for
	  the menu in the list.
	
	7. In the menu editor, right-click &Exit\tCTRL+E, and then click Add Event
	  Handler.
	
	8. In the Event Handler Wizard, select the COMMAND message type. In the Class
	  list, select the CDialog derived main class for the handler to be generated
	  in. Make sure that the function handler name is appropriate, and then click
	  Add and Edit to create the menu item event handler.
	
	9. Insert the following line in the function Exit menu item event handler method
	  that is generated in step 8:
	
	  PostMessage(WM_COMMAND, IDOK, 0L);
	
	This produces the same effect as clicking OK when the user clicks Exit on the
	File menu. Clicking OK closes your dialog box application.
	
	10. Create a new accelerator resource and associate the CTRL+E key combination
	  with ID_FILE_EXIT. Save your changes.
	
	11. Edit the Stdafx.h file to declare the following global variables after the
	  #include statements:
	
	  extern HWND    ghDlg;          // Handle to main dialog box.
	  extern HACCEL  ghAccelTable;   // Handle to accelerator table.
	
	12. In the .cpp file that contains the CWinApp derived class implementation
	  (usually the .cpp file with the same base name as your project name), add
	  the following global variable initializations:
	
	  HWND    ghDlg = 0;          // Handle to main dialog box.
	  HACCEL  ghAccelTable = 0;   // Handle to accelerator table.
	
	13. In the main CDialog derived class (not the dialog class that implements the
	  default About dialog box), find the OnInitDialog() method. If necessary, you
	  can add an override for the OnInitDialog() method. To do this, click to
	  select the CDialog derived class in the Class View window, and then click
	  Overrides in the Properties window. Find the OnInitDialog row and click the
	  right column. If OnInitDialog() is not overridden for this class, you have
	  the option to create an override.
	
	14. Edit the function that you added earlier to include the following line of
	  code:
	
	  ghDlg = m_hWnd;
	
	15. In the .cpp file that contains the CWinApp derived implementation, find the
	  InitInstance() class method. Add the following line immediately after the
	  call to the base class CWinApp::InitInstance():
	
	  ghAccelTable = LoadAccelerators(AfxGetInstanceHandle(),
	  MAKEINTRESOURCE(IDR_ACCELERATOR1));
	
	NOTE: The resource ID that is used here (IDR_ACCELERATOR1) is the ID of the
	accelerator table resource that is added in step 10.
	
	16. Add an override to the CWinApp derived class for the ProcessMessageFilter()
	  class method. To do this, in the Class View window, select the CWinApp
	  derived class in your project. Then, in the Properties window, click
	  Overrides. Find the ProcessMessageFilter row in the Properties window and
	  select the right-most column of that row. Click the drop-down arrow, and
	  then click the option to add an override for the ProcessMessageFilter
	  method.
	
	17. Edit the ProcessMessageFilter() method override so that it has the following
	  implementation:
	
	  BOOL CMyProjectApp::ProcessMessageFilter(int code, LPMSG lpMsg)
	         {
	            if (code < 0)
	               CWinApp::ProcessMessageFilter(code, lpMsg);
	
	            if (ghDlg && ghAccelTable)
	               {
	               if (::TranslateAccelerator(ghDlg, ghAccelTable, lpMsg))
	                  return(TRUE);
	               }
	
	           return CWinApp::ProcessMessageFilter(code, lpMsg);
	        }
	
	18. Compile and run the application. Note that it has a menu. When you click
	  Exit on the File menu or press CTRL+E, the application closes, as expected.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbui kbGrpDSMFCATL kbVC100 kbVC150 kbVC151 kbVC152 kbVC200 kbVC210 kbVC400 kbVC500 kbVC600 kbKeyAccel kbMenu kbMFC kbAcceleratorKey 
	Technology        : kbAudDeveloper kbMFC
	Version           : :2.0,2.1,4.0,5.0,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
