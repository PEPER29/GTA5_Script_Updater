
# GTA5_Script_Updater

<img width="1920" height="1080" alt="GTAscriptmanager" src="https://github.com/user-attachments/assets/69659896-7a95-40d3-a496-3fd217c7e282" />


A Windows desktop app for managing GTA V scripts and plugins.

<img width="317" height="245" alt="image" src="https://github.com/user-attachments/assets/f14ae096-0718-467c-abb1-da230afc76db" /><img width="317" height="245" alt="image" src="https://github.com/user-attachments/assets/17416d02-42d3-44c0-88eb-f77fc7c2123e" /><img width="317" height="245" alt="image" src="https://github.com/user-attachments/assets/0b2b29d5-6a32-4edc-a99f-689b17449941" />

<a href="https://github.com/PEPER29/GTA5_Script_Updater/blob/main/PLAN%20%3A%20future%20Update">For more details (future-Update)</a>

<div style="font-family: 'Segoe UI', Arial, sans-serif; border: 1px solid #e4e4e7; border-radius: 8px; padding: 20px; max-width: 500px; margin: 20px auto; background-color: #fafafa; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
  
  <!-- Titre fixe de l'encadré -->
  <h2 style="font-size: 18px; color: #18181b; margin: 0 0 15px 0; font-weight: 700; text-align: center; border-bottom: 1px solid #e4e4e7; padding-bottom: 10px;">
    📜 Update history
  </h2>
  
```powershell

#Changelog: v.1.2.0 (Fonction scripts log and profile Update) *+optimisations
- Add a "Script Logs" tab
- Implement a feature for the software to scan `.log` files and highlight them based on their content:
   Red: logs containing terms such as "error", "Fatal error", "Crash", etc.
   Orange: logs containing terms such as "Warning", "Deprecated", "Out of memory", etc.
   Green: logs that contain no errors. 
  in 2 steps / functions:
   1. scan the log files (one button or when application scan through your list of scripts)
   2. scan the content of the log files (button)
(scan only the game root directory, excluding subfolders—with the exception of the "scripts" and "plugins" folders).
- Added a profile selector (presets)
  Save and load enabled/disabled scripts
- A "share profile" feature that automatically list the enabled scripts and exports them in a .txt format
(useful for sharing a working script profile, or simply for debugging in the event of a crash—for instance, when seeking help on forums, etc.)
  file saved in root GTA5 folder : curent_profile.txt
- Thread reduction: the internet scan features a sequential mode to prevent spam.*
- Experimental feature "gta5-mods" API_KEY option (non-useable but in the future...)

#Changelog: v.1.1.5 (Better app Update)
- LSPDFR support (API)
  Implement proper search/update checking via the official LSPDFR API.
  Add a field in Preferences to enter an LSPDFR API key.
  bIf no API key is provided, keep the provider disabled and show a clear message.
- Nexus Mods support (API)
  Implement search/update checking for Nexus Mods.
  Add a field in Preferences to enter a Nexus Mods personal API key.
  If no API key is provided, keep the provider disabled and show a clear message
- Manual hotkey editing (Manual-Edit MOD)
  In the existing “Edit information…” dialog (right-click on a row).
  add a dedicated section to manually set/edit the activation hotkeys.
  This allows the user to correct or add hotkeys when automatic detection fails.
  Save the manual hotkeys persistently with the other overrides. 
- Logo + Version in the interface (UI)
  Replace the current text title “GTA Script Updater” with the application logo 
  display the current version number in the format: V:1.2.0

#Changelog: v.1.1.0 (manual modification patch)
- Added a context menu [right-click] to edit the entry (URL, INI path, local version, script name)
- Update checks will prioritize the provided URL
- Option to switch between English and French (available since v1.0.0 but not previously listed)
```

<div style="font-family: 'Georgia', serif; border-left: 4px solid #0076ff; padding-left: 15px; margin-bottom: 25px;">
  <h2 style="font-size: 22px; color: #1a1a1a; margin: 0; font-weight: normal; font-style: italic;">
    #-------------------EN-------------------
  </h2>
</div>


GTA5 Script Updater is a PySide6 desktop application designed to inventory GTA V scripts and plugins, manage their local status, and manually check for updates.

<div style="font-family: 'Georgia', serif; border-left: 4px solid #0076ff; padding-left: 15px; margin-bottom: 25px;">
  <h2 style="font-size: 22px; color: #1a1a1a; margin: 0; font-weight: normal; font-style: italic;">
    ##-Features
  </h2>
