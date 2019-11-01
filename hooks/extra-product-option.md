---
layout: post
title:  Hooks - Extra Product Option Pro
---

* Table of content. Use {:.no_toc} to escape some heading
{:toc}

## Filter hooks

### thwepo_extra_fields_display_position

Filter available field display positions in backend settings.

	apply_filters('thwepo_extra_fields_display_position', $positions);

#### Parameters

Array

#### Usage

	add_filter('thwepo_extra_fields_display_position', 'th_extra_fields_display_position');

	function th_extra_fields_display_position($positions){

		return $positions;
	}

#### Default value

	array
	(
	    [woo_before_add_to_cart_button] => Before Add To Cart Button
	    [woo_after_add_to_cart_button] => After Add To Cart Button
	    [woo_single_variation_5] => Before Variation Data (for variable products)
	)

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_load_products

Override product selection dropdown options in display rules.

	apply_filters( "thwepo_load_products", array() );
	
Note: Set priority more than 10 for this filter.

#### Parameters

Array (empty)

#### Usage

	add_filter( "thwepo_load_products", 'th_override_product_selection_display_rules', 20 );

	function th_override_product_selection_display_rules($products){
		
		$products = array(
			0 => array(
				'id' => 10,
				'title' => 'Product 1'
			),
			1 => array(
				'id' => 11,
				'title' => 'Product 2'
			),		
		);

		return $products;
	}

#### Default value

Empty array - Load all products in store

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_load_products_cat

Override category selection dropdown options in display rules.

	apply_filters( "thwepo_load_products_cat", array() );

Note: Set priority more than 10 for this filter.

#### Parameters

Array

#### Usage

	add_filter('thwepo_load_products_cat', 'thwepo_change_category', 20);
	function thwepo_change_category($cat){
		$cat = array(
			0 => array('id' => 8, 'title' => 'Category name 1' ),
			1 => array('id' => 75, 'title' => 'Category name 2' ),
		);

		return $cat;
	}

#### Default value

Empty array

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_load_user_roles

Override user role selection dropdown options in display rules.

	apply_filters( "thwepo_load_user_roles", array() );

#### Parameters

Array

#### Usage

	add_filter('thwepo_load_user_roles', 'thwepo_add_user_roles', 11);
	function thwepo_add_user_roles($role){
		$role = array(
			0 => array('id' => 'role', 'title' => 'role_name' ),
		);

		return $role;
	}


#### Default value

Array of user roles.

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_extra_fields_for_diaplay_rules

Add / change field for field based rules in display rule tab.

	apply_filters('thwepo_extra_fields_for_diaplay_rules', array('quantity' => 'Product Quantity'));

#### Parameters

Array

#### Usage

	add_filter('thwepo_extra_fields_for_diaplay_rules', 'thwepo_add_new_field_conditions');
	function thwepo_add_new_conditions($conditions){
		$conditions = array('additional_field_name' => 'additional_field_title');

		return $conditions;
	}

#### Default value

	array('quantity' => 'Product Quantity')

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_show_filed_name_for_field_list_in_conditions_tab

For removing the field name displayed in the display rule tab of field based condition section. 

	apply_filters('thwepo_show_filed_name_for_field_list_in_conditions_tab', true);

#### Parameters

Boolean

#### Usage

	add_filter('thwepo_show_filed_name_for_field_list_in_conditions_tab', '__return_false');

#### Default value

True

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_debug_mode

Deliver unminified version of CSS & javascript files

	apply_filters('thwepo_debug_mode', false);

#### Parameters

Boolean

#### Usage

	add_filter('thwepo_debug_mode', '__return_true');

#### Default value

false

#### Location

	admin/class-thwepo-admin.php

### plugin_locale

Filter locale of plugin.

	apply_filters('plugin_locale', get_locale(), self::TEXT_DOMAIN);

#### Parameters

get_locale() - (string) The plugin's current locale.

self::TEXT_DOMAIN - (string) Text domain. Unique identifier for retrieving translated strings.

#### Usage

	add_filter('plugin_locale', 'th_override_locale', 10, 2);
	function th_override_locale($locale, $text_domain){

		return $locale;
	}

#### Default value

string

#### Location

	includes/class-thwepo-i18n.php




/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/public/class-thwepo-public.php:

### thwepo_enqueue_public_scripts

