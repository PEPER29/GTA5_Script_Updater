# GTA5_Script_Updater

<img width="1672" height="941" alt="GTA5_scripts_manager" src="https://github.com/user-attachments/assets/5c1a808a-7643-4939-b51c-d082e28725a1" />


A Windows desktop app for managing GTA V scripts and plugins.

<img width="1273" height="987" alt="image" src="https://github.com/user-attachments/assets/bdf29e9e-afda-4d87-848d-81d4cef5abfe" />

```powershell
#For Future update WIP
- add scripts log Tab
- favori scripts Tab
Any requests for additions/modifications will be considered; the plan for the upcoming update is not yet complete.
```

```powershell
#Changelog: v1.1.0 (manual modification patch)
- Added a context menu [right-click] to edit the entry (URL, INI path, local version, script name)
- Update checks will prioritize the provided URL
- Option to switch between English and French (available since v1.0.0 but not previously listed)
```

----------------------------------------------------------------------------------------
-                                                                                      -
--------------------------------------------EN------------------------------------------
-                                                                                      -
----------------------------------------------------------------------------------------

GTA5 Script Updater is a PySide6 desktop application designed to inventory GTA V scripts and plugins, manage their local status, and manually check for updates.

-- ##Features

Scans .asi files in the root folder, recognized GTA V dependencies (including ScriptHookV.dll, dinput8.dll, and RagePluginHook.exe), scripts in the scripts/ folder, and plugins in the Plugins/ folder.

Recognizes .disabled files, .dll, .cs, and .vb extensions in supported locations, and detects matching .ini files with the same base name.

Extracts version information from Windows PE resources, then from an associated INI file, then from a number present in the filename.

Opens the associated INI or the containing folder, enables/disables scripts by renaming, and supports favorites and an ignored items list.

Detects common activation keys in associated INI files and displays them in the Keys column. Standalone modifiers are excluded, combined modifiers are stripped from the value, and an empty/unassigned value is kept visibly empty.

Resizable table columns.

Dark and light themes, filters, search, persistent preferences, and debug mode.

Logs / Debug tab available inside the application, plus a detailed log file stored in the user’s configuration folder.

Version checking against GTA5-Mods.com,
[LCPDFR via its official API (optional LCPDFR_API_KEY)]
for RPH plugins, and GitHub Releases for ScriptHookVDotNet and Enhanced Native Trainer.

Multi-term GTA5-Mods search with manual aliases for popular mods, explicit confidence threshold, and a “possible match” status for results that need manual verification.

Semantic version comparison, configurable JSON cache (12 hours by default), HTTP timeout capped at 12 seconds and a 15-second budget per script, 3-second delay only after a successful request, clear HTTP error logging, and cancellation from the progress button.

Direct access to the online page when a match is found; dedicated filter for available updates.

LCPDFR web scraping is disabled. Without an LCPDFR_API_KEY, this provider makes no requests.

GTA5-Mods pages are queried at a low frequency and without any anti-bot bypass. If a site refuses access or does not respond, the result is reported as an error rather than “up to date”.

Common dependency libraries (e.g. Newtonsoft.Json, NAudio, EasyHook, System.*, Microsoft.*) are not checked. The tool never downloads or installs any files.

-- ##Installation


Python 3.11 or newer is recommended. From the project folder:
```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```
-- ##Usage

1- Select the folder containing GTA5.exe, then click Scan.

2- Filter the list by type, status, favorites, or ignored items; the search also filters by name.

3- Use the actions on each row to open the INI, open the folder, enable/disable, or mark as favorite.

4- Right-click a row to ignore or restore it.

5- Click Check for updates to compare online versions. The progress bar immediately shows the current script and its counter (e.g. “Checking 12/89 – HeapAdjuster.asi…”); the row status changes to “In progress…”. 
The button becomes Cancel check during processing, and partial results remain visible.

6- The With update filter shows only versions detected as newer. The Page button on each row opens the corresponding page after a successful search.

7- In Preferences, change the theme, enable debug mode, or adjust the cache duration for results (1 to 168 hours).

8- Open the Logs / Debug tab to view diagnostics or open the log file. The file can also be opened directly from this tab.

Settings are saved in %LOCALAPPDATA%\GTA5ScriptUpdater\settings.json.

The cache is stored in %LOCALAPPDATA%\GTA5ScriptUpdater\update_cache.json

and logs in %LOCALAPPDATA%\GTA5ScriptUpdater\logs\updater.log

(with a fallback location in the user folder on other platforms).

**Important technical notes**

- This version can search on LCPDFR (if you provide the API key).
- May freeze slightly during the update check.
- Normalized matching (extensions, versions, and common suffixes removed), manual aliases for known mods; scores below 75 % are shown as “possible match” rather than a confirmed update.
- Scripts not found during update checks are usually caused by a filename that differs from the actual mod name or is poorly formatted.
- Missing INI files are the result of a different name than the script.

----------------------------------------------------------------------------------------
-                                                                                      -
--------------------------------------------FR------------------------------------------
-                                                                                      -
----------------------------------------------------------------------------------------

**GTA5 Script Updater** est une application de bureau PySide6 pour inventorier les scripts et plugins GTA V, gérer leur état local et vérifier manuellement les mises à jour...


