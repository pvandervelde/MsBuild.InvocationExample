# MsBuild loading of dynamically generated items

This repository demonstrates two methods of 'reloading' item group information. The different directories contain MsBuild
scripts which print a list of items. The expected outputs are

    First - 1
    Second - 2

For the first stage, and then

    First - 1
    Second - 2
    Third - 3
    Fourth - 4

For the second stage

* **no-reload** The item groups are written to a project file and then imported. Because MsBuild does not reload imports
  the output the second stage prints exactly what the first stage prints.
* **dynamic-itemgroups** The item groups are dynamically loaded from a file.
* **separate-instances** The projects are executed by different MsBuild instances.

To execute any of the tests navigate to the folder of the sample and run

    msbuild.exe start.msbuild