Filter loading of public script & style in WordPress pages.

	apply_filters('thwepo_enqueue_public_scripts', false);

#### Parameters

Boolean value

#### Usage

	add_filter('thwepo_enqueue_public_scripts', '__return_true');

#### Default value

False

#### Location

	public/class-thwepo-public.php

### thwepo_enqueue_script_in_footer

Load required javascript files in page footer.

	apply_filters( 'thwepo_enqueue_script_in_footer', true );

#### Parameters

Boolean

#### Usage

add_filter('thwepo_enqueue_script_in_footer', '__return_false');

#### Default value

true

#### Location

	public/class-thwepo-public.php

### thwepo_include_jquery_ui_i18n

Load jQuery UI i18n file for translation of jQuery UI elements.

	apply_filters('thwepo_include_jquery_ui_i18n', true);

#### Parameters

Boolean value

#### Usage

add_filter('thwepo_enqueue_script_in_footer', '__return_false');

#### Default value

true

#### Location

	public/class-thwepo-public.php

### thwepo_select2_i18n_languages

	apply_filters( 'thwepo_select2_i18n_languages', false);

Load languages files for select default messages & warning.

#### Parameters

Boolean value

#### Usage

add_filter('thwepo_select2_i18n_languages', '__return_true');

#### Default value

false

#### Location

	public/class-thwepo-public.php

### thwepo_date_picker_field_readonly

	apply_filters('thwepo_date_picker_field_readonly', true);

In default, the date picker field is read-only. That means no option to enter date field manually. To enable manually entering value, use this filter & return false.

#### Parameters

Boolean value

#### Usage

add_filter('thwepo_select2_i18n_languages', '__return_false');

#### Default value

true

#### Location

	public/class-thwepo-public.php

### thwepo_product_price_placeholder

	apply_filters('thwepo_product_price_placeholder', '');

Used for changing the place holder of the price in product page for **simple product**.

#### Parameters

None

#### Usage

	add_filter('thwepo_product_price_placeholder', 'thwepo_product_price_holder');
	function thwepo_product_price_holder(){
		$placeholder = '.class_name';

		return $placeholder;
	}

#### Default value

Empty string

#### Location

	public/class-thwepo-public.php

### thwepo_variable_product_price_placeholder

	apply_filters('thwepo_variable_product_price_placeholder', '');

Used for changing the place holder of the price in product page for **variable product**.

#### Parameters

None

#### Usage

	add_filter('thwepo_variable_product_price_placeholder', 'thwepo_variable_product_price_holder');
	function thwepo_variable_product_price_holder($placeholder){
		$placeholder = '.class_name';

		return $placeholder;
	}

#### Default value

Empty string

#### Location

	public/class-thwepo-public.php

### thwepo_loop_add_to_cart_link_hook_priority

	apply_filters('thwepo_loop_add_to_cart_link_hook_priority', 10);

Usefull for changing the add to cart link change hook priority.

#### Parameters

Number

#### Usage

	add_filter('thwepo_loop_add_to_cart_link_hook_priority', 'thwepo_change_cart_link_hook_priority');
	function thwepo_change_cart_link_hook_priority($priority){
		$priority = 100;
		return $priority;
	}

#### Default value

10

#### Location

	public/class-thwepo-public.php

### thwepo_display_hooks_priority

	apply_filters('thwepo_display_hooks_priority', 10);

Usefull for changing the priority of extra product option field display in product page.

#### Parameters

Number

#### Usage

	add_filter('thwepo_display_hooks_priority', 'thwepo_display_hooks_priority');
	function thwepo_display_hooks_priority($priority){
		$priority = 100;
		return $priority;
	}

#### Default value

10

#### Location

	public/class-thwepo-public.php

### thwepo_add_to_cart_validation_hook_priority

	apply_filters('thwepo_add_to_cart_validation_hook_priority', 99);

Usefull for changing the  priority of validation function in the hook.

#### Parameters

Number

#### Usage

	add_filter('thwepo_add_to_cart_validation_hook_priority', 'validation_hook_priority');
	function validation_hook_priority($priority){
		$priority = 100;
		return $priority;
	}

#### Default value

99

#### Location

	public/class-thwepo-public.php

### thwepo_before_calculate_totals_hook_priority

	apply_filters('thwepo_before_calculate_totals_hook_priority', 1);

