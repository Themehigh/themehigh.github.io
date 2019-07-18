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

#### Useage

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

#### Useage

	add_filter('thwcfe_debug_mode', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_include_jquery_ui_i18n

	apply_filters( 'thwcfe_include_jquery_ui_i18n', TRUE );

Load jQuery UI i18n file for translation of jQuery UI elements

#### Parameters

Boolean value

#### Useage

	add_filter('thwcfe_include_jquery_ui_i18n', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_select2_i18n_languages**

apply_filters('thwcfe_select2_i18n_languages', array());

which languages select2 (warning message & defaut) to be translated. langes array

#### Parameters

empty array

#### Useage

	add_filter('thwcfe_select2_i18n_languages', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_force_register_date_picker_script

	apply_filters('thwcfe_force_register_date_picker_script', false);

Enque jQuery UI data picker script in checkout page.

#### Parameters

Boolean value

#### Useage

	add_filter('thwcfe_force_register_date_picker_script', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_date_picker_field_readonly**

	apply_filters('thwcfe_date_picker_field_readonly', true);

Date picker read only. No option to enter date field manually.  If manually enetering required, return false.

#### Parameters

Boolean value

#### Useage

	add_filter('thwcfe_date_picker_field_readonly', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_date_picker_notranslate**

	apply_filters('thwcfe_date_picker_notranslate', true);

Enable date picker for translateion.

#### Parameters

Boolean value

#### Useage

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

#### Useage

	add_filter('thwcfe_time_picker_restrict_slots_for_same_day', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_enable_conditions_based_on_review_panel_fields**

	apply_filters( 'thwcfe_enable_conditions_based_on_review_panel_fields', $enable_conditions_payment_shipping);

Enable conditional rules based on payment and shipping. Option already avialble in backend settings.

#### Parameters



#### Useage


#### Default value


#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_change_event_disabled_fields (????)

	apply_filters('thwcfe_change_event_disabled_fields', '');


#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfd_woocommerce_checkout_fields_hook_priority

	apply_filters('thwcfd_woocommerce_checkout_fields_hook_priority', 1000);

Set proirity of filter hook used to add new checkout fields

#### Parameters

Integer value

#### Useage

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

Override country related rules on the checkout fields like ZIP code & state etc.

#### Parameters

Boolean value

#### Useage

	add_filter('thwcfe_override_country_locale', '__return_false');

#### Default value

true

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_cart_product_categories(????)

	apply_filters('thwcfe_cart_product_categories', array_values($cart['categories']);

Modify category summery

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_ignore_wpml_translation_for_product_category**

	apply_filters('thwcfe_ignore_wpml_translation_for_product_category', true);

ignore product category translation for conditional fields.

#### Parameters

Boolean value

#### Useage

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

#### Useage

	add_filter('thwcfe_use_default_fields_if_empty', 'th_3df5func');

	function th_3df5func($section_name){
		if($section_name){

		}
	}

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_ignore_address_field_changes (???? - need to change hook name)

	apply_filters('thwcfe_ignore_address_field_changes', false));

If checkout field are overrided by cfe plugin, ignore this changes in my account pages and only effect in checkout fields.

#### Parameters

Boolean value

#### Useage

	add_filter('thwcfe_ignore_address_field_changes', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_skip_default_address_fields_override (Private use ----------------------------)

	apply_filters('thwcfe_skip_default_address_fields_override', false);

Disable overriding of defaul address fields (country, zip, address 1, address 2).

#### Parameters

Boolean value

#### Useage

	add_filter('thwcfe_skip_default_address_fields_override', '__return_true');

#### Default value

false

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_with

	apply_filters('thwcfe_address_field_override_with', 'billing');

#### Parameters

String

#### Useage

#### Default value

'billing'

#### Location

	public/class-thwcfe-public-checkout.php


### thwcfe_address_field_override_placeholder

	apply_filters('thwcfe_address_field_override_placeholder', true, $country);

Override field placeholder based on country.

#### Parameters

1. Boolean value
2. $country

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_label

	apply_filters('thwcfe_address_field_override_label', true, $country);

Override field label based on country

#### Parameters

1. Boolean value
2. $country

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_required

	apply_filters('thwcfe_address_field_override_required', false, $country);

Override field required condition based on country

#### Parameters

1. Boolean value
2. $country

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_address_field_override_priority

	apply_filters('thwcfe_address_field_override_priority', true, $country);

Override field priority based on country.

#### Parameters

1. Boolean value
2. $country

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_country_locale_override_with

	apply_filters('thwcfe_country_locale_override_with', 'billing');

#### Parameters

String

#### Useage

#### Default value

'billing'

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_custom_section_positions

	apply_filters('thwcfe_custom_section_positions', array());

Add custom hooks (created by multistep checkout plugin) to checkout page

#### Parameters

array

#### Useage

#### Default value

Empty array

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_disabled_hooks

	apply_filters('thwcfe_disabled_hooks', $dis_hooks);

Get the disabled hooks by other plugins / theme

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_disabled_sections

	apply_filters('thwcfe_disabled_sections', $dis_sections);

Get the disabled sections by other plugins / theme

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_disabled_fields

	apply_filters('thwcfe_disabled_fields', $dis_fields);

Get the disabled fields by other plugins / theme

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_woocommerce_checkout_user_meta_posted_value_$key

	apply_filters( 'thwcfe_woocommerce_checkout_user_meta_posted_value_'.$key, $value, $customer_id, $posted );

If field value is saved as user meta, override submitted data of field before saving as user meta

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_woocommerce_checkout_order_meta_posted_value_$key

	apply_filters( 'thwcfe_woocommerce_checkout_order_meta_posted_value_'.$key, $value, $order_id, $posted );

Override submitted data of field before saving as order meta

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_force_wp_session

	apply_filters('thwcfe_force_wp_session', false);

Use PHP session instead of WooCommerce session

#### Parameters

Boolean value

#### Useage

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

#### Useage

	add_filter('thwcfe_force_wp_session', '__return_true');

#### Default value

False

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_checkout_field_extra_price_$name

	apply_filters('thwcfe_checkout_field_extra_price_'.$name, $price, $value);

Override additional price for checkout field.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_dynamic_price_quantity

	apply_filters('thwcfe_dynamic_price_quantity', $qty, $name);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_checkout_field_extra_cost_$name

	apply_filters('thwcfe_checkout_field_extra_cost_'.$name, $fprice, $value);

Add an extra cost for checkout field

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_show_tax_label_in_cart_totals_fee_html

	apply_filters('thwcfe_show_tax_label_in_cart_totals_fee_html', true);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_country_hidden_field_override_default_value

	apply_filters('thwcfe_country_hidden_field_override_default_value', false, $key, $value)

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_nl2br_custom_field_value

	apply_filters('thwcfe_nl2br_custom_field_value', true);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php


### thwcfe_esc_attr_custom_field_label_thankyou_page

	apply_filters('thwcfe_esc_attr_custom_field_label_thankyou_page', false)

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_clickable_filename_in_order_view

	apply_filters('thwcfe_clickable_filename_in_order_view', true, $key)

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_align_field_value_in_separate_lines

	apply_filters('thwcfe_align_field_value_in_separate_lines', false);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_esc_attr_custom_field_label_thankyou_page

	apply_filters('thwcfe_esc_attr_custom_field_label_thankyou_page', false)

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_view_order_customer_details_table_view

	apply_filters( 'thwcfe_view_order_customer_details_table_view', true )

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-checkout.php

### thwcfe_myaccount_address_fields_hook_priority

	apply_filters('thwcfe_myaccount_address_fields_hook_priority', 1100);

Set filter hook priority to add address field created by checkout field editor plugin.

#### Parameters

Integer value

#### Useage

#### Default value

1100

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_myaccount_display_hidden_field_as_text_field

	apply_filters('thwcfe_myaccount_display_hidden_field_as_text_field', false);

Display hidden field as text field in my account page

#### Parameters

Integer value

#### Useage

#### Default value

1100

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_ignore_custom_fields_in_address_to_edit

	apply_filters('thwcfe_ignore_custom_fields_in_address_to_edit', false)

Ignore custom field in edit address form.

#### Parameters

Boolean value

#### Useage

#### Default value

false

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_edit_address_ignore_row_split

	apply_filters('thwcfe_edit_address_ignore_row_split', true)

#### Parameters

Boolean value

#### Useage

#### Default value

false

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_edit_address_form_enctype_multipart

	apply_filters('thwcfe_edit_address_form_enctype_multipart', false);

#### Parameters

Boolean value

#### Useage

#### Default value

false

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_show_in_my_account_page

	apply_filters('thwcfe_show_in_my_account_page', true, $key);

Display checkout field in my account page.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_edit_account_enable_file_support

	apply_filters('thwcfe_edit_account_enable_file_support', true);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_show_section_in_my_account_page

	apply_filters('thwcfe_show_section_in_my_account_page', true, $sname);

Show section in my account page.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_show_section_title_in_my_account_page

	apply_filters('thwcfe_show_section_title_in_my_account_page', $show_section_title, $sname);

Show section title in my account page

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public-myaccount.php

### thwcfe_skip_address_fields_override_with_locale

	apply_filters('thwcfe_skip_address_fields_override_with_locale', false)

Skip address field override by checkout field Editor.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_show_edit_address_form_field_$key

	apply_filters('thwcfe_show_edit_address_form_field_'.$key, true, $sname, $field);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_file_upload_maxsize

	apply_filters('thwcfe_file_upload_maxsize', $field['maxsize'], $name);

File upload maximum size

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_file_upload_accepted_file_types

	apply_filters('thwcfe_file_upload_accepted_file_types', $field['accept'], $name);

Acceptable file type for file upload field.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_ignore_fields

	apply_filters('thwcfe_ignore_fields', array());

Ignore fields

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_woocommerce_form_field_value

	apply_filters( 'thwcfe_woocommerce_form_field_value', $value, $key );

Filter form field value

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### woocommerce_form_field_args

	apply_filters( 'woocommerce_form_field_args', $args, $key, $value );

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_disable_checkout_field_autocomplete

	apply_filters('thwcfe_disable_checkout_field_autocomplete', false, $key);

Disable field auto compleete.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_is_readonly_field_$key

apply_filters('thwcfe_is_readonly_field_'.$key, false));

Make field as read only.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_display_field_description_below_label

	apply_filters('thwcfe_display_field_description_below_label', false, $key)

Display field description below label

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_input_field_options_$key

	apply_filters( 'thwcfe_input_field_options_'.$key, $args['options_object'] );

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_checkboxgroup_options_per_line

	apply_filters('thwcfe_checkboxgroup_options_per_line', 1, $key);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_woocommerce_form_field_value

	apply_filters( 'thwcfe_woocommerce_form_field_value', $value, $key );

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_input_field_options

	apply_filters( 'thwcfe_input_field_options', $args['options_object'], $key );

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_input_field_options_$key

	apply_filters( 'thwcfe_input_field_options_'.$key, $args['options_object'] );

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_min_date_date_picker_$key

	apply_filters( 'thwcfe_min_date_date_picker_'.$key, $minDate );

Set date picker min date.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_max_date_date_picker_$key

	apply_filters( 'thwcfe_max_date_date_picker_'.$key, $maxDate );

Set date picker max date.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_disabled_days_date_picker_$key

	apply_filters( 'thwcfe_disabled_days_date_picker_'.$key, $disabledDays );

Set disabled day for date picker field

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_disabled_dates_date_picker_$key

	apply_filters( 'thwcfe_disabled_dates_date_picker_'.$key, $disabledDates );

Set disabled dates for date picker field.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_date_picker_first_day

	apply_filters( 'thwcfe_date_picker_first_day', 0, $key );

Set date picker's first day

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_min_time_time_picker_$key

	apply_filters( 'thwcfe_min_time_time_picker_'.$key, $args['min_time'] );

Set min. time for time picker.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_max_time_time_picker_$key

	apply_filters( 'thwcfe_max_time_time_picker_'.$key, $args['max_time'] );

Set max time for time picker field.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_start_time_time_picker_$key

	apply_filters( 'thwcfe_start_time_time_picker_'.$key, $args['start_time'] );

Set start time for time picker

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_time_step_time_picker_$key

	apply_filters( 'thwcfe_time_step_time_picker_'.$key, $args['time_step'] );

Step for time picker field.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_linked_date_time_picker_$key

	apply_filters( 'thwcfe_linked_date_time_picker_'.$key, $args['linked_date'] );

Linked date for time picker.

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### account_file_name_prefix

	apply_filters('thwcfe_my-account_file_name_prefix', '', $key);

#### Parameters

#### Useage

#### Default value

#### Location

	public/class-thwcfe-public.php

### thwcfe_woo_api_order_response_fields

	apply_filters('thwcfe_woo_api_order_response_fields', $fields);

Add custom checkout field data in to WooCommerce REST API responce.

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
