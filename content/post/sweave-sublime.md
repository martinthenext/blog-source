---
Title: R Sweave Sublime Text build system
Date: 2013-05-23
Tags: ['r']
---

To be able to edit R Sweave files in Sublime and render them to pdf's with one click you can do the following.

*1. Create a batch file*

This `run-sweave.bat` file will take your Snw file as an argument and output a pdf to the same directory. It will also call Adobe Reader to preview the pdf, don't forget to change the last part to your actual Adobe Reader path.

    @echo off
    set filename=%1
    set name=%filename:~0,-4%
    R CMD Sweave --encoding="utf-8" %name%.Snw
    pdflatex %name%.tex
    "C:\Program Files (x86)\Adobe\Reader 11.0\Reader\AcroRd32.exe" %name%.pdf

*2. Link this batch file in a build system*

Create a new build system in Sublime with a simple config:

    {
      "cmd": ["C:/run-sweave.bat", "$file"]
    }

The location of the file, of course, should be altered as well.
