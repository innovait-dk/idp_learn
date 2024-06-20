
Requirements:

1. The ArchitectureItem "Security" is added to the designer (if not the appextension will not be shown)
2. Some operations (and roles) has been defined (you can keep add/delete operation/roles in the designer)

To implement Security Extension:

1. Add AppExtension: Choose on of the "Security" AppExtension
2. Follow the instructions in the readme.txt

When you have implemented the Security AppExtension there are created 7 SQL tables in the database and the UI for maintaining these tables is added either to your Ribbon og OutlookBar.

When you "Create code" in the designer (in "Security") there are now also generated a "InsertData-sqlscript.sql" in the Security-folder in the data project.
If you have defined roles and operations in the designer, these are in the sql-script. So if you run the sql-script the roles and operations are inserted into the database.

Before the Security AppExtension you needed to add the current user to roles in code [see here](../../tutorials/Security/addusertoroles.md) in the `ApplicationSecurityBuilder`.

The Security AppExtension files out the Roles with data from the database.


