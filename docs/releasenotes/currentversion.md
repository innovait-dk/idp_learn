## 2024.6.17

The first AppExtensions has landed. This version includes the following AppExtensions:

-	[Logging](../appextensions/log/index.md)
-	[Security](../appextensions/security/index.md)

All AppExtensions are created with IDP and are fully opensourced (for customers). And yes, you can make your own AppExtensions.

### Designer

- Database: The connectionstring is no longer in the iad-file. It uses the connectionstring in the app.config. [See here](../guide//elements/database.md)
- UI Designer now supports drag-n-drop for fields between groups.
- Checkboxlist, radiobuttonlist and comboxes has a “DependentField” property so for example if you have two comboboxes and you want the second combox’s items to be depended on the selection in the first combox then you should use this new property.
- Radiobutton and Checkboxlist’s orientation can be configured with horizontal or vertical.
- Various bug fixes and optimizations

### Framework

- **Breaking change** Implemented ApplicationBuilder which are used in the app.xaml.cs to load services, appextension and so on. 
- New Revision UI
- Added support for Swedish and Norwegian culture in the UI (beside English and Danish).
- Various bug fixes and optimizations

### Breaking Changes

Upgrade from 2024.2.57:

Backup your app.xaml and app.xaml.cs if you have made custom changes.

Run code-task “AppBase” (which will replace app.xaml/app.xaml.cs)