</div>

- Full scan of scripts (.asi, .NET, RPH, etc.)
- Direct access to configuration .ini files
- Quick enable/disable for scripts
- Detection and display of activation keys
- Update checks (GTA5-Mods, Nexus, LSPDFR, GitHub)
- Manual editing of information (version, link, hotkeys, INI)
- Profile system (save/load configurations)
- Profile export (current_profile.txt) for sharing or debugging
- Script Logs tab with error analysis and color-coding
- Multi-language support (French / English)
- Dark and light themes
  
<div style="font-family: 'Georgia', serif; border-left: 4px solid #0076ff; padding-left: 15px; margin-bottom: 25px;">
  <h2 style="font-size: 22px; color: #1a1a1a; margin: 0; font-weight: normal; font-style: italic;">
    ##-Instalation
  </h2>
</div>

Python 3.11 or newer is recommended. From the project folder:
```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

<div style="font-family: 'Georgia', serif; border-left: 4px solid #0076ff; padding-left: 15px; margin-bottom: 25px;">
  <h2 style="font-size: 22px; color: #1a1a1a; margin: 0; font-weight: normal; font-style: italic;">
    ##-Usage and details
  </h2>
</div>

#- The application is available in French and English (this option can be found in the preferences).
Support for other languages ​​may be added if there is sufficient demand.

#- Please prioritize manual entry! (You may run an "update" scan, but only when first setting things up.)
This is especially important for [URLs]; it prevents the application from having to search for them automatically, which consumes a large number of requests.
(Doing so risks getting you blocked by the website due to request-per-minute limits.)
Furthermore, the application might not always find the correct URL (it could even select the wrong one, particularly when multiple scripts share the same name).
Providing complete information for each entry is highly recommended for optimal performance and ease of use.
<a href="https://github.com/PEPER29/GTA5_Script_Updater/blob/main/Manual%20modification%20entry%20details">More details for Manual entry</a>

#- The application searches via:
- https://www.gta5-mods.com/
- https://www.nexusmods.com/ ( /!\ API key required /!\)
- https://www.lcpdfr.com/ ( /!\ API key required /!\)
- https://github.com/

#- Don't forget to enter your API keys for LCPDFR and Nexus Mods (available upon request via your personal account; see the preferences menu).
Without these, the scan will be limited and may fail to detect updates for your scripts.

#- The application will never download scripts for you! You can do this by clicking on "page" (to access the site's webpage).

This software was not created to replace official sites like gta5-mods.com, Nexus, or LSPDFR.

It simply allows you to quickly check whether any of your scripts have available updates.
Given that most of us have at least 50 scripts, checking them one by one becomes tedious and time-consuming.
(This assumes you have already saved the URLs; otherwise, it’s even slower, and you risk ending up on the wrong page, as there are sometimes multiple scripts with the same name...)

#-The GTA5-mods API key is an experimental feature (it is currently impossible to obtain one).
This was included in case GTA5-mods decides to enable a public or private API in the future.
For now, please leave this field blank.

#-The "share profile" function will create a text file (current_profile.txt) in your GTA5 root directory.
Line format: [original script filename] [display name] [local version] [script URL]

#-I recommend setting the update cache to 72 hours or longer (since scripts don't change versions every single day).

- Settings are saved in %LOCALAPPDATA%\GTA5ScriptUpdater\settings.json.
- The cache is located in %LOCALAPPDATA%\GTA5ScriptUpdater\update_cache.json,
- and logs can be found in %LOCALAPPDATA%\GTA5ScriptUpdater\logs\updater.log
  
(with a fallback location in the user directory on other platforms).

<div style="font-family: 'Georgia', serif; border-left: 4px solid #0076ff; padding-left: 15px; margin-bottom: 25px;">
  <h2 style="font-size: 22px; color: #1a1a1a; margin: 0; font-weight: normal; font-style: italic;">
    ##-Important technical notes
  </h2>
</div>

- May freeze slightly during the update check.
- Normalized matching (extensions, versions, and common suffixes removed), manual aliases for known mods; scores below 75 % are shown as “possible match” rather than a confirmed update.
- Scripts not found during update checks are usually caused by a filename that differs from the actual mod name or is poorly formatted.
- Missing INI files are the result of a different name than the script.

  <img width="500" height="120" alt="logo" src="https://github.com/user-attachments/assets/8f3c67c5-6131-426f-a132-2c1ea6ff2811" />
16/10/2026

