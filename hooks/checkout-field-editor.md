---
layout: post
title:  Hooks - Checkout Field Editor Pro
---

* Table of content. Use {:.no_toc} to escape some heading
{:toc}

## Filter hooks

### thwcfe_force_enqueue_checkout_public_scripts

	apply_filters('thwcfe_force_enqueue_checkout_public_scripts', false);

Enque checkout field editor's javascript & css files in other public pages.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_force_enqueue_checkout_public_scripts', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_debug_mode

	apply_filters('thwcfe_debug_mode', false);

Load unminified javascript & CSS files in front end for debugging.

#### Parameters

Boolean value

#### Usage

add_filter('thwcfe_debug_mode', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_enqueue_script_in_footer

	apply_filters('thwcfe_enqueue_script_in_footer', true);

Load javascript files in in footer.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_debug_mode', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_include_jquery_ui_i18n

	apply_filters( 'thwcfe_include_jquery_ui_i18n', TRUE );

Load jQuery UI i18n file for translation of jQuery UI elements.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_include_jquery_ui_i18n', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_select2_i18n_languages

	apply_filters('thwcfe_select2_i18n_languages', false);

Load languages files for select default messages & warning.

#### Parameters

empty array

#### Usage

	add_filter('thwcfe_select2_i18n_languages', $languages_array);

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_force_register_date_picker_script

	apply_filters('thwcfe_force_register_date_picker_script', false);

In default, WooCommerce will register data picker script in checkout page. If script is not loaded, use this filter to forcefully enque jQuery UI data picker script in checkout page.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_force_register_date_picker_script', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_date_picker_field_readonly

	apply_filters('thwcfe_date_picker_field_readonly', true);

In default, the date picker field is read-only. That means no option to enter date field manually. To enable manually entering value, use this filter & return false.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_date_picker_field_readonly', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_date_picker_notranslate

	apply_filters('thwcfe_date_picker_notranslate', true);

In default, date picker fields are not translatable. If translation required for these fields, use this filter & return false.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_date_picker_notranslate', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_time_picker_restrict_slots_for_same_day (???)

	apply_filters( 'thwcfe_time_picker_restrict_slots_for_same_day', true);

Disable all time slot before current time in current day in time picker field

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_time_picker_restrict_slots_for_same_day', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_enable_conditions_based_on_review_panel_fields - DPR

	apply_filters( 'thwcfe_enable_conditions_based_on_review_panel_fields', $enable_conditions_payment_shipping);

Enable conditional rules based on country, payment, shipping or review panel. Option already avialble in backend settings.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_enable_conditions_based_on_review_panel_fields', '__return_true');

#### Default value

Based on value in advance settings.

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_change_event_disabled_fields (????)

field names of disabled fields (examples - conditionally hide & show fields) that don't have a change event. Return comma separated field names.

	apply_filters('thwcfe_change_event_disabled_fields', '');

#### Parameters

String (Comma seperated field names)

#### Usage

	add_filter('thwcfe_change_event_disabled_fields', 'change_event_disabled_fields');
	
	function change_event_disabled_fields(){
		return 'field_name_1,field_name_2';
	}

#### Default value

Empty string

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfd_woocommerce_checkout_fields_hook_priority

	apply_filters('thwcfd_woocommerce_checkout_fields_hook_priority', 1000);

Set proirity of filter hook used to add new checkout fields

#### Parameters

Integer value

#### Usage

	add_filter('thwcfd_woocommerce_checkout_fields_hook_priority', 'th_34hf_function');

	function th_34hf_function(){
		return 9999;
	}

#### Default value

1000

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_override_country_locale

	apply_filters('thwcfe_override_country_locale', true);

In default, checkout field editor plugin override country related rules (exmple - ZIP code & state are required etc). If this override is not required, use filter & return false.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_override_country_locale', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_cart_product_categories

	apply_filters('thwcfe_cart_product_categories', array_values($cart['categories']);

There is an option to show or hide fields based on conditions like cart items is in a specific category. To do so, Checkout field editor plugin creates a category list of cart items. To override this category list, use this filter & return a new list of category in an array format.

#### Parameters

	Array (array of categories slug)


#### Usage

add_filter('thwcfe_cart_product_categories', 'override_cart_category' , 10, 1);

function override_cart_category($categories){
	
	// Remove an array element by search & find array key of slug
	if (($key = array_search('category-slug', $categories)) !== false) {
		unset($categories[$key]);
	}
	
	// Add new category
	array_push($categories, "another-category-slug");
	
	return $categories;
}

#### Default value

	Current cart items category in array format

#### Location

	includes/utils/class-thwcfe-utils.php

### thwcfe_ignore_wpml_translation_for_product_category

	apply_filters('thwcfe_ignore_wpml_translation_for_product_category', true);

Ignore product category translation for conditional fields.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_ignore_wpml_translation_for_product_category', '__return_true');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_use_default_fields_if_empty(internal pourpose only)

If shipping and billing fields are empty, use default billing and shipping fields.

	apply_filters('thwcfe_use_default_fields_if_empty', false, $section_name);

Parameters

1. Boolean
2. $section_name - section name ('billing' or 'shipping')

#### Usage

	add_filter('thwcfe_use_default_fields_if_empty', 'th_3df5func', 10, 2);
	
	function th_3df5func($value, $section_name){
		if($section_name == 'billing'){
			$value = true;
		}
		
		return $value;
	}

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_ignore_address_field_changes (**** - need to change hook name)

	apply_filters('thwcfe_ignore_address_field_changes', false));

If checkout fields are overridden by Checkout field editor plugin, ignore these changes in my account pages and only effect in checkout fields.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_ignore_address_field_changes', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_skip_default_address_fields_override

	apply_filters('thwcfe_skip_default_address_fields_override', false);

Disable overriding of defaul address fields (country, zip, address 1, address 2).

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_skip_default_address_fields_override', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_with   *******************?????

	apply_filters('thwcfe_address_field_override_with', 'billing');
	
If the default address fields override is disabled, default address fields are fields in billing section. Developer can switch the section name using this filter.

#### Parameters

String

#### Usage

	add_filter('thwcfe_address_field_override_with', 'address_field_override_with_shipping', 10, 1);
	function address_field_override_with_shipping($section){
		$section = 'shipping';
		return $section;
	}

#### Default value

'billing'

#### Location

	public/class-thwcfe-public-checkout.php


### thwcfe_address_field_override_placeholder

	apply_filters('thwcfe_address_field_override_placeholder', true, $country);

If there is a placeholder in WooCommerce country locale for a country, disable checkout field editor plugin override of that placeholder.

#### Parameters

1. Boolean value
2. $country

#### Usage

add_filter('thwcfe_address_field_override_placeholder', 'disable_address_field_override_placeholder' , 10, 2);

function disable_address_field_override_placeholder($value, $country){
	
	if($country == 'US'){
		$value = false;
	}
	
	return $value;
}

#### Default value

True

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_label

	apply_filters('thwcfe_address_field_override_label', true, $country);

If there is a label in WooCommerce country locale for a country, disable checkout field editor plugin override of that label.

#### Parameters

1. Boolean value
2. $country

#### Usage

	add_filter('thwcfe_address_field_override_label', 'disable_address_field_override_label' , 10, 2);

	function disable_address_field_override_label($value, $country){
		
		if($country == 'US'){
			$value = false;
		}
		
		return $value;
	}

#### Default value

True

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_required

	apply_filters('thwcfe_address_field_override_required', false, $country);

If there is a required parameter for a field in WooCommerce country locale for a country, disable checkout field editor plugin override of that required parameter.

#### Parameters

1. Boolean value
2. $country

#### Usage

	add_filter('thwcfe_address_field_override_required', 'disable_address_field_override_required' , 10, 2);

	function disable_address_field_override_required($value, $country){
		
		if($country == 'US'){
			$value = true;
		}
		
		return $value;
	}


#### Default value

False

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_priority

	apply_filters('thwcfe_address_field_override_priority', true, $country);

If there is a priority parameter for a field in WooCommerce country locale for a country, disable checkout field editor plugin override of that priority parameter.

#### Parameters

1. Boolean value
2. $country

#### Usage

	add_filter('thwcfe_address_field_override_priority', 'disable_address_field_override_priority' , 10, 2);

	function disable_address_field_override_priority($value, $country){
		
		if($country == 'US'){
			$value = false;
		}
		
		return $value;
	}

#### Default value

True

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_custom_section_positions

	apply_filters('thwcfe_custom_section_positions', array());

Add custom hooks (created by multistep checkout plugin or any other plugin that add a hook in checkout page) to checkout page.

#### Parameters

array

#### Usage

	add_filter('thwcfe_custom_section_positions', 'thwcfe_custom_section_positions');
	function thwcfe_custom_section_positions($custom){
		$custom = array(
			'hook_name' => 'title';
		);

		return $custom;
	}

#### Default value

Empty array

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_disabled_hooks

	apply_filters('thwcfe_disabled_hooks', $dis_hooks);

Filter the disabled hooks by checkout field editor plugin. 

#### Parameters

Array (array of disabled hooks)

#### Usage

	add_filter('thwcfe_disabled_hooks', 'th_modify_disabled_hooks', 10, 1);
	
	function th_modify_disabled_hooks($hooks){
	
		return $hooks;
	}

#### Default value

	An array of disabled hook as per different conditions.

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_disabled_sections

	apply_filters('thwcfe_disabled_sections', $dis_sections);

Get the disabled sections

#### Parameters

Array

#### Usage

	add_filter('thwcfe_disabled_sections', 'thwcfe_remove_disabled_sections');
	function thwcfe_remove_disabled_sections($sections){
		$sections[] = 'section_name';

		return $sections;
	}


#### Default value

Empty array

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_disabled_fields

	apply_filters('thwcfe_disabled_fields', $dis_fields);

Get the disabled fields

#### Parameters

Array

#### Usage

	add_filter('thwcfe_disabled_fields', 'thwcfe_remove_disabled_fields');
	function thwcfe_remove_disabled_fields($fields){
		$fields[] = 'field_name';

		return $fields;
	}

#### Default value

Empty Array

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_woocommerce_checkout_user_meta_posted_value_$key

	apply_filters( 'thwcfe_woocommerce_checkout_user_meta_posted_value_'.$key, $value, $customer_id, $posted );

If field value is saved as user meta, override submitted data of field before saving as user meta

#### Parameters

$value - string
$customer_id - integer
$posted - Array

#### Usage

	add_filter('thwcfe_woocommerce_checkout_user_meta_posted_value_field_name', 'thwcfe_change_submited_value_of_field', 10, 3);
	
	function thwcfe_change_submited_value_of_field($value, $customer_id, $posted){
		$value = 'changed value';
		return $value;
	}


#### Default value

$posted - Checkout data

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_woocommerce_checkout_order_meta_posted_value_$key

	apply_filters( 'thwcfe_woocommerce_checkout_order_meta_posted_value_'.$key, $value, $order_id, $posted );

Override submitted data of field before saving as order meta

#### Parameters

$value - string
$order_id - integer
$posted - array

#### Usage

	add_filter('thwcfe_woocommerce_checkout_order_meta_posted_value_field_name', 'thwcfe_change_submited_order_value_of_field', 10, 3);
	
	function thwcfe_change_submited_order_value_of_field($value, $order_id, $posted){
		$value = 'changed value';

		return $value;
	}

#### Default value

$posted - Checkout data

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_force_wp_session

	apply_filters('thwcfe_force_wp_session', false);

Use PHP session instead of WooCommerce session

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_force_wp_session', '__return_true');

#### Default value

False

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_force_start_session

	apply_filters('thwcfe_force_start_session', false);

If PHP session is using, trigger session_start.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_force_wp_session', '__return_true');

#### Default value

False

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_checkout_field_extra_price_$name

	apply_filters('thwcfe_checkout_field_extra_price_'.$name, $price, $value);

Override additional price for checkout field.

#### Parameters

	$price - Float number
	$value - string
	
#### Usage

	add_filter('thwcfe_checkout_field_extra_price_field_name', 'thwcfe_change_value_of_price_field', 10, 2);
	function thwcfe_change_value_of_price_field($price, $value){
		$price = 20; // New Price

		return $price;
	}

#### Default value

	Field price

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_dynamic_price_quantity (???????)

	apply_filters('thwcfe_dynamic_price_quantity', $qty, $name);

If field price is dynamic, filter the price quantity.

#### Parameters

	$qty - Integer
	$name - String

#### Usage

	add_filter('thwcfe_dynamic_price_quantity', 'thwcfe_change_quantity_added_in_field', 10, 2);
	function thwcfe_change_quantity_added_in_field($qty, $name){
		if($name == 'test_field'){
			$qty = 2;
		}

		return $qty;
	}

#### Default value

	false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_checkout_field_extra_cost_$name

	apply_filters('thwcfe_checkout_field_extra_cost_'.$name, $fprice, $value);

Modify price of checkout field

#### Parameters

$fprice =  Integer or float
$value = string

#### Usage

	add_filter('thwcfe_checkout_field_extra_cost_your_field_name', 'th_modify_checkout_field_extra_cost', 10, 2);

	function th_modify_checkout_field_extra_cost($field_price, $field_value){
		
		return $field_price;
	}


#### Default value

	Field price

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_show_tax_label_in_cart_totals_fee_html

	apply_filters('thwcfe_show_tax_label_in_cart_totals_fee_html', true);
	
Show / hide the tax label of checkout fees added by checkout field editor field with price.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_show_tax_label_in_cart_totals_fee_html', '__return_false');

#### Default value

True

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_country_hidden_field_override_default_value (???????)

	apply_filters('thwcfe_country_hidden_field_override_default_value', false, $key, $value)

#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_nl2br_custom_field_value ????????

	apply_filters('thwcfe_nl2br_custom_field_value', true);

#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php


### thwcfe_esc_attr_custom_field_label_thankyou_page

	apply_filters('thwcfe_esc_attr_custom_field_label_thankyou_page', false)
	
Escape HTML attribute of field label in thank you page.

#### Parameters

Boolean

#### Usage

apply_filters('thwcfe_esc_attr_custom_field_label_thankyou_page', '__return_true');

#### Default value

False

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_clickable_filename_in_order_view

	apply_filters('thwcfe_clickable_filename_in_order_view', true, $key);

Uploaded file wiil be clicable in thank you page as link. To show it as text, use this filter & return false.

#### Parameters

$key - field name

#### Usage

	add_filter('thwcfe_clickable_filename_in_order_view', '__return_false');

#### Default value

True

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_align_field_value_in_separate_lines

	apply_filters('thwcfe_align_field_value_in_separate_lines', false);

Show multi select and checkbox group options in separate line in thank you page & order detail pages.

#### Parameters

Boolean

#### Usage

	add_filter('thwcfe_align_field_value_in_separate_lines', '__return_true');

#### Default value

False

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_view_order_customer_details_table_view

	apply_filters( 'thwcfe_view_order_customer_details_table_view', true );

Show the items added as table view in the thank you page. To show in dt dd tags, use this filter & return false.

#### Parameters

Boolean

#### Usage

	add_filter('thwcfe_view_order_customer_details_table_view', '__return_false');

#### Default value

True

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_myaccount_address_fields_hook_priority

	apply_filters('thwcfe_myaccount_address_fields_hook_priority', 1100);

Set filter hook priority to add address field created by checkout field editor plugin.

#### Parameters

Integer value

#### Usage

	add_filter('thwcfe_myaccount_address_fields_hook_priority', 'myaccount_address_fields_hook_priority');
	function myaccount_address_fields_hook_priority($priority){

		return $priority;	
	}

#### Default value

1100

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_myaccount_display_hidden_field_as_text_field

	apply_filters('thwcfe_myaccount_display_hidden_field_as_text_field', false);

Display hidden field as text field in my account page

#### Parameters

Boolean

#### Usage

	add_filter('thwcfe_myaccount_display_hidden_field_as_text_field', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_ignore_custom_fields_in_address_to_edit

	apply_filters('thwcfe_ignore_custom_fields_in_address_to_edit', false)

Ignore custom field in edit address form in my account page.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_ignore_custom_fields_in_address_to_edit', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_edit_address_ignore_row_split

	apply_filters('thwcfe_edit_address_ignore_row_split', true);

Ignoring the form row first an last class.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_edit_address_ignore_row_split', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_edit_address_form_enctype_multipart ?????????

	apply_filters('thwcfe_edit_address_form_enctype_multipart', false);

#### Parameters

Boolean value

#### Usage

#### Default value

false

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_show_in_my_account_page

	apply_filters('thwcfe_show_in_my_account_page', true, $key);

Display / remove checkout field in my account page & edit address forms.

#### Parameters

$key - string (field_name)

#### Usage

	add_filter('thwcfe_show_in_my_account_page', 'er3_show_in_my_account_page', 10, 2);

	function er3_show_in_my_account_page($show, $key){
		
		return $show;
	}

#### Default value

True

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_edit_account_enable_file_support

	apply_filters('thwcfe_edit_account_enable_file_support', true);

Add `enctype="multipart/form-data"` attribute in edit account form.

#### Parameters

Boolean

#### Usage

	add_filter('thwcfe_edit_account_enable_file_support', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_show_section_in_my_account_page

	apply_filters('thwcfe_show_section_in_my_account_page', true, $sname);

Show section in my account page.

#### Parameters

$sname - string (section name)

#### Usage

	add_filter('thwcfe_show_section_in_my_account_page', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_show_section_title_in_my_account_page

	apply_filters('thwcfe_show_section_title_in_my_account_page', $show_section_title, $sname);

Override show section title settings of my account page.

#### Parameters

$show_section_title - string
$sname - string

#### Usage

	add_filter('thwcfe_show_section_title_in_my_account_page', 'er3_show_in_my_account_page', 10, 2);

	function er3_show_in_my_account_page($show_section_title, $section_name){
		
		return $show_section_title;
	}

#### Default value

True or false as per section settings.

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_skip_address_fields_override_with_locale

	apply_filters('thwcfe_skip_address_fields_override_with_locale', false)

Skip address field override by checkout field Editor.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_skip_address_fields_override_with_locale', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public.php

### thwcfe_show_edit_address_form_field_$key

	apply_filters('thwcfe_show_edit_address_form_field_'.$key, true, $sname, $field);

#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_file_upload_maxsize

	apply_filters('thwcfe_file_upload_maxsize', $maxsize, $name);

File upload maximum size

#### Parameters

$maxsize - Integer
$name - string

#### Usage

	add_filter('thwcfe_file_upload_maxsize', 'm35rt_file_upload_maxsize', 10, 2);
	function m35rt_file_upload_maxsize($maxsize, $name){
		
		return $maxsize;
	}

#### Default value

Value as per field setting.

#### Location

	public/class-thwcfe-public.php

### thwcfe_file_upload_accepted_file_types

	apply_filters('thwcfe_file_upload_accepted_file_types', $accept, $name);

Acceptable file type for file upload field.

#### Parameters

$accept - array
$name - string

#### Usage

	add_filter('thwcfe_file_upload_accepted_file_types', 'm35rt_file_upload_accepted_file_types', 10, 2);
	function m35rt_file_upload_accepted_file_types($accept, $name){
		
		return $accept;
	}

#### Default value

Value as per field settings

#### Location

	public/class-thwcfe-public.php

### thwcfe_ignore_fields

	apply_filters('thwcfe_ignore_fields', array());

Ignore fields in checkout form.

#### Parameters

array

#### Usage

	add_filter('thwcfe_ignore_fields', 'thwcfe_ignore_field_array');
	function thwcfe_ignore_field_array($fields){
		$fields = array('field_name_1, field_name_2, field_name_3');

		return $fields;
	}

#### Default value

empty array

#### Location

	public/class-thwcfe-public.php

### thwcfe_woocommerce_form_field_value

	apply_filters( 'thwcfe_woocommerce_form_field_value', $value, $key );

Filter form field value

#### Parameters

$value - string
$key - string

#### Usage

	add_filter('thwcfe_woocommerce_form_field_value', 'change_new_value_to_field', 10, 2);
	function change_new_value_to_field($value, $key){
		if($key == 'field_name'){
			$value = 'new value';
		}
		
		return $value;
	}

#### Default value

Value as per submitted data

#### Location

	public/class-thwcfe-public.php

### woocommerce_form_field_args

	apply_filters( 'woocommerce_form_field_args', $args, $key, $value );

#### Parameters

$args - array
$key - string
$value - string

#### Usage

	add_filter('woocommerce_form_field_args', 'change_form_field_args', 10, 3);
	function change_form_field_args($args, $key, $value){
		$arg = // new arg for the field;

		return $args;
	}

#### Default value

	array as per field settings.

#### Location

	public/class-thwcfe-public.php

### thwcfe_disable_checkout_field_autocomplete

	apply_filters('thwcfe_disable_checkout_field_autocomplete', false, $key);

Disable field auto compleete.

#### Parameters

	Boolean
	$key - string

#### Usage

	add_filter('thwcfe_disable_checkout_field_autocomplete', 'change_autocomplete_parameter', 10, 2);
	function change_autocomplete_parameter($flag, $key){
		if($flag == 'field_name'){
			$flag = true;
		}

		return $flag;
	}

#### Default value

	false

#### Location

	public/class-thwcfe-public.php

### thwcfe_is_readonly_field_$key

apply_filters('thwcfe_is_readonly_field_'.$key, false));

Make field as read only.

#### Parameters

Boolean value

#### Usage

	add_filter('thwcfe_is_readonly_field_your_field', 'm35rt_read_only_field');
	function m35rt_file_upload_maxsize($read_only){
		
		return $read_only;
	}

#### Default value

false

#### Location

	public/class-thwcfe-public.php

### thwcfe_display_field_description_below_label

	apply_filters('thwcfe_display_field_description_below_label', false, $key)

Display field description below label

#### Parameters

Boolean
$key - string

#### Usage

	add_filter('thwcfe_display_field_description_below_label', 'm35rt_display_field_description_below_label', 10, 2);
	function m35rt_display_field_description_below_label($show_below, $key){

		return $show_below;
	}

#### Default value

false

#### Location

	public/class-thwcfe-public.php

### thwcfe_input_field_options_$key

	apply_filters( 'thwcfe_input_field_options_'.$key, $args['options_object'] );

Override field's settings by checkout field editor plugin

#### Parameters

Object

#### Usage

	add_filter('thwcfe_input_field_options_your_field', 'm34er_input_field_options');
	function m34er_input_field_options($_Object){

		return $_Object;
	}

#### Default value

Field settings

#### Location

	public/class-thwcfe-public.php

### thwcfe_checkboxgroup_options_per_line

	apply_filters('thwcfe_checkboxgroup_options_per_line', 1, $key);

#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_input_field_options

	apply_filters( 'thwcfe_input_field_options', $args['options_object'], $key );

Override field's settings by checkout field editor plugin.

#### Parameters

$args['options_object'] - object
$key - string

#### Usage

	add_filter('thwcfe_input_field_options_your_field', 'm34er_input_field_options', 10, 2);
	function m34er_input_field_options($_Options, $key){

		return $_Options;
	}

#### Default value

Field settings

#### Location

	public/class-thwcfe-public.php

### thwcfe_min_date_date_picker_$key

	apply_filters( 'thwcfe_min_date_date_picker_'.$key, $minDate );

Set date picker min date.

#### Parameters

$minDate - Integer

#### Usage

	add_filter('thwcfe_min_date_date_picker_your_field_name', 'change_mindate_parameter');
	function change_mindate_parameter($min_date){

		return $min_date;
	}

#### Default value

Value as per field setting.

#### Location

	public/class-thwcfe-public.php

### thwcfe_max_date_date_picker_$key

	apply_filters( 'thwcfe_max_date_date_picker_'.$key, $maxDate );

Set date picker max date.

#### Parameters

Integer

#### Usage

	add_filter('thwcfe_max_date_date_picker_your_field_name', 'change_maxdate_parameter');
	function change_maxdate_parameter($max_date){

		return $max_date;
	}

#### Default value

Value as per field setting.

#### Location

	public/class-thwcfe-public.php

### thwcfe_disabled_days_date_picker_$key

	apply_filters( 'thwcfe_disabled_days_date_picker_'.$key, $disabledDays );

Set disabled day for date picker field.

#### Parameters

Coma seperated week days abbrivation

#### Usage

	add_filter('thwcfe_disabled_days_date_picker_your_field_name', 'th34_override_disabled_days');
	function th34_override_disabled_days($disabled_days){
		
		return $disabled_days;
	}

#### Default value

Value as per field setting.

#### Location

	public/class-thwcfe-public.php

### thwcfe_disabled_dates_date_picker_$key

	apply_filters( 'thwcfe_disabled_dates_date_picker_'.$key, $disabledDates );

Set disabled dates for date picker field.

#### Parameters

Coma seperated dates in yyyy-mm-dd format.

#### Usage

	add_filter('thwcfe_disabled_dates_date_picker_your_field_name', 'th34_override_disabled_dates');
	function th34_override_disabled_dates($disabled_dates){
		
		write_log($disabled_dates);
		
		return $disabled_dates;
	}

#### Default value

Value as per field setting.

#### Location

	public/class-thwcfe-public.php

### thwcfe_date_picker_first_day

	apply_filters( 'thwcfe_date_picker_first_day', 0, $key );

Set date picker's first day

#### Parameters

Intiger - Week day number
$key -  String

#### Usage

	add_filter('thwcfe_date_picker_first_day', 'change_new_start_day', 10, 2);
	function change_new_start_day($value, $key){

		return $value;
	}
	
0 - for Sunday
1 - for Monday
6 - for Saturday

#### Default value

0 - (Sunday)

#### Location

	public/class-thwcfe-public.php

### thwcfe_min_time_time_picker_$key

	apply_filters( 'thwcfe_min_time_time_picker_'.$key, $args['min_time'] );

Set minimum time for time picker.

#### Parameters

Time in 12 hour format

#### Usage

	add_filter('thwcfe_min_time_time_picker_your_field_name', 'change_min_time_picker', 10, 1);
	function change_min_time_picker($min_time){
		
		return $min_time;
	}


#### Default value

12:00am / value as per field settings

#### Location

	public/class-thwcfe-public.php

### thwcfe_max_time_time_picker_$key

	apply_filters( 'thwcfe_max_time_time_picker_'.$key, $args['max_time'] );

Set max time for time picker field.

#### Parameters

Time in 12 hour format

#### Usage

	add_filter('thwcfe_max_time_time_picker_your_field_name', 'change_max_time_picker', 10, 1);
	function change_max_time_picker($max_time){
		
		return $max_time;
	}

#### Default value

11:30pm / value as per field settings

#### Location

	public/class-thwcfe-public.php

### thwcfe_start_time_time_picker_$key

	apply_filters( 'thwcfe_start_time_time_picker_'.$key, $args['start_time'] );

Set selectable time by considering current time & min. time for time picker. Example like prepartion time. If min time is 10 AM & user current time is 11 AM & start time is 2 hour, user can only select time slots after 1 PM.

#### Parameters

String - (Hour & minutes)

#### Usage

	add_filter('thwcfe_start_time_time_picker_your_field_name', 'er34t_start_time_time_picker');
	function er34t_start_time_time_picker($start_time){
		return $start_time;
	}

#### Default value

False

#### Location

	public/class-thwcfe-public.php

### thwcfe_time_step_time_picker_$key

	apply_filters( 'thwcfe_time_step_time_picker_'.$key, $args['time_step'] );

Step for time picker field.

#### Parameters

Integer - (Minutes as integer)

#### Usage

	add_filter('thwcfe_time_step_time_picker_your_field_name', 'we34r_change_time_step');
	function we34r_change_time_step($time_step){
		return $time_step;
		
	}

#### Default value

30

#### Location

	public/class-thwcfe-public.php

### thwcfe_linked_date_time_picker_$key

	apply_filters( 'thwcfe_linked_date_time_picker_'.$key, $args['linked_date'] );

Link date picker field with a time picker field.

Example case - Disable time picker on Sunday if there is another date picker field with Sunday as disabled day.

#### Parameters

String (field name)

#### Usage

	add_filter( 'thwcfe_linked_date_time_picker_your_field_name', 'qs325_link_date_picker_time_picker' );
	function qs325_link_date_picker_time_picker($date_picker_field_name){
		
		return $date_picker_field_name;
	}

#### Default value

Empty

#### Location

	public/class-thwcfe-public.php

### thwcfe_my-account_file_name_prefix

	apply_filters('thwcfe_my-account_file_name_prefix', '', $key);
	
Add / Change uploaded file's name prefix.

#### Parameters

Empty string

$key - String

#### Usage

	add_filter( 'thwcfe_my-account_file_name_prefix', 'qs325_thwcfe_uploaded_file_name_prefix', 10, 2 );
	function qs325_thwcfe_uploaded_file_name_prefix($prefix, $key){
		
		return $prefix;
	}

#### Default value

Empty string

#### Location

	public/class-thwcfe-public.php

### thwcfe_woo_api_order_response_fields

	apply_filters('thwcfe_woo_api_order_response_fields', $fields);

Add custom checkout field data in to old legacy WooCommerce REST API responce.

#### Parameters

1. $fields (array)

#### Usage

	add_filter('thwcfe_woo_api_order_response_fields', 'th_custom_function');

	function th_custom_function(){
		return array('field_1', 'field_2');
	}

#### Default value

Empty array

#### Location

	includes/compatibility/class-wcfe-wc-api-handler.php
