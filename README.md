# IssuesSolutionsWorkflow-4ahmnm

Was kann schiefgehen? Vieles!
Hier eine Sammlung mit Lösungen zu Stolpersteinen.

Sammlung:

## Intellisense is not working in the right way, Visual Studio 2019
Hier gibt es mehrere Ansätze, da es mehrere Ursachen geben kann.

1) Restart Unity & Visual Studio
2) Ensure Visual Studio is External Editor: Edit > Preferences > External Tools
3) Check Unity dev tools installed in Visual Studio: Tools > Get Tools and Features
4) Check Unity dev tools installed in Visual Studio: Tools > Extensions> Manage Extensions 
5) Check script included in project (Visual Studio): Solution Explorer
6) Try updatingVisual Studio

## SteamVR files tracked although ingored in .gitignore

.gitignore updaten: folgende Änderung im .gitignore (befindet sich wahrscheinlich am Ende des .gitignore)

```
# Asset meta data should only be ignored when the corresponding asset is also ignored
!/[Aa]ssets/**/*.meta
```
1) vor diesen Block schreiben!
```
/[Aa]ssets/SteamVR/
/[Aa]ssets/SteamVR_Input/
/[Aa]ssets/SteamVR_Resources/
/[Aa]ssets/StreamingAssets/
/[Aa]ssets/ResonanceAudio/

Assets/ResonanceAudio.meta
Assets/SteamVR.meta
Assets/SteamVR_Input.meta
Assets/SteamVR_Resources.meta
Assets/StreamingAssets.meta
```
2) an jeder anderen Stelle entfernen
3) git commit -am "update gitignore ignore .meta files"
4) alles bezüglich SteamVR nicht mehr tracken

```
Untrack files already added to git repo:
git rm -r --cached fileToUntrack.meta

rm is the remove command
-r will allow recursive removal
--cached will only remove files from the index. Your files will still be there.
```

## I've no trust in git/GitHub because I'm not sure if my last changes are online!!
Meine letzte lokale Änderung habe ich mit einer commit message zum lokalen Repository hinzugefühgt. Z.B.: git commit -m "add cubes in scene".
Wenn ich meine Arbeit beende und ich möchte, dass die Änderungen online verfügbar sind, muss ich git push ausführen und alle commits inkl. dem letzten werden mit dem
remote Repository synchronisiert. D.h. einfach die commits lokal mit den commits online vergleichen (durch schauen) und ich kann mir sicher sein, dass meine Änderungen online sind ;).