## Fonctionnalités

- Scan des fichiers `.asi` de la racine, des dépendances GTA V reconnues (dont `ScriptHookV.dll`, `dinput8.dll` et `RagePluginHook.exe`), des scripts de `scripts/` et des plugins de `Plugins/`.

- Reconnaissance des fichiers `.disabled`, des extensions `.dll`, `.cs` et `.vb` dans les emplacements pris en charge, et détection des fichiers INI homonymes.

- Extraction de version depuis les ressources PE Windows, puis depuis un INI, puis depuis un numéro présent dans le nom du fichier.

- Ouverture de l’INI associé ou du dossier, activation/désactivation par renommage, favoris et liste des éléments ignorés.

- Détection des touches d’activation courantes dans les INI associés, affichées dans la colonne **Touches**; les modificateurs seuls sont exclus, les modificateurs combinés sont retirés de la valeur, et une valeur non renseignée reste visiblement vide.

- Colonnes du tableau redimensionnables 

- Thèmes sombre et clair, filtres, recherche, préférences persistantes et mode debug.

- Onglet **Journaux / Debug** accessible dans l’application et fichier de log détaillé conservé dans le dossier de configuration utilisateur.

- Vérification des versions publiée sur GTA5-Mods.com, 
[ LCPDFR via son API officielle "manquant" (clé optionnelle `LCPDFR_API_KEY`) ] 
pour les plugins RPH et GitHub Releases pour ScriptHookVDotNet et Enhanced Native Trainer.

- Recherche GTA5-Mods multi-termes avec alias manuels pour les mods populaires, seuil de confiance explicite et statut « correspondance possible » pour les résultats à vérifier.

- Comparaison sémantique des versions, cache JSON configurable (12 h par défaut), timeout
HTTP plafonné à 12 secondes et budget de 15 secondes par script, délai de 3 secondes uniquement après une requête réussie, journalisation claire des erreurs HTTP et annulation depuis le bouton de progression.

- Accès direct à la page en ligne lorsqu’une correspondance a été trouvée; filtre dédié aux mises à jour disponibles.

Le scraping web de LCPDFR est désactivé; sans clé `LCPDFR_API_KEY`, ce provider n’effectue aucune requête. 
Les pages GTA5-Mods sont consultées à faible fréquence et sans contournement des protections anti-bot. Si un site refuse l’accès ou ne répond pas, le résultat est signalé comme erreur plutôt que comme « à jour ». 
Les bibliothèques de dépendances communes (par ex. `Newtonsoft.Json`, `NAudio`, `EasyHook`, `System.*`, `Microsoft.*`) ne sont pas vérifiées; La vérification ne télécharge ni n’installe de fichiers.

## Installation

Python 3.11 ou plus récent est recommandé. Depuis le dossier du projet :

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python main.py
```

## Utilisation

1. Choisissez le dossier contenant `GTA5.exe`, puis lancez **Scanner**.
2. Filtrez la liste par type, état, favoris ou éléments ignorés; la recherche filtre aussi par nom.
3. Utilisez les actions de chaque ligne pour ouvrir l’INI, ouvrir le dossier, activer/désactiver ou marquer un favori.
4. Faites un clic droit sur une ligne pour l’ignorer ou la rétablir.
5. Cliquez sur **Vérifier les mises à jour** pour comparer les versions en ligne. La progression affiche immédiatement le script en cours et son compteur (par ex. « Vérification 12/89 – HeapAdjuster.asi… »); le statut de sa ligne passe à « En cours… ». Le bouton devient **Annuler la vérification** pendant le traitement, et les résultats partiels restent visibles.
6. Le filtre **Avec mise à jour** ne montre que les versions détectées comme plus récentes. Le bouton **Page** de chaque ligne ouvre la page correspondante après une recherche réussie.
7. Dans **Préférences**, changez le thème, activez le mode debug ou réglez la durée de cache des résultats (1 à 168 heures).
8. Ouvrez l’onglet **Journaux / Debug** pour consulter les diagnostics ou ouvrir le fichier de log. Le fichier peut aussi être ouvert directement depuis cet onglet.

Les réglages sont enregistrés dans `%LOCALAPPDATA%\GTA5ScriptUpdater\settings.json`. Le cache est dans `%LOCALAPPDATA%\GTA5ScriptUpdater\update_cache.json` et les journaux dans `%LOCALAPPDATA%\GTA5ScriptUpdater\logs\updater.log` (avec un emplacement de repli dans le dossier utilisateur sur les autres plateformes).


--------------------------------
**Points techniques importants**
--------------------------------
- Cette version est capable de rechercher sur lspdfr (si vous trouvez l'api).

- Peut freezer légèrement pendant la recherche de mise a jours.

- Matching normalisé (extensions, versions et suffixes courants retirés), alias manuels pour des mods connus; score inférieur à 75 % présenté comme correspondance possible plutôt qu’une mise à jour confirmée.

- Scripts introuvables par les mises a jour sont la cause d'un nom de fichier différent du script ou mal formatée.

- ini introuvable est la conséquence d'un nom différent de celui du script.
