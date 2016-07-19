# cache-source-control
The simplest source control for Caché Studio

Setup.
Import SourceControl.cls.xml in target namespace.
Open Management Portal and set in Configuration/Additional Settings/Source Control/ Util.SourceControl as source control class for the namespace.
[Screenshot](https://cloud.githubusercontent.com/assets/14019396/16948872/e1667516-4dbf-11e6-85b5-632cffdf2601.PNG)


Open the terminal and run "do ##class(Util.SourceControl).Init()"
It will export all the classes to the specified folder. 
The source control can work in three modes(XML files, new XML files(compatible with cache-tort-git), UDL)


Parameters to adjust:
-ExpMode: number
    0 - export in classname.xml 
    1 - export in classname.cls.xml (compatible with cache-tort-git)
    2 - export in classname.cls (udl format)

-SourceFolder: string - specifies where exported files should be stored

-RefreshTime: number - specifies the frequency of checking for new files in the SourceFolder(in seconds)


File hierarchy: 
1) XML:

/namespace
    /cls
        /PackageName
            Classname.xml
    /mac
        Routine.xml
    /int
        SomeFile.xml
    /dfi 
        SomeAnotherFile.xml

2) New XML files(compatible with cache-tort-git):
/namespace
    /cls
        /PackageName
            Classname.cls.xml
    /mac
        Routine.mac.xml
    /int
        SomeFile.int.xml
    /dfi 
        SomeAnotherFile.dfi.xml

3) UDL:
/namespace
    /cls
        /PackageName
            Classname.cls
    /mac
        Routine.mac
    /int
        SomeFile.int
    /dfi 
        SomeAnotherFile.dfi


During your coding process it will export class from studio after every successful compilation.
Moreover, the files that are added from an external source will be automatically imported into a project.


Sample project that shows the structure of files in UDL format: https://github.com/RustamIbragimov/SourceControlTest


It is very simple tool so pull requests are very welcomed.