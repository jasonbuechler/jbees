# These files are what Kodi "looks at" (for *install-via-repo*)

Sooo... there is not much point in uploading your repository.whatever-1.2.3.zip (the zip of your own repo "addon") to the actual repo.

...because you'll *always* be adding your repo **via zip**.
And only after this repo addon is installed, can you then install **other** addons *via repository*.  

(But heck it's your project. And you could still upload it... if you like confusion.)

(And trust me, that *would* cause confusion.)

# Layout of the repo files
Otherwise arrange the hierachy to exactly match what the XML-file inside your repo-zip belongs to. E.g.:
```
(( github.com/[yourName]/[repoName] ))
│
├── addons.xml
│
├── addons.xml.md5           <--- literally any text inside
│
├── script.realdebrid        <--- an addon you wanna install
│   └── script.realdebrid-0.5.zip
│
└── [addonType].[addonName]  <--- not *your* addon!!
    └── [addonType].[addonName]-0.0.0.zip
```
