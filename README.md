# Domains-Reseller-whmcs

Domains Reseller module for WHMCS to integrate API functionality for resellers directly into their WHMCS installations. Simplifies the automation of registering, transferring, and renewing domain name registrations. RAD WEB HOSTING account is required.

After account creation, users gain access to the Domain API by siging up for a Domain Reseller account.

## About

This is a custom WHMCS module built for our resellers to enable remote Domain Registration and management of RAD WEB HOSTING domains.

## Installation

1. Download the module via the following [link](https://github.com/Rad-Web-Hosting/RadWebHosting/releases/latest)
2. Copy the `RadWebHosting` directory into the respective WHMCS directory in your WHMCS setup: `/whmcs/modules/registrars/`
3. In WHMCS Admin area, navigate to Setup -&gt; Products/Services -&gt; Domain Registrars and activate the `RadWebHosting` registrar
4. Enter your API username and API secret. These can be obtained via your [Hosting Dashboard](https://radwebhosting.com/client_area/clientarea.php).
5. Choose to pay via credit card. You must have one on file. This will ensure domains are registered/renewed when your WHMCS requests. If you do not want to use a credit card, you must have a credit balance on your account with RAD WEB HOSTING.
6. Add the following code to /includes/additionaldomainfields.php if using WHMCS v6 or add to /resources/domains/additionalfields.php if using WHMCS v7:

   ```text
   /********************************************* RadWebHosting Domain Additional Fields ********************************************/
   if(!defined('DS'))
    define('DS',DIRECTORY_SEPARATOR);
   $filename = ROOTDIR.DS.'modules'.DS.'registrars'.DS.'RadWebHosting'.DS.'RadWebHosting.php';
   if(file_exists($filename)){
    require_once ($filename);
    $fields = RadWebHosting_GetDomainFields();
    if(is_array($fields))
        $additionaldomainfields = $fields;     
   }
   /********************************************* End RadWebHosting Domain Additional Fields *****************************************/
   ```

## Help

If you have any questions or problems please submit a [Domain Support Ticket](https://radwebhosting.com/client_area/submitticket.php?step=2&deptid=10).

## Bugs

If you discover any bugs or issues with this module, please notify our staff via the [24/7 Helpdesk](https://radwebhosting.com/client_area/submitticket.php).

## License

This project is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).

