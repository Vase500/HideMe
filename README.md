# HideMe

HideMe is a simple, easy to use and lightweight PowerShell script that can remove pre-installed Windows bloatware apps, disable telemetry and declutter the experience by disabling or removing intrusive interface elements, ads and more. No need to painstakingly go through all the settings yourself or remove apps one by one. HideMe makes the process quick and easy!

The script also includes many features that system administrators will enjoy. Such as support for Windows Audit mode, the option to make changes to other Windows users and the ability to run the script without requiring user input during runtime.

App Removal
Remove a wide variety of bloatware apps.
Remove all pinned apps from start for the current user, or for all existing & new users. (Windows 11 only)
Telemetry, Tracking & Suggested Content
Disable telemetry, diagnostic data, activity history, app-launch tracking & targeted ads.
Disable tips, tricks, suggestions and ads in start, settings, notifications, File Explorer, and on the lockscreen.
Disable the 'Windows Spotlight' desktop background option.
Bing Web Search, Copilot & More
Disable & remove Bing web search & Cortana from Windows search.
Disable & remove Microsoft Copilot. (W11 only)
Disable Windows Recall snapshots. (W11 only)
File Explorer
Change the default location that File Explorer opens to.
Show hidden files, folders and drives.
Show file extensions for known file types.
Hide the Home or Gallery section from the File Explorer navigation pane. (W11 only)
Hide the 3D objects, music or OneDrive folder from the File Explorer navigation pane. (W10 only)
Hide duplicate removable drive entries from the File Explorer navigation pane, so only the entry under 'This PC' remains.
Taskbar & Start
Align taskbar icons to the left. (W11 only)
Hide or change the search icon/box on the taskbar. (W11 only)
Hide the taskview button from the taskbar. (W11 only)
Disable the widgets service & hide icon from the taskbar.
Hide the chat (meet now) icon from the taskbar.
Disable & hide the recommended section in the start menu. (W11 only)
Enable the 'End Task' option in the taskbar right click menu. (W11 only)
Context Menu
Restore the old Windows 10 style context menu. (W11 only)
Hide the 'Include in library', 'Give access to' and 'Share' options from the context menu. (W10 only)
Other
Disable Xbox game/screen recording, this also stops gaming overlay popups.
Turn off Enhance Pointer Precision, also known as mouse acceleration.
Disable Fast Start-up to ensure a full shutdown.
Disable the Sticky Keys keyboard shortcut. (W11 only)
Option to apply changes to a different user, instead of the currently logged in user.
Sysprep mode to apply changes to the Windows Default user profile. Afterwards, all new users will have the changes automatically applied to them.
Default Settings
The script allows you to select exactly what changes you want to make, but it also provides a 1-click default mode. The default mode allows you to quickly and easily apply the changes that are recommended for most users. Expand the section below for more info.

Click to expand
Usage
Warning

Great care went into making sure this script does not unintentionally break any OS functionality, but use at your own risk!

Quick method
Download & run the script automatically via PowerShell. All files related to the script are saved to %temp%/HideMe if you wish to inspect them. The script automatically cleans up the files after execution.

Open PowerShell, preferably as an administrator.
Copy and paste the code below into PowerShell, press enter to run the script:
& ([scriptblock]::Create((irm "https://debloat.raphi.re/")))
Wait for the script to automatically download HideMe.
A new PowerShell window will open showing the HideMe menu. Select either the default or custom mode to continue.
Carefully read through and follow the on-screen instructions.
This method supports parameters. To use parameters simply run the script as explained above, but add the parameters at the end with spaces in between. Example:

& ([scriptblock]::Create((irm "https://debloat.raphi.re/"))) -RunDefaults -Silent
Traditional method
Manually download & run the script.

Download the latest version of the script, and extract the .ZIP file to your desired location.
Navigate to the HideMe folder
Double click the Run.bat file to start the script. NOTE: If the console window immediately closes and nothing happens, try the advanced method below.
Accept the Windows UAC prompt to run the script as administrator, this is required for the script to function.
A new PowerShell window will now open showing the HideMe menu. Select either the default or custom mode to continue.
Carefully read through and follow the on-screen instructions.
Advanced method
Manually download the script & run the script via PowerShell. Recommended for advanced users.

Download the latest version of the script, and extract the .ZIP file to your desired location.
Open PowerShell as an administrator.
Temporarily enable PowerShell execution by entering the following command:
Set-ExecutionPolicy Unrestricted -Scope Process
In PowerShell, navigate to the directory where the files were extracted. Example: cd c:\HideMe
Now run the script by entering the following command:
.\HideMe.ps1
The HideMe menu will now open. Select either the default or custom mode to continue.
Carefully read through and follow the on-screen instructions.
This method supports parameters. To use parameters simply run the script as explained above, but add the parameters at the end with spaces in between. Example:

.\HideMe.ps1 -RemoveApps -DisableBing -Silent
Parameters
The quick and advanced usage methods support switch parameters. A table of all the supported parameters and what they do can be found below.