Usefull for changing the priority of function applied in the hook `woocommerce_before_calculate_totals`.

#### Parameters

Number

#### Usage

	add_filter('thwepo_before_calculate_totals_hook_priority', 'before_calculate_totals_hook_priority');
	function before_calculate_totals_hook_priority($priority){
		$priority = 100;
		return $priority;
	}

#### Default value

1

#### Location

	public/class-thwepo-public.php

### thwepo_new_order_item_hook_priority

	apply_filters('thwepo_new_order_item_hook_priority', 10);

Usefull to set priority of hook (`woocommerce_new_order_item`) to add extra product option data as item meta in new order.

#### Parameters

Integer

#### Usage

	add_filter('thwepo_new_order_item_hook_priority', 'new_order_item_hook_priority');
	function new_order_item_hook_priority($priority){
		$priority = 100;
		return $priority;
	}

#### Default value

10

#### Location

	public/class-thwepo-public.php

### thwepo_before_mini_cart_hook_priority

	apply_filters('thwepo_before_mini_cart_hook_priority', 10);

Usefull for changing the priority of function applied in the hook `woocommerce_before_mini_cart`.

#### Parameters

Integer

#### Usage

	add_filter('thwepo_before_mini_cart_hook_priority', 'before_mini_cart_hook_priority');
	function before_mini_cart_hook_priority($priority){
		$priority = 100;
		return $priority;
	}

#### Default value

10

#### Location

	public/class-thwepo-public.php

### thwepo_add_cart_item_data_hook_priority

	apply_filters('thwepo_add_cart_item_data_hook_priority', 10);

Usefull for changing the priority of function applied in the hook `woocommerce_add_cart_item_data`.

#### Parameters

Integer

#### Usage

	add_filter('thwepo_add_cart_item_data_hook_priority', 'add_cart_item_data_hook_priority');
	function add_cart_item_data_hook_priority($priority){
		$priority = 100;
		return $priority;
	}

#### Default value

10

#### Location

	public/class-thwepo-public.php

### hook_name_before_single_product

	apply_filters('hook_name_before_single_product', 'woocommerce_before_single_product')

Usefull for changing the hook name that used to configure extra product option fields.

#### Parameters

String value

#### Usage

	add_filter('hook_name_before_single_product', 'hook_name_wepo_config');
	function hook_name_wepo_config($hook_name){
		$hook_name = 'hook_name';
		return $hook_name;
	}

#### Default value

woocommerce_before_single_product

#### Location

	public/class-thwepo-public.php

### hook_name_before_add_to_cart_button

	apply_filters('hook_name_before_add_to_cart_button', 'woocommerce_before_add_to_cart_button')

Usefull for changing the hook name that render extra product fields before add to cart button.

#### Parameters

String value

#### Usage

	add_filter('hook_name_before_add_to_cart_button', 'before_add_to_cart_button_hook_change');
	function before_add_to_cart_button_hook_change($hook_name){
		$hook_name = 'hook_name';
		return $hook_name;
	}

#### Default value

woocommerce_before_add_to_cart_button

#### Location

	public/class-thwepo-public.php

### hook_name_after_add_to_cart_button

	apply_filters('hook_name_after_add_to_cart_button', 'woocommerce_after_add_to_cart_button')

Usefull for changing the hook name that render extra product fields after add to cart button.

#### Parameters

String value

#### Usage

	add_filter('hook_name_after_add_to_cart_button', 'after_add_to_cart_button_hook_change');
	function after_add_to_cart_button_hook_change($hook_name){
		$hook_name = 'hook_name';
		return $hook_name;
	}

#### Default value

woocommerce_after_add_to_cart_button

#### Location

	public/class-thwepo-public.php

### thwepo_modify_loop_add_to_cart_link

	apply_filters('thwepo_modify_loop_add_to_cart_link', true);

Usefull to disable modification done by extra product option plugin in add to cart button in product loop pages like shop & category.

#### Parameters

Boolean value

#### Usage

	add_filter('thwepo_modify_loop_add_to_cart_link', '__return_false');

#### Default value

true

#### Location

	public/class-thwepo-public.php

### thwepo_ignore_unposted_fields ?????????

	apply_filters( 'thwepo_ignore_unposted_fields', false );

