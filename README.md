ezrpg-1.0.x-modulemanager v1.0 (MM1.0)
=========================

My Module Manager for ezRPG 1.0.x

Example of a Module:
https://github.com/uaktags/ezrpg-module-mailbox

Compatibility:
Only with 1.0.x versions
See https://github.com/ezrpg/ezrpg for commits

Installation:
-Copy Directories to Root of ezRPG install.
-Login as Admin
-Navigate to ezrpg/admin/index.php?mod=Plugins
-You're Done!

Basic Use
========
-Navigate to ezrpg/admin/index.php?mod=Plugins
-Click Add New Plugins
-Click Upload Plugin and select module's zip
-When complete either Install the new Module or Click Go Back

Building a Module to work with MM1.0
====================================
Modules are already set up to be dropped in and ran,
so MM1.0 is only trying to streamline the tedious tasks
of copying files everywhere and running needed commands.

Make sure if your Module uses a new DB table, that you create
a Install Action of some kind. MM1.0 only handles the FileSystem
Operations of moving the files, organizing their options, the
rest is still on the Module's developer (you) to make.

File Structure should be as follows:
{ZIP}
-Module.xml
-modules/TestModule/*
-smarty/templates/*

--------------------------
|The XML file is MANDATORY|
--------------------------

XML Structure :

<?xml version="1.0" encoding="UTF-8"?>
<ezRPG_Module>
   <Module>
      <Name>Test Module</Name>
      <Version>1.0</Version>
      <Author>UAKTags</Author>
    <AuthorSite>http://ezrpgproject.net</AuthorSite>
	  <Desc>Description Goes Here</Desc>
	  <InstallCode>index.php?mod=TestModule&amp;act=install</InstallCode>
   </Module>
</ezRPG_Module>


Install code points to the Install Action in your module. Make sure &amp; replaces your '&'
