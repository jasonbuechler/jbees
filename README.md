# These files are what Kodi "looks at" (for *install-via-repo*)

Sooo... there is not much point in uploading your repository.whatever-1.2.3.zip (the zip of your own repo "addon") to the actual repo.

...because you'll *always* be adding your repo **via zip**.
And only after this repo addon is installed, can you then install **other** addons *via repository*.  

(But heck it's your project. And you could still upload it... if you like confusion.)

(And trust me, that *would* cause confusion.)


# diagram of our ⭐ BATTLE PLAN ⭐
![repoProject.png](repoProject.png)


# Layout of files in your web-hosted repository
Otherwise arrange the hierachy to exactly match what the XML-file inside your repo-zip belongs to. E.g.:
```
<<github.com/[yourName]/[repoName]>>   <--- or whatever web host you want
│
├── addons.xml                         <--- list of each addon's <addon>...</addon> blob
│                                             (from: [addon].zip > [addon] > addon.xml)
|                                             (note: this one is 'addonS', plural!!)
|
├── addons.xml.md5                     <--- literally any text inside
|                                             (if contents change, Kodi refreshes repo)
│
├── script.realdebrid                  <--- folder matching an addon's name (w/o version)
│   └── script.realdebrid-0.5.zip      <--- an addon your repo provides 
│
└── [addonType].[addonName]            <--- another addon (not your repo's addon!!)
    │
    └── [addonType].[addonName]-[version].zip
```


# Barebones "addon.xml" content for a "repository installer" addon
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<addon id="repository.jbees" name="[COLOR gold]Jbees Repository[/COLOR]" version="1.2.3" provider-name="JB">
    <extension point="xbmc.addon.repository" name="[COLOR gold]Jbees Repository[/COLOR]">
		<dir>
		<info compressed="false">https://raw.githubusercontent.com/jasonbuechler/jbees/master/addons.xml</info>
			           <checksum>https://raw.githubusercontent.com/jasonbuechler/jbees/master/addons.xml.md5</checksum>
			 <datadir zip="true">https://raw.githubusercontent.com/jasonbuechler/jbees/master/</datadir>
		</dir>
    </extension>
    <extension point="xbmc.addon.metadata">
		<summary lang="en">Jbees Repository</summary>
		<description lang="en">Jbees Repository: the repository of JB</description>
		<platform>all</platform>
		<news>[B]1.2.3[/B][CR]JB ftw!</news>
    </extension>
</addon>
```