#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_skip_extra_options_for_bundled_items

	apply_filters('thwepo_skip_extra_options_for_bundled_items', true);

Usefull to enable/disable extra option for bundeled product.

#### Parameters

Boolean value

#### Usage

	add_filter('thwepo_skip_extra_options_for_bundled_items', '__return_false');

#### Default value

True

#### Location

	public/class-thwepo-public.php

### thwepo_set_unique_key_for_cart_item ?????

	apply_filters('thwepo_set_unique_key_for_cart_item', false, $cart_item_data, $product_id, $variation_id);

Usefull to creat unique key for cart item.

#### Parameters

$cart_item_data - object
$product_id - integer
$variation_id - integer

#### Usage

	add_filter('thwepo_set_unique_key_for_cart_item', 'unique_key_for_cart_item', 10, 4);
	function unique_key_for_cart_item($value, $cart_item_data, $product_id, $variation_id){

		return $value;
	}

#### Default value

False

#### Location

	public/class-thwepo-public.php

### thwepo_extra_cost_exclude_base_price

	apply_filters('thwepo_extra_cost_exclude_base_price', false, $product_id);

Exlude the base price of the product and only use extra cost.

#### Parameters

Boolean

Integer

#### Usage

	add_filter('thwepo_extra_cost_exclude_base_price', 'th34r_wepo_exclude_base_price', 10, 2);
	function th34r_wepo_exclude_base_price($value, $product_id){
		$value = true;

		return $value;
	}

#### Default value

False

#### Location

	public/class-thwepo-public.php

### thwepo_dynamic_pricing_display_price_excluding_extra_cost

	apply_filters('thwepo_dynamic_pricing_display_price_excluding_extra_cost', false);

Add compatibility for WooCommerce dynamic pricing plugin.

#### Parameters

Boolean

#### Usage

	add_filter('thwepo_dynamic_pricing_display_price_excluding_extra_cost', '__return_true');

#### Default value

False

#### Location

	public/class-thwepo-public.php

### thwepo_display_custom_cart_item_meta

	apply_filters('thwepo_display_custom_cart_item_meta', true);

Hide the extra product options data from cart item data. if returns false then the submitted extra product fields data will be hidden in cart & order review pages. But the submitted data will be saved as order item meta data & details will be visible in order details pages.

#### Parameters

Boolean

#### Usage

	add_filter('thwepo_display_custom_cart_item_meta', '__return_false');

#### Default value

True

#### Location

	public/class-thwepo-public.php

### thwepo_order_item_meta_display_option_text ????

	apply_filters('thwepo_order_item_meta_display_option_text', true);

#### Parameters

#### Usage


#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_item_display_filename_as_link

	apply_filters('thwepo_item_display_filename_as_link', false, $name);

Show uploaded file name (Uploaded by extra product option field) as link in cart & checkout.

#### Parameters

Boolean
String

#### Usage

	add_filter('thwepo_item_display_filename_as_link', 'th25e_show_uploaded_file_name_as_link', 20, 2);
	function th25e_show_uploaded_file_name_as_link($value, $field){

		if($field == 'your_field'){
			$value = True;
		}
		
		return $value;
	}

#### Default value

False

#### Location

	public/class-thwepo-public.php

### thwepo_show_price_for_item_meta

	apply_filters('thwepo_show_price_for_item_meta', true, $name);



#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_price_html

	apply_filters('thwepo_add_order_item_meta_price_html', $price_html, $name, $data);

Override additional price HTML in order item meta.

#### Parameters

$price_html - String
$name - String
$data - Array

#### Usage

	add_filter('thwepo_add_order_item_meta_price_html', 'th25e_order_item_meta_price_html', 20, 3);

	function th25e_order_item_meta_price_html($price_html, $name, $data){
		
		return $price_html;
	}

#### Default value

Field price HTML.

#### Location

	public/class-thwepo-public.php

### thwepo_show_price_for_order_formatted_meta

	apply_filters('thwepo_show_price_for_order_formatted_meta', true, $name);

Show / hide additional price added by extra product options plugin in order item meta.

#### Parameters

	add_filter('thwepo_show_price_for_order_formatted_meta', 'th34e_show_price_for_order_formatted_meta', 20, 2);
	function th34e_show_price_for_order_formatted_meta($value, $field){
		
		return $value;
	}

