# Jetpack WHMCS Addon Module
The Jetpack [WHMCS addon module](https://developers.whmcs.com/addon-modules/) is intended to assist Jetpack hosting partners who utilize WHMCS in creating Jetpack products and product addons within WHMCS. This module requires the [Jetpack provisioning module](https://github.com/Automattic/jetpack-whmcs-provisioning-module) to be installed and available before use.

## Getting Started
If the provisioning module has not yet be installed or you do not yet have a Jetpack partner account please begin with the instructions available with the [provisioning module](https://github.com/Automattic/jetpack-whmcs-provisioning-module)

## Setup
To install this module clone this repository in a directory named `jetpack` in the `modules/addons` directory of your WHMCS installation. Once the module has been made available in the addons directory, visit the WHMCS addon modules configuration page. The Jetpack addon module will be shown in the list of available modules and can be activated from there. On activation the module will attempt 2 actions.
- Creating the `jetpack_product_licenses` database table if this table does not already exist. This database table is where end user orders and their corresponding Jetpack licenses are stored. If a product has previously been created that utilizes the Jetpack WHMCS provisioning module this table will already exist.
- Creating the `Jetpack Products` product group within WHMCS. Products added using the addon module will be added to this product group by default.

## Configuration
The module does support a configuration option to store the Jetpack Partner API token. This is the token used to make API calls when creating, revoking and attaching licenses with the Jetpack provisioning module. If the option is saved in the addon module it will be made available when creating products.

## Usage
Once installed and activated the module can be accessed from the Addons menu option in the WHMCS admin. The module currently provides options for the following:
- Creating a new WHMCS product type for a Jetpack Product.
- Creating a new WHMCS product addon type for a Jetpack Product.
- Updating your API key for all products that use the provisioning module.

Products created using the Jetpack addon module are set as hidden by default as pricing and all configuration options are not set. The product or product addon will also need to have it's URL set in the WHMCS product management before changes made can be saved.