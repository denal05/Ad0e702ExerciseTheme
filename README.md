# Ad0e702ExerciseTheme
An AD0-E702 certification exercise module: Create a theme that customizes the Magento UI and overrides certain files.  

The theme preview image was designed using [Canva](https://www.canva.com/).  

Make sure to switch to this theme in Admin > Content > Config > Default Store View > Edit > Applied Theme: AD0-E702 Exercise Theme > Save Configuration

1. The first exercise is to override the Onepage Success template.

Per https://magento.stackexchange.com/a/326297
```php
In Magento 2.4.1 there are two success.phtml templates:
module-checkout/view/frontend/templates/success.phtml
module-inventory-in-store-pickup-frontend/view/frontend/templates/success.phtml
In my case, I had to override the second one in app/design/frontend/Vendor/Theme/Magento_InventoryInStorePickupFrontend/templates/success.phtml
```

After the modifications, run ``` bin/magento s:s:d -f -j3 ```

Overrode a Knockout.JS HTML template in Magento_Checkout/web/template/shipping-address/shipping-method-item.html
For each change of this template the following steps are required to see the changes:  
1. ```rm pub/static/frontend/Denal05/Ad0e702ExerciseTheme/en_US/Magento_Checkout/template/shipping-address/shipping-method-item.html```
2. ```bin/magento s:s:d -f -j3```
3. ```bin/magento c:f```


Overrode Magento/luma theme LESS files and changed the background color in web/css/source/_variables.less  
Per https://developer.adobe.com/commerce/frontend-core/guide/css/preprocess/#server-side-less-compilation  

> In server-side Less compilation mode, to have your changes applied, you need to do the following:  
> 1. Clear pub/static/frontend/Vendor/theme/locale by deleting the directory in the file system (excluding .htaccess).  
```rm -rf pub/static/frontend/Denal05/Ad0e702ExerciseTheme/en_US/*```
> 2. Clear the var/cache and var/view_preprocessed directories by deleting the directory in the file system. (if they already existed there).  
```rm -rf var/cache/*```
```rm -rf var/view_preprocessed/*```
> 3. Trigger static files compilation and publication.  
```bin/magento s:s:d -f -j3```