#### Usage

	add_filter('thwepo_show_price_for_order_formatted_meta', '__return_false');

#### Default value

True

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_value

	apply_filters('thwepo_add_order_item_meta_value', $value, $name, $display_value);

Filter value to be saved as order item meta.

#### Parameters

$value - Submitted value (String, Intiger etc as per field)
$name - String
$display_value - Formatted value of submitted data

#### Usage

	add_filter('thwepo_add_order_item_meta_value', 'th14r_update_order_item_meta_value', 20, 3);
	function th14r_update_order_item_meta_value($value, $name, $display_value){

		return $value;
	}

#### Default value

Formatted data.

#### Location

	public/class-thwepo-public.php

### thwepo_order_display_filename_as_link

	apply_filters('thwepo_order_display_filename_as_link', true, $meta->key);

Show uploaded file name (Uploaded by extra product option field) as link in order pages.

#### Parameters

Boolean
String

#### Usage

	add_filter('thwepo_order_display_filename_as_link', 'th25e_show_uploaded_file_name_as_link_order', 20, 2);
	function th25e_show_uploaded_file_name_as_link_order($value, $field){

		if($field == 'your_field'){
			$value = True;
		}
		
		return $value;
	}


#### Default value

True

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_price_meta_key_prefix

	apply_filters('thwepo_add_order_item_price_meta_key_prefix', '_thwepoprice_');

Filter meta key prefix of meta key that save price field value.

#### Parameters

String

#### Usage

	add_filter('thwepo_add_order_item_price_meta_key_prefix', 'th256t_order_item_price_meta_key_prefix', 10); 
	function th256t_order_item_price_meta_key_prefix($prefix){
		$prefix = '_new_prefix_';

		return $prefix;
	}

#### Default value

_thwepoprice_

#### Location

	public/class-thwepo-public.php

### thwepo_product_price_html

	apply_filters('thwepo_product_price_html', $price_html, $product_id);

#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_extra_cart_item_data

	apply_filters('thwepo_extra_cart_item_data', $extra_data);

Filter cart item data added by extra product option.

#### Parameters

Array

#### Usage

	add_filter('thwepo_extra_cart_item_data', 'th265_extra_cart_item_data', 10); 
	function th265_extra_cart_item_data($extra_data){

		return $extra_data;
	}

#### Default value

Array as per submitted fields

#### Location

	public/class-thwepo-public.php

### thwepo_file_upload_maxsize

	apply_filters('thwepo_file_upload_maxsize', $field->get_property('maxsize'), $name);

#### Parameters

#### Usage

add_filter('thwepo_file_upload_maxsize', 'file_upload_maxsize', 10, 2); 
function file_upload_maxsize($maxsize, $name){
	$maxsize =  New size // upload size

	return $maxsize;
}

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_file_upload_accepted_file_types

	apply_filters('thwepo_file_upload_accepted_file_types', $field->get_property('accept'), $name);

#### Parameters

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php







/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils-field.php:

