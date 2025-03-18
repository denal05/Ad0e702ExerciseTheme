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
