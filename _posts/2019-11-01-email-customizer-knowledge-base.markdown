---
layout: post
title:  Email Customizer Knowledge Base
categories: jekyll update
---

### CUSTOMER NOTE IN EMAIL TEMPLATE


There are situations where you have to show `Customer Note` in the email template. By default, Customer Note is not displayed in the Email Customizer templates. In order to show customer note, you have to use the placeholder `{th_customer_note}` where necessary.

Follow the steps to display customer note.
1. Click on `Add element` button in the right sidebar
2. Choose `Text` from the list that appears.
3. Click on  `Edit` (pencil icon) near the Text element.
4. Type the placeholder `{th_customer_note}` to display customer note.

You can use the available placeholders to place dynamic datas.
The available placeholders are {th_customer_name}, {th_billing_phone}, {th_order_id}, {th_order_url}, {th_billing_email}, {th_site_url}, {th_site_name}, {th_order_completed_date}, {th_order_created_date}, {th_checkout_payment_url}, {th_payment_method}, {th_customer_note}, {th_user_login}, {th_user_pass}, {th_account_area_url}, {th_reset_password_url.


### USING WOOCOMMERCE HOOKS IN TEMPALTE

WooCommerce have provided a number of hooks in the email template to pass data. Third party plugins or themes can use these hooks to pass data to the email templates. 

Email Customizer has the option to add or remove these WooCommerce Hooks. 

1. Click on `Add Element` button inside a column.
2. From the list that appears on sidebar, navigate and click on `WooCommerce Hooks` section.
3. Click on the hook necessary. Data will be replaced on placing an order.


### USING CUSTOM HOOK

Email customizer has a special feature called `Custom Hook`. The `Custom Hook` is an action hook, which can be used to add dynamic contents to the email template. You can use custom hook to show Order meta fields, Display shortcodes from third party plugins in Email,  Result based on checkout field values or on the email status like processing, on hold etc.

You can use the `Custom Hook` as follows

1. Click on `Add Element` button inside a column.
2. From the list that appears on sidebar, navigate and click on `WooCommerce Hooks` section.
3. Click on `Custom Hook` tile. You can see `{custom_hook_name}` added to the builder.
4. Click on the `Edit` button (pencil icon) near the `Custom Hook` entry in the right sidebar
5. Enter a unique name for the hook (eg: `themehigh_template_hook` ). Using an existing hook name can cause unexpected errors.
6. Use the hook name provided to write a function in the active theme/ child theme functions.php
	
    function themehigh_template_hook_callback( $order, $email ){
		// Your content here
	}
	add_action('themehigh_template_hook', 'themehigh_template_hook_callback', 10, 2);



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