### thwepo_show_field

	apply_filters('thwepo_show_field', $show, $field->name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_field_options

	apply_filters('thwepo_field_options', array(), $field->get_property('name'));

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_product_extra_option_value_$name

	apply_filters('thwepo_product_extra_option_value_'.$name, $field->get_property('value'));

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_enable_html5_required_validation

	apply_filters('thwepo_enable_html5_required_validation', true, $name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_skip_translation_for_numeric_field_options

	apply_filters('thwepo_skip_translation_for_numeric_field_options', true, $name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_input_field_options

	apply_filters('thwepo_input_field_options', $field->get_property('options'), $name)

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_required_html

	apply_filters( 'thwepo_required_html', ' <abbr class="required" title="'.$title_required.'">*</abbr>', $field->get_property('name') );

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_display_prefix

	apply_filters('thwepo_extra_cost_display_prefix', ' (', $name, $price, $price_type);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_display_suffix

	apply_filters('thwepo_extra_cost_display_suffix', ')', $name, $price, $price_type);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_price_percentage_symbol

	apply_filters('thwepo_extra_price_percentage_symbol', '%', $field);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_unit_label_$name

	apply_filters('thwepo_extra_cost_unit_label_'.$name, '/'.$price_unit.' unit', $price_unit);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_unit_price_$name

	apply_filters('thwepo_extra_cost_unit_price_'.$name, $price, $product_price, $price_type);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_display_field_price

	apply_filters('thwepo_display_field_price', $show_price, $field->get_property('name'), $field->get_property('type'));

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_enable_html5_required_validation

	apply_filters('thwepo_enable_html5_required_validation', true, $name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_checkbox_field_label_wrap

	apply_filters('thwepo_checkbox_field_label_wrap', true, $name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_display_field_option_price

	apply_filters('thwepo_display_field_option_price', true, $name, $field->get_property('type'));

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_checkboxgroup_options_per_line

	apply_filters('thwepo_checkboxgroup_options_per_line', 1, $name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_date_picker_first_day

	apply_filters('thwepo_date_picker_first_day', 0, $name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_date_picker_display_inline

	apply_filters('thwepo_date_picker_display_inline', false, $name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php










/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils-price.php:


### thwepo_extra_cost_exclude_base_price

	apply_filters('thwepo_extra_cost_exclude_base_price', false, $product_id);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_exclude_base_price_single

	apply_filters('thwepo_extra_cost_exclude_base_price_single', $exclude_base_price, $product_id, $fname);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_show_product_price_suffix

	apply_filters('thwepo_show_product_price_suffix', true, $product);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_price

	apply_filters('thwepo_product_price', $price, $product, $is_default);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_field_price

	apply_filters('thwepo_product_field_price', $price, $price_type, $name, $price_info, $index);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_quantity

	apply_filters('thwepo_extra_cost_quantity', $quantity, $name, $value);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_unit_price_$name

	apply_filters('thwepo_extra_cost_unit_price_'.$name, $price, $product_price, $price_type);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_unit_price

	apply_filters('thwepo_extra_cost_unit_price', $price, $name, $product_price, $price_type);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_unit_price_type_range_$name

	apply_filters('thwepo_extra_cost_unit_price_type_range_'.$name, false);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_field_extra_cost_$name

	apply_filters('thwepo_product_field_extra_cost_'.$name, $fprice, $product_price, $price_info);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_field_extra_cost

	apply_filters('thwepo_product_field_extra_cost', $fprice, $name, $price_info, $product_info);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_item_meta_price_prefix

	apply_filters('thwepo_item_meta_price_prefix', ' (', $name, $price, $data);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_item_meta_price_suffix

	apply_filters('thwepo_item_meta_price_suffix', ')', $name, $price, $data);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_item_meta_display_price

	apply_filters('thwepo_item_meta_display_price', $price_html, $name, $data);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price_sign

	apply_filters('thwepo_extra_option_display_price_sign', $price_sign, $unformatted_price, $field);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price

	apply_filters('thwepo_extra_option_display_price', $return, $price, $unformatted_price, $field);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price_formatted

	apply_filters('thwepo_extra_option_display_price_formatted', $return, $price, $unformatted_price, $field);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price_plain

	apply_filters('thwepo_extra_option_display_price_plain', $return, $price, $unformatted_price, $field);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:



/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils-section.php:

### thwepo_show_section

	apply_filters('thwepo_show_section', $show, $section->name);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-section.php




/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils.php:

### thwepo_advanced_settings

	apply_filters('thwepo_advanced_settings', $settings);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_ignore_wpml_translation_for_product_category

Disable translation of category slug.

	apply_filters('thwepo_ignore_wpml_translation_for_product_category', false);

#### Parameters

Boolean value

#### Usage

	add_filter('thwepo_ignore_wpml_translation_for_product_category', '__return_true');

#### Default value

false

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_file_upload_path

	apply_filters('thwepo_file_upload_path', $path);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_uploads_use_unique_folders

	apply_filters('thwepo_uploads_use_unique_folders', true);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_uploads_use_yearmonth_folders

	apply_filters('thwepo_uploads_use_yearmonth_folders', false);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_upload_path

	apply_filters('thwepo_upload_path', '/thwepo_uploads/');

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_woo_dynamic_pricing_plugin_enabled

	apply_filters('thwepo_woo_dynamic_pricing_plugin_enabled', $active);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_rightpress_dynamic_pricing_plugin_enabled

	apply_filters('thwepo_rightpress_dynamic_pricing_plugin_enabled', $active);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_is_quick_view_plugin_active

	apply_filters('thwepo_is_quick_view_plugin_active', $quick_view);

#### Parameters

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php
