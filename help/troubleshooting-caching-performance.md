---
title: Troubleshooting caching performance  
seo-title: Troubleshooting caching performance  
description: Troubleshooting caching performance  
seo-description: Troubleshooting caching performance  
contentOwner: khsingh

---

# Caching performance {#caching-performance}

The following sections describes some issues that you can face while configuring or using Adaptive Forms cache in a Cloud Service environment:

## Some adaptive forms containing images or videos are not automatically invalidated from dispatcher cache {#images-videos-not-invalidated}

When you select and add images or videos via asset browser to an adaptive form and these images and videos are edited in Assets editor, adaptive forms containing such images are not invalidated from dispatcher cache automatically.

To resolve the issue, after publishing the images and video, explicitly unpublish and publish the adaptive forms that reference these assets. 

## Some adaptive forms containing content fragment or experience fragments are not automatically invalidated from dispatcher cache {#content-fragments-experience fragments-not-invalidated}

When you add a content fragment or an experience fragment to an adaptive form and these assets are independently edited and published, adaptive forms containing such assets not invalidated from dispatcher cache automatically.

To resolve the issue, after publishing updated content fragment or experience fragment, explicitly unpublish and publish the adaptive forms that use these assets. 

## Only first instance of adaptive forms is cached {#only-first-instance-cached}

When the adaptive form URL does not contain any localization information, and the Use Browser Locale option in configuration manager is enabled, a localized version of the adaptive form is served and an instance of the adaptive form, based on the first request (browser locale requested), is cached and delivered to every subsequent user. 

Perform the following steps to resolve the issue:

1. Open your AEM project.
1. Open the dispatcher/scr/conf.d/rewrites/rewrite.rules for editing. 
1. Open the conf.d/httpd-dispatcher.conf or any other configuration file configured to load at runtime.
1. Add the following code to your file and save it. It is a sample code modify it to suit your environment.

```shellscript

    # Handle actual URL convention (just pass through)
    RewriteRule "^/content/forms/af/(.*)[.](.*).html$" "/content/forms/af/$1.$2.html" [PT]
    
    # Handle selector-based redirection based on browser language
    <VirtualHost *:80>
            # Handle actual URL convention (just pass through)
    RewriteRule "^/content/forms/af/(.*)[.](.*).html$" "/content/forms/af/$1.$2.html" [PT]

    # Handle selector based redirection basded on browser language
    # The Rewrite Condition is looking for the Accept-Language header and if found takes the first two character which most likely will be the desired language selector.
    RewriteCond %{HTTP:Accept-Language} ^(..).*$ [NC]
    RewriteRule "^/content/forms/af/(.*).html$" "/content/forms/af/$1.%1.html" [R]
    RewriteRule "^/content/forms/af/(.*).html$" "/content/forms/af/$1.%1.html" [R]

```

## CDN caching stops working after 300 seconds {#CDN-caching-stops-working-after-300-seconds}

CDN caching stops working after 300 seconds and all the requests to cache on CDN are re-directed to dispatcher. 

To resolve the issue, set the age header to 0:
1. Create a new file at `src\conf.d\available_vhosts`
1. Add the following to file to set the age header

```shellscript
    <IfModule mod_headers.c>
            Header add X-Vhost "publish"
            Header set age 0
    </IfModule>
```

1. Save and close the file.
1. Modify the softlink for `src\conf.d\enabled_vhosts\default.vhost` to point to new file. 


