

Web site: http://www.nirsoft.net


Description
===========

RunAsDate is a small utility that allows you to run a program in the date
and time that you specify. This utility doesn't change the current system
date and time of your computer, but it only injects the date/time that
you specify into the desired application.
You can run multiple applications simultaneously, each application works
with different date and time, while the real date/time of your system
continues to run normally.



How does it work ?
==================

RunAsDate intercepts the kernel API calls that returns the current date
and time (GetSystemTime, GetLocalTime, GetSystemTimeAsFileTime,
NtQuerySystemTime, GetSystemTimePreciseAsFileTime), and replaces the
current date/time with the date/time that you specify.





Using RunAsDate
===============

RunAsDate doesn't require any installation process or additional DLL
files. In order to start using it, simply copy the executable file
(RunAsDate.exe) to any folder you like, and run it.
In the main window of RunAsDate, select the desired date and time and the
application that you want to run. Optionally, you can also specify the
command-line parameters to run the program. Press the "Run" button to
start the application with the specified date/time.



Immediate Mode
==============

In versions prior to 1.03, RunAsDate always waited until the kernel was
fully loaded, and only then injected the desired date/time. This mean
that some programs that get the date/time im very early stage, received
the real current date/time, instead of the fake date/time of RunAsDate.
Starting from version 1.03, when the 'Immediate Mode' is turned on,
RunAsDate inject the date/time immediately when the process starts,
without waiting to the kernel loading. However, this mode can also cause
troubles to some applications, especially if they were written in .NET

If executing an application from RunAsDate cause it to crash, you should
turn off the 'Immediate Mode'.



Using RunAsDate from Command-Line
=================================

You can also use RunAsDate from command-line, with the following syntax:
RunAsDate.exe {/immediate} {/movetime} {/startin [folder]} {/returntime
[seconds] } [dd\mm\yyyy] {hh:mm:ss} [Program to run] {Program parameters}

Examples:
RunAsDate.exe 22\10\2002 12:35:22 "C:\Program Files\Microsoft
Office\OFFICE11\OUTLOOK.EXE"
RunAsDate.exe 14\02\2005 "c:\temp\myprogram.exe" param1 param2
RunAsDate.exe /movetime 11\08\2004 16:21:42 "C:\Program Files\Microsoft
Office\OFFICE11\OUTLOOK.EXE"
RunAsDate.exe /movetime /returntime 15 10\12\2001 11:41:26
"c:\temp\myprogram.exe"
RunAsDate.exe Hours:-10 "C:\Program Files\Microsoft
Office\OFFICE11\OUTLOOK.EXE"



RunAsDate Limitations
=====================


* RunAsDate will not affect applications that take the current
  date/time from another source. For example: application that loads the
  current date from remote server.









