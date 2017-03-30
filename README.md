A UPS shipping module for CubeCart based on the AWSP shipping library.

---

## REQUIREMENTS

* [Cubecart](http://www.cubecart.com) v6 or higher: http://www.cubecart.com

* Database supporting 'length', 'height', and 'width' fields for products  
	See https://github.com/briansandall/v6/commits/product_dimensions

* [AWSP Shipping Library](https://bitbucket.org/briansandall/awsp-ship) v1.3 or higher:  https://bitbucket.org/briansandall/awsp-ship

## INSTALLATION
Before starting, make sure you meet all of the requirements listed above.

1. Add or update shippable inventory product dimensions; products with no dimensions provided will use weight-based shipping.

2. Remove the standard UPS shipping module if it is installed  
	(see below for co-installation instructions)

3. Place the AWSP shipping library in CubeCart's `/includes/lib/` directory

4. Place this folder and its contents in CubeCart's `/modules/shipping/` directory

5. Replace the `/Awsp/includes/autoloader.php` class with the `autoloader.php` file included with the module

6. Rename the `Awsp_UPS` folder to `UPS` (otherwise it appears to customers as 'Awsp UPS')

7. Enable the plugin and edit its settings from the Manage Plugins page of the CubeCart admin panel

8. (Optional) Delete `/Awsp/config.php` - settings are handled by the module via CubeCart's admin panel

9. (Optional) Delete example files in the root `/Awsp` directory

## OPTIONAL

In order for the 'Separate Packages by Manufacturer' setting to function, you need to
either install the AWSP MultiPackageProducts plugin OR import the code snippet located
in this module's `/snippets` directory.

## DUAL INSTALLATION

If you would like to have both the standard UPS and Awsp UPS modules installed at the
same time, e.g. for comparing rate results, you can do so by changing the following
prior to installing the Awsp UPS module:

1. Open `shipping.class.php` in a text editor; change the class name to `Awsp_UPS`

2. Open `admin/index.tpl` in a text editor; change `<div id="UPS">` to `<div id="Awsp_UPS">`

3. Follow the regular installation instructions, but skip steps 2 and 6.
