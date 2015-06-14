# cache-source-control
The simplest source control for Caché Studio

Setup.
Import SourceControl.cls.xml in target namespace.
Open Management Portal and set in Configuration/Additional Settings/Source Control/ Util.SourceControl as source control class for the namespace.
[Screenshot](https://www.dropbox.com/s/016ld9l7rl9f1r7/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%88%D0%BE%D1%82%202015-06-14%2000.26.50.png?dl=0)

Open Util.SourceControl in Studio and set the defaults: temp directory, temp global.

Go to cterm and run d ##class(Util.SourceControl).SetUp()
It will export all the classes to ..#Folder with /folder/cls/package/class.xml manner.

During your coding process it will export class from studio after every successful compilation.

..#ExpMode=1 - will generate class.cls.xml instead of class.xml - it is compatible with cache-tort-git.

DFI files (pivots and dashboards) will be exported as well.

It is very simple tool so pull requests are very welcomed.
