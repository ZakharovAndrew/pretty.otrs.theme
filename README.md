# Pretty OTRS SKIN

## Installation

In order to install the Pretty OTRS Skin, go to the Custom directory in your OTRS
deployment directory (e.g.: /opt/otrs/Custom)::

```
$ cd /opt/otrs/Custom
$ git clone https://github.com/ZakharovAndrew/pretty.otrs.theme
```

Edit install.sh and make sure OTRS_USER, OTRS_GROUP and OTRS_ROOT variables are set correctly for your environment, then::

```
$ sudo ./install.sh
```

**Log into OTRS system with the admin user, go to SysConfig Core::Web** and set:  
>  **Loader::Agent::DefaultSelectedSkin** to PrettyOTRS 
  
**then go to Frontend::Customer** and set:  
>  **Loader::Customer::SelectedSkin** to PrettyOTRS

In order to be able to use our own favicon.ico, we need to change **Frontend::ImagePath** to   <OTRS_CONFIG_Frontend::WebPath>skins/Agent/PrettyOTRS/img/

OTRS Theme:

To activate the theme in otrs, we need to go to SysConfig Core::Web and add our PrettyOTRS theme to Frontend::Themes and make it active.
To make our theme the default theme, we need to go to SysConfig Core and change the *DefaultTheme* setting to **PrettyOTRS** . This will apply our theme to all users that have not previously set the Theme preference in their user preferences.

If we want the theme default theme setting to override user's preferences, then we need to set our default theme on a host level *DefaultTheme::HostBased*.

## Other Installation
/opt/otrs/bin/otrs.Console.pl Maint::Config::Rebuild  
/opt/otrs/bin/otrs.Console.pl Maint::Cache::Delete  
/opt/otrs/bin/otrs.Console.pl Maint::Loader::CacheCleanup  
/opt/otrs/bin/otrs.Console.pl Maint::Loader::CacheGenerate  