Parameter	Description
-Silent	Suppresses all interactive prompts, so the script will run without requiring any user input.
-Sysprep	Run the script in Sysprep mode. All changes will be applied to the Windows default user profile and will only affect new user accounts.
-User <USERNAME>	Run the script for the specified user, instead of the currently logged in user. This user must have logged on atleast once, and cannot be logged in at the time the script is run.
-RunDefaults	Run the script with the default settings.
-DisableFastStartup	Disables Fast Start-up to ensure a full shutdown.
-RunSavedSettings	Run the script with the saved custom settings from last time. These settings are saved to and read from the SavedSettings file in the root folder of the script.
-RemoveApps	Remove the default selection of bloatware apps.
-RemoveAppsCustom	Remove all apps specified in the 'CustomAppsList' file. IMPORTANT: You can generate your custom list by running the script with the -RunAppsListGenerator parameter. No apps will be removed if this file does not exist.
-RunAppsListGenerator	Run the apps list generator to generate a custom list of apps to remove, the list is saved to the 'CustomAppsList' file inside the root folder of the script. Running the script with the -RemoveAppsCustom parameter will remove the selected apps.
-RemoveCommApps	Remove the Mail, Calendar, and People apps.
-RemoveW11Outlook	Remove the new Outlook for Windows app.
-RemoveDevApps	Remove developer-related apps such as Remote Desktop, DevHome and Power Automate.
-RemoveGamingApps	Remove the Xbox App and Xbox Gamebar.
-ForceRemoveEdge	Forcefully remove Microsoft Edge, this option leaves Core, WebView and Update components installed for compatibility. NOT RECOMMENDED!
-DisableDVR	Disable Xbox game/screen recording feature & stop gaming overlay popups.
-ClearStart	Remove all pinned apps from start for the current user (Windows 11 update 22H2 or later only)
-ClearStartAllUsers	Remove all pinned apps from start for all existing and new users. (Windows 11 update 22H2 or later only)
-DisableTelemetry	Disable telemetry, diagnostic data & targeted ads.
-DisableSuggestions	Disable tips, tricks, suggestions and ads in start, settings, notifications and File Explorer.
-DisableDesktopSpotlight	Disable the 'Windows Spotlight' desktop background option.
-DisableLockscreenTips	Disable tips & tricks on the lockscreen.
-DisableBing	Disable & remove Bing web search, Bing AI & Cortana in Windows search.
-DisableCopilot	Disable and remove Microsoft Copilot. (Windows 11 only)
-DisableRecall	Disable Windows Recall snapshots. (Windows 11 only)
-RevertContextMenu	Restore the old Windows 10 style context menu. (Windows 11 only)
-DisableMouseAcceleration	Turn off Enhance Pointer Precision, also known as mouse acceleration. Requires reboot to apply.
-DisableStickyKeys	Disable the Sticky Keys keyboard shortcut.
-ShowHiddenFolders	Show hidden files, folders and drives.
-ShowKnownFileExt	Show file extensions for known file types.
-HideDupliDrive	Hide duplicate removable drive entries from the File Explorer navigation pane, so only the entry under 'This PC' remains.
-TaskbarAlignLeft	Align taskbar icons to the left. (Windows 11 only)
-HideSearchTb	Hide search icon from the taskbar. (Windows 11 only)
-ShowSearchIconTb	Show search icon on the taskbar. (Windows 11 only)
-ShowSearchLabelTb	Show search icon with label on the taskbar. (Windows 11 only)
-ShowSearchBoxTb	Show search box on the taskbar. (Windows 11 only)
-HideTaskview	Hide the taskview button from the taskbar. (Windows 11 only)
-HideChat	Hide the chat (meet now) icon from the taskbar.
-DisableWidgets	Disable the widget service & hide the widget (news and interests) icon from the taskbar.
-EnableEndTask	Enable the 'End Task' option in the taskbar right click menu.
-DisableStartRecommended
Disable & hide the recommended section in the start menu. This will also change the start menu layout to More pins.
-HideHome	Hide the home section from the File Explorer navigation pane and add a toggle in the File Explorer folder options. (Windows 11 only)
-HideGallery	Hide the gallery section from the File Explorer navigation pane and add a toggle in the File Explorer folder options. (Windows 11 only)
-ExplorerToHome	Change File Explorer to open to Home.
-ExplorerToThisPC	Change File Explorer to open to This PC.
-ExplorerToDownloads	Change File Explorer to open to Downloads.
-ExplorerToOneDrive	Change File Explorer to open to OneDrive.
-HideOnedrive	Hide the OneDrive folder from the File Explorer navigation pane. (Windows 10 only)
-Hide3dObjects	Hide the 3D objects folder under 'This pc' in File Explorer. (Windows 10 only)
-HideMusic	Hide the music folder under 'This pc' in File Explorer. (Windows 10 only)
-HideIncludeInLibrary	Hide the 'Include in library' option in the context menu. (Windows 10 only)
-HideGiveAccessTo	Hide the 'Give access to' option in the context menu. (Windows 10 only)
-HideShare	Hide the 'Share' option in the context menu. (Windows 10 only)
