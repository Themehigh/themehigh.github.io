---
layout: post
title:  Knowledge base - Email Customizer for WooCommerce
categories: jekyll update
---

###### Themehigh Email Customizer plugin for WooCommerce - Design the way you love !!
[FREE](https://wordpress.org/plugins/email-customizer-for-woocommerce/) | [PREMIUM](https://www.themehigh.com/product/woocommerce-email-customizer/) | [DEMO](https://flydemos.com/wecm/wp-admin) | [DOCS](https://www.themehigh.com/help-guides/woocommerce-email-customizer/)

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

You can use the available placeholders to place dynamic datas. For more placeholders, [see](#placeholders-in-email-template).

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
   
The plugin [Themehigh Checkout Field Editor for WooCommerce](https://www.themehigh.com/product/woocommerce-checkout-field-editor-pro/) is compatible with email customizer. The fields created using Checkout field editor plugin is passed conditionally to default woocommerce hooks `woocommerce_email_order_meta` or `woocommerce_email_customer_details`.

Email customizer have option to show the checkout fields anywhere in the template using a shortcode `[WCFE name='field_name' label='field_label']`

You can use the shortcode `[WCFE name='field_name']` to show only the value without label.

Eg: Consider you have created a field `test_field` in the checkout field editor plugin. In order to show the field in the email template at a particular position, you can use the above shortcode as `[WCFE name='test_field' label='Test Field']`.

N.B: Remember not to use double qoutes in the shortcode.
   

### DUPLICATING EMAIL TEMPLATES

How can i make the copy of a template that i have created ? Do i have to start from scratch again ?
No. You don't have to do this. Making a copy of any template you have created is so easy. Just rename and save the template. You will have a new copy of template you were editing without losing the old one. Follow the below steps to duplicate the email template.  
1. Go to Templates submenu(If you're not editing a template or want to make duplicate of saved template)
2. Goto `Edit Template` section and choose the template you wish to duplicate. Then click `Edit`.
3. From the template that is loaded in builder, give another name to the template in the top left textbox.
4. click `Save` button and your template is duplicated.


### PLACEHOLDERS IN EMAIL TEMPLATE

Placeholders can be used in email template to replace dynamic contents. Our email customizer plugin provides a number of placeholders, which you can insert in your template, to display dynamic data.
The available placeholders are   

**{th_customer_name}**  -  Displays the customer name   
**{th_billing_phone}**  -  Displays the billing phone number   
**{th_billing_email}**  -  Displays the billing email   
**{th_order_id}**	    -  Displays the Order ID   
**{th_order_url}**		-  Displays the url to the Order in My account page   
**{th_site_url}**		-  Displays the url to the site   
**{th_site_name}**		-  Displays the name of the site   
**{th_order_completed_date}**	-  Displays the Order completed date   
**{th_order_created_date}**		-  Displays the Order created date   
**{th_checkout_payment_url}**	-  Displays the payment url   
**{th_payment_method}**			-  Displays the payment method name   
**{th_customer_note}**			-  Displays the customer note   
**{th_user_login}**				-  Displays the username   
**{th_user_pass}**				-  Displays the password   
**{th_account_area_url}**		-  Displays the url to my account page   
**{th_reset_password_url}**   	-  Displays url to reset password

The above placeholders can be used without the *th_* prefix from version 2.0.5

New list of placeholders are available from version 2.0.5

##### Site Related   
**{site_url}**  	-  Displays the url to the site   
**{site_name}** 	-  Displays the name of the site   

##### Order Related   
**{order_id}**				-  Displays the Order ID   
**{order_number}**          -  Displays the order number. By default, order ID (v3.0.0)   
**{order_url}**				-  Displays the url to the Order in My account page   
**{order_completed_date}**	-  Displays the Order completed date   
**{order_created_date}**	-  Displays the Order created date   
**{order_total}**			-  Displays the order total   
**{order_formatted_total}** -  Displays the formatted order total   

##### Billing Fields   
**{billing_first_name}**	-  Displays the billing first name in billing address   
**{billing_last_name}**    	-  Displays the billing last name   
**{billing_company}**		-  Displays the billing company name   
**{billing_country}**		-  Displays the biling country name   
**{billing_address_1}**		-  Displays the billing address1   
**{billing_address_2}**		-  Displays the billing address2  
**{billing_city}**			-  Displays the billing city   
**{billing_state}**			-  Displays the billing state   
**{billing_postcode}**		-  Displays the billing postcode   
**{billing_phone}**			-  Displays the billing phone   
**{billing_email}**			-  Displays the billing email   

##### Shipping Fields   
**{shipping_first_name}**	-  Displays the shipping first name   
**{shipping_last_name}**	-  Displays the shipping last name   
**{shipping_company}**		-  Displays the shipping company name   
**{shipping_country}**		-  Displays the shipping country name   
**{shipping_address_1}**	-  Displays the shipping address1   
**{shipping_address_2}**	-  Displays the shipping address2   
**{shipping_city}**			-  Displays the shipping city name   
**{shipping_state}**		-  Displays the shipping state name   
**{shipping_postcode}**		-  Displays the shipping postcode   

##### Account Related   
**{user_login}**			-  Displays the username   
**{user_pass}**				-  Displays the password   
**{user_email}**            -  Displays the user email (v3.0.0)   
**{account_area_url}** 		-  Displays the url to my account page   
**{reset_password_url}** 	-  Displays url to reset password   
**{account_order_url}**     -  Displays url to my account orders page (v3.0.0)   
 
##### Other   
**{customer_name}** 		-  Displays the first name of customer   
**{customer_full_name}**	-  Displays the full name of customer   
**{customer_note}**			-  Displays the customer note   
**{checkout_payment_url}**	-  Displays the payment url   
**{shipping_method}**		-  Displays the shipping method   
**{payment_method}**		-  Displays the payment method name   

**N.B** : {customer_name} placeholder works only in order related emails. In account related emails use {user_login} instead.


### SAMPLE TEMPLATES

From version 2.0.5, you have sample templates, which can be accessed from templates page of the plugin.
You can access these sample templates as follows

1. Click on `Templates` submenu from dashboard.
2. From the `Edit Template` section, click on the dropdown under `Choose Template`.
3. You will see two groups in dropdown. `User Templates` and `Sample Templates`.
4. Choose a template from `Sample Templates` group and click the `Edit` Button.
5. The chosen template will be opened in the builder. You can give a name to the template, make changes if necessary and save the template.

### MISSING SAMPLE TEMPLATES ?

If your `Sample Templates` group in the `Edit Template` section dropdown is  empty or if you are seeing --empty-- option under `Sample Templates` group in dropdown, then you can follow the below steps.

1. Add the following code to the active theme/child theme functions.php   
	    
		add_filter('thwec_reset_sample_templates', '__return_true');

2. Deactivate and Activate the plugin
3. You will see sample templates added to the dropdown.   
   
### WPML - EMAIL CUSTOMIZER COMPATIBILITY
   
From version `3.0.0`, Email Customizer is compatible with WPML. This means that you can create template for each language added in WPML. Suppose you have 3 languages setup in WPML, email customizer provides you an option to create templates for each of the 3 language.

##### How does it work ?

1. Create a template (**My Template**) in the Email Customizer. The default language will be automatically selected in the language selector ( drop down in builder header ).
2. The template created in the default language is called the `base template`.
3. Once you have completed making changes, save the template by clicking the `Save` button in the builder header. Now from the language selector( the drop down in builder header ), choose the language in which you need to make the template.
4. You will see the `base template` loaded in the builder. Make necessary changes and click `Save` button in the builder header ( without changing the template name ). Now the template is saved for the new language.
5. Similarly, you can just change the language in builder and save changes for all the languages.
6. Now you have created template **My Template** in all WPML languages. i.e, under a template name **MY Template**, you have created WPML language versions of the template.
7. Assign this template to an email from `Email Customizer -> Templates -> Template Mapping`. 

Now when an order is placed, based on the language in which the order is placed, the corresponding language version of the template (**My Template**) will be loaded.

##### WPML Template Selection Criterias.

When the WooCommerce email is triggered, the WPML email template is selected based on some criterias. 
1. Pliugin checks for the order placed language version of the assigned template. Suppose if the assigned template for an email is **My Template**, then the plugin checks for the order placed language version of **My Template**. If the template version exists, the corresponding version of template is loaded.
2. If not, plugin checks for the default language version of the template (**My Template**). If the corresponding template is found, then the template is loaded.


##### Editing WPML Templates

The templates created using the Email Customizer are listed in `Email Customizer -> Templates -> Manage Template`.
Click the `Edit` option under the template name. The template in the default language will be loaded in the builder. 
Change the language in language selector( drop down in builder header), to view other language version of the template.   
   


