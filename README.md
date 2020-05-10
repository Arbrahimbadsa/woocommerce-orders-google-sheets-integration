# woocommerce-google-sheets-integration
This google sheet syncs order data from your WooCommerce store to Google sheets automatically. A free alternative to Zapier-WooCommerce order integration.

The sheet uses the WooCommerce Rest API v2 to connect to the WooCommerce store and sync the order data to the google sheet. The sheet will fetch order details like First Name, Last Name, Billing Address, Shipping address, Phone, Email, Price, Payment method, Items, Quantity  OrderId, Notes, Date, Refunds, Order key.

PS: If you are looking for an easy to setup advanced order integrations and features, please check out the zapier plugin for woo-commerce store <a href="https://goo.gl/8KepXA">here</a> or inbuilt reporting plugins <a href="https://goo.gl/spCPes">csv-export</a> or <a href="https://goo.gl/F8adgV">order-export</a> 

NOTE: Woocommerce REST API only supports website that has https enabled. If your website is not https, consider installing SSL certificate from https://www.freessl.com/ or your hosting provider. 

Below are the steps to set up the sheet:

# 1. Set up WooCommerce REST API in your WordPress website:

Steps can be found here: https://github.com/woocommerce/woocommerce/wiki/Getting-started-with-the-REST-API#generate-keys. You need to provide the API key and API secret generated from this step in the Google sheet.

# 2. Set up google sheets
If you know how to work with google app script, copy the code from .gs file to your script editor and set up your google sheet in the format of the template. Alternatively click on the google sheets link: https://goo.gl/r8qnMJ

The sheet is view only - request an edit permission - The sheet is kept as read-only so that no one makes changes in the original sheet / accidentally enter his or her API credentials in this sheet accessible to the public. YOU SHOULD ALWAYS KEEP YOUR API CREDENTIALS as secret.

IMPORTANT: Once you get the edit permission, go to File > Make a copy and save the copy to your google drive. Now, this copy can be accessed only by you. Do not make any modifications / enter your API credentials in the original sheet as anyone can see the data in the public sheet.

# 3. Set up your google sheet

Enter your store URL (Should be in the format https://yourstore.com - notice that only https is supported), API Key, API secret, Date in the sheet and click on the Update button. The google sheets will ask for permission for the app to run. The sheet requires permission to 1. View and manage your spreadsheets in Google Drive, 2. Connect to an external service. It will show the app as unverified - This is because it is trying to access an external URL - the site you have given in the sheet in this case. Click on Advanced and proceed. Please feel free to take a look at the code in the script editor to see what the sheet is doing in case you are in doubt. 
If everything is set up correctly, the sheet will update with the order details from your woo-commerce store.


# 4. Set up automatic order sync 

The sheet can be manually updated on click of the update button. If you want the sheet to update automatically, you can set up a trigger for the sheet. 
Click on Tools > Script Editor. A new window will pop up. 

On that page, click on Edit > Current Projects Trigger. In the pop-up, give the name 'start_syncv2' in the first field and time driven in the second field. You can set the update frequency also here. There is an option to update sheet daily, hourly, monthly and even on opening the sheet.

'start_syncv2' is the function that invokes the script that syncs data between the google sheets and your site. Setting a trigger will trigger this process periodically based on the preferences you set.

If you face any issues or have any suggestions to improve this woocommerce orders google sheets integration tool, create a ticket at https://github.com/mithunmanohar/woocommerce-orders-google-sheets-integration/issues

Version V2 of the tool has additional features. If  you want to try out the v1 of this tool, check out https://goo.gl/jAqPMz

Contributors to this project: @mithunmanohar, @petrfaitl

If you find this tool useful, you can consider buying me a coffee !

<a href="https://www.buymeacoffee.com/68smoil" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
