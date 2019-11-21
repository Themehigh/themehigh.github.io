---
layout: post
title:  Email Customizer for WooCommerce
categories: jekyll update
---

###### Themehigh Email Customizer plugin for WooCommerce - Design the way you love !!
[FREE](https://wordpress.org/plugins/email-customizer-for-woocommerce/) | [PREMIUM](https://www.themehigh.com/product/woocommerce-email-customizer/) | [DEMO](https://flydemos.com/wecm/wp-admin)

## Quick Links
{:.no_toc}

* Table of content. Use {:.no_toc} to escape some heading
{:toc}
   
### ARE ALL EMAILS CUSTOMIZABLE ?
   
Email notifications for the default WooCommerce order statuses are customizable. Custom email order status created by 3rd party plugin or using custom coding is not supported at the moment. 
The list of customizable email notifications are listed below.

1. Admin New Order Email	
2. Admin Cancelled Order Email	
3. Admin Failed Order Email	
4. Customer Completed Order	
5. Customer On Hold Order Email	
6. Customer Processing Order	Email
7. Customer Refund Order	Email
8. Customer invoice / Order details	Email
9. Customer Note	Email
10. Reset Password Email
11. New Account Email
   

### EMAILS ARE NOT SEND/DELIVERED ?
 
if emails from the Email Customizer plugin are not send or is not delivered, then please check the following.

1. Check if any SMTP plugin is active. If yes check whether the SMTP plugin is configured correctly. Try placing Test mail from the SMTP plugin to rule out issues.
2. If no SMTP plugins are active, then try any SMTP plugin like [Easy WP SMTP](https://en-gb.wordpress.org/plugins/easy-wp-smtp/) and configure the settings accordingly. 
3. Use an email logging plugin like [WP Mail Logging](https://en-gb.wordpress.org/plugins/wp-mail-logging/) which will log all outgoing mails so you can see what is being sent. Place a test order to see if order emails are logged in WP Mail Logging settings (dashboard -> WP Mail Log). If emails are not logged, it could be a plugin or theme conflict.
4. Deactivate the Email Customizer plugin and confirm whether WooCommerce Default emails are delivered. Continue this process by deactivating other plugins till email is sent or delivered.
5. If none of the above steps solve the issue, please contact Email Customizer support team


### BROKEN IMAGES IN EMAILS
   
   If the image in email send using Email Customizer plugin is broken, confirm whether the image is publicly accessible. Also ensure your images are inserted with a full URL including the protocol.     
   

### CUSTOMER NOTE IN EMAIL TEMPLATE


There are situations where you have to show `Customer Note` in the email template. By default, Customer Note is not displayed in the Email Customizer templates. In order to show customer note, you have to use the placeholder `{th_customer_note}` where necessary.

Follow the steps to display customer note.
1. Click on `Add element` button in the right sidebar
2. Choose `Text` from the list that appears.
3. Click on  `Edit` (pencil icon) near the Text element.
4. Type the placeholder `{th_customer_note}` to display customer note.  

You can use the available placeholders to place dynamic datas.
The available placeholders are **{th_customer_name}**, **{th_billing_phone}**, **{th_order_id}**, **{th_order_url}**, **{th_billing_email}**, **{th_site_url}**, **{th_site_name}**, **{th_order_completed_date}**, **{th_order_created_date}**, **{th_checkout_payment_url}**, **{th_payment_method}**, **{th_customer_note}**, **{th_user_login}**, **{th_user_pass}**, **{th_account_area_url}**, **{th_reset_password_url}**.


### USING WOOCOMMERCE HOOKS IN TEMPALTE

WooCommerce have provided a number of hooks in the email template to pass data. Third party plugins or themes can use these hooks to pass data to the email templates. 

Email Customizer has the option to add or remove these WooCommerce Hooks. 

1. Click on `Add Element` button inside a column.
2. From the list that appears on sidebar, navigate and click on `WooCommerce Hooks` section.
3. Click on the hook necessary. Data will be replaced on placing an order.  
   

### DOWNLOADABLE PRODUCTS IN EMAIL TEMPLATE

Email Customzier plugin have option to show `Downloadable Product` data in email template. For that,

1. Click on `Add Element` button inside a column.
2. From the list that appears on sidebar, navigate and click on `WooCommerce Elements` section.
3. Click on `Downloadable Product` tile.   
   

###  WOOCOMMERCE ELEMENTS CUSTOMIZABLE ??

WooCommerce passes Order table, Billing Details, Shipping Details etc to hooks in the email template. So when the appropriate hooks are inserted into the email templates, these details are displayed in the email. These blocks are not customizable.

But email customizer has option to customize these WooCommerce Elements (  Header, Order Table, Customer Details, Billing Details, and Shipping Details).

1. Click on `Add Element` button inside a column.
2. From the list that appears on sidebar, navigate and click on `WooCommerce Elements` section.
3. You can see the list of WooCommerce elements that can be customized (Downloadable product is not customizable now).   
   

### USING CUSTOM HOOK

Email customizer has a special feature called `Custom Hook`. The `Custom Hook` is an action hook, which can be used to add dynamic contents to the email template. You can use custom hook to show Order meta fields, Display shortcodes from third party plugins in Email,  Result based on checkout field values or on the email status like processing, on hold etc.

You can use the `Custom Hook` as follows

1. Click on `Add Element` button inside a column.
2. From the list that appears on sidebar, navigate and click on `WooCommerce Hooks` section.
3. Click on `Custom Hook` tile. You can see `{custom_hook_name}` added to the builder.
4. Click on the `Edit` button (pencil icon) near the `Custom Hook` entry in the right sidebar
5. Enter a unique name for the hook (eg: **themehigh_template_hook** ). Using an existing hook name can cause unexpected errors.
6. Use the hook name provided to write a function in the active theme/ child theme functions.php. 

	
		function themehigh_template_hook_callback( $order, $email ){
			// Your content here
		}
		add_action('themehigh_template_hook', 'themehigh_template_hook_callback', 10, 2);    

   

### THEMEHIGH CHECKOUT FIELD EDITOR PLUGIN INTEGRATION
   
The plugin [Themehigh Checkout Field Editor for WooCommerce](https://www.themehigh.com/product/woocommerce-checkout-field-editor-pro/) is compatible with email customizer. The fields created using Checkout field editor plugin is passed conditionally to default woocommerce hooks
**woocommerce_email_order_meta** or **woocommerce_email_customer_details**

Email customizer have option to show the checkout fields anywhere in the template using a shortcode `[WCFE name='field_name' label='field_label']`

You can use the shortcode `[WCFE name="field_name"]` to show only the value without label.

Eg: Consider you have created a field `test_field` in the checkout field editor plugin. In order to show the field in the email template at a particular position, you can use the above shortcode as `[WCFE name='test_field' label='Test Field']`.

N.B: Remember not to use double qoutes in the shortcode. 


