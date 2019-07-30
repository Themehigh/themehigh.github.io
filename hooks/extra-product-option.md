---
layout: post
title:  Hooks - Extra Product Option Pro
---

* Table of content. Use {:.no_toc} to escape some heading
{:toc}

## Filter hooks

### thwepo_extra_fields_display_position

	apply_filters('thwepo_extra_fields_display_position', $positions);

#### Usage

#### Default value

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_load_products

	apply_filters( "thwepo_load_products", array() );

#### Usage

#### Default value

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_load_products_cat

	apply_filters( "thwepo_load_products_cat", array() );

#### Usage

#### Default value

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_load_user_roles

	apply_filters( "thwepo_load_user_roles", array() );

#### Usage

#### Default value

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_extra_fields_for_diaplay_rules

	apply_filters('thwepo_extra_fields_for_diaplay_rules', array('quantity' => 'Product

#### Usage

#### Default value

#### Location

	admin/class-thwepo-admin-settings-general.php

### thwepo_show_filed_name_for_field_list_in_conditions_tab

	apply_filters('thwepo_show_filed_name_for_field_list_in_conditions_tab', true);

#### Usage

#### Default value

#### Location

	admin/class-thwepo-admin-settings-general.php









/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/admin/class-thwepo-admin.php:

### thwepo_debug_mode

	apply_filters('thwepo_debug_mode', false);

#### Usage

#### Default value

#### Location

	admin/class-thwepo-admin.php




/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/class-thwepo-i18n.php:

### plugin_locale

	apply_filters('plugin_locale', get_locale(), self::TEXT_DOMAIN);

#### Usage

#### Default value

#### Location

	includes/class-thwepo-i18n.php




/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/public/class-thwepo-public.php:

### thwepo_enqueue_public_scripts

	apply_filters('thwepo_enqueue_public_scripts', false);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_debug_mode

	apply_filters('thwepo_debug_mode', false);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_enqueue_script_in_footer

	apply_filters( 'thwepo_enqueue_script_in_footer', true );

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_include_jquery_ui_i18n

	apply_filters('thwepo_include_jquery_ui_i18n', true);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_select2_i18n_languages

	apply_filters( 'thwepo_select2_i18n_languages', false);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_date_picker_field_readonly

	apply_filters('thwepo_date_picker_field_readonly', true);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_product_price_placeholder

	apply_filters('thwepo_product_price_placeholder', '');

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_variable_product_price_placeholder

	apply_filters('thwepo_variable_product_price_placeholder', '');

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_loop_add_to_cart_link_hook_priority

	apply_filters('thwepo_loop_add_to_cart_link_hook_priority', 10);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_display_hooks_priority

apply_filters('thwepo_display_hooks_priority', 10);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_to_cart_validation_hook_priority

	apply_filters('thwepo_add_to_cart_validation_hook_priority', 99);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_before_calculate_totals_hook_priority

	apply_filters('thwepo_before_calculate_totals_hook_priority', 1);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_new_order_item_hook_priority

	apply_filters('thwepo_new_order_item_hook_priority', 10);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_before_mini_cart_hook_priority

	apply_filters('thwepo_before_mini_cart_hook_priority', 10);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_cart_item_data_hook_priority

	apply_filters('thwepo_add_cart_item_data_hook_priority', 10);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### hook_name_before_single_product

	apply_filters('hook_name_before_single_product', 'woocommerce_before_single_product')

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### hook_name_before_add_to_cart_button

	apply_filters('hook_name_before_add_to_cart_button', 'woocommerce_before_add_to_cart_button')

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### hook_name_after_add_to_cart_button

	apply_filters('hook_name_after_add_to_cart_button', 'woocommerce_after_add_to_cart_button')

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_modify_loop_add_to_cart_link

	apply_filters('thwepo_modify_loop_add_to_cart_link', true);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_ignore_unposted_fields

	apply_filters( 'thwepo_ignore_unposted_fields', false );

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_skip_extra_options_for_bundled_items

	apply_filters('thwepo_skip_extra_options_for_bundled_items', true);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_set_unique_key_for_cart_item

	apply_filters('thwepo_set_unique_key_for_cart_item', false, $cart_item_data, $product_id, $variation_id);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_cart_item_extra_cost

	apply_filters('thwepo_cart_item_extra_cost', $extra_price, $cart_item);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_extra_cost_exclude_base_price

	apply_filters('thwepo_extra_cost_exclude_base_price', false, $product_id);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_dynamic_pricing_display_price_excluding_extra_cost

	apply_filters('thwepo_dynamic_pricing_display_price_excluding_extra_cost', false);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_display_custom_cart_item_meta

	apply_filters('thwepo_display_custom_cart_item_meta', true);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_order_item_meta_display_option_text

	apply_filters('thwepo_order_item_meta_display_option_text', true);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_item_display_filename_as_link

	apply_filters('thwepo_item_display_filename_as_link', false, $name);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_show_price_for_item_meta

	apply_filters('thwepo_show_price_for_item_meta', true, $name);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_price_html

	apply_filters('thwepo_add_order_item_meta_price_html', $price_html, $name, $data);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_show_price_for_order_formatted_meta

	apply_filters('thwepo_show_price_for_order_formatted_meta', true, $name);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_value

	apply_filters('thwepo_add_order_item_meta_value', $value, $name, $display_value);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_price_html

	apply_filters('thwepo_add_order_item_meta_price_html', $price_html, $name, $data);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_show_price_for_order_formatted_meta

	apply_filters('thwepo_show_price_for_order_formatted_meta', true, $name);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_value

	apply_filters('thwepo_add_order_item_meta_value', $value, $name, $display_value);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_price_html

	apply_filters('thwepo_add_order_item_meta_price_html', $price_html, $name, $data);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_show_price_for_order_formatted_meta

	apply_filters('thwepo_show_price_for_order_formatted_meta', true, $name);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_meta_value

	apply_filters('thwepo_add_order_item_meta_value', $value, $name, $display_value)

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_order_item_meta_display_option_text

	apply_filters('thwepo_order_item_meta_display_option_text', true);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_order_display_filename_as_link

	apply_filters('thwepo_order_display_filename_as_link', true, $meta->key)

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_show_price_for_order_formatted_meta

	apply_filters('thwepo_show_price_for_order_formatted_meta', true, $meta->key);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### woocommerce_order_item_display_meta_key

	apply_filters( 'woocommerce_order_item_display_meta_key', $display_key, $meta, $order_item );

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### woocommerce_order_item_display_meta_value

	apply_filters( 'woocommerce_order_item_display_meta_value', $display_value, $meta, $order_item );

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_add_order_item_price_meta_key_prefix

	apply_filters('thwepo_add_order_item_price_meta_key_prefix', '_thwepoprice_');

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_product_price_html

	apply_filters('thwepo_product_price_html', $price_html, $product_id);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_extra_cart_item_data

	apply_filters('thwepo_extra_cart_item_data', $extra_data);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_file_upload_maxsize

	apply_filters('thwepo_file_upload_maxsize', $field->get_property('maxsize'), $name);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php

### thwepo_file_upload_accepted_file_types

	apply_filters('thwepo_file_upload_accepted_file_types', $field->get_property('accept'), $name);

#### Usage

#### Default value

#### Location

	public/class-thwepo-public.php







/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils-field.php:

### thwepo_show_field

	apply_filters('thwepo_show_field', $show, $field->name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_field_options

	apply_filters('thwepo_field_options', array(), $field->get_property('name'));

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_product_extra_option_value_$name

	apply_filters('thwepo_product_extra_option_value_'.$name, $field->get_property('value'));

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_enable_html5_required_validation

	apply_filters('thwepo_enable_html5_required_validation', true, $name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_skip_translation_for_numeric_field_options

	apply_filters('thwepo_skip_translation_for_numeric_field_options', true, $name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_input_field_options

	apply_filters('thwepo_input_field_options', $field->get_property('options'), $name)

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_required_html

	apply_filters( 'thwepo_required_html', ' <abbr class="required" title="'.$title_required.'">*</abbr>', $field->get_property('name') );

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_display_prefix

	apply_filters('thwepo_extra_cost_display_prefix', ' (', $name, $price, $price_type);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_display_suffix

	apply_filters('thwepo_extra_cost_display_suffix', ')', $name, $price, $price_type);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_price_percentage_symbol

	apply_filters('thwepo_extra_price_percentage_symbol', '%', $field);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_unit_label_$name

	apply_filters('thwepo_extra_cost_unit_label_'.$name, '/'.$price_unit.' unit', $price_unit);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_extra_cost_unit_price_$name

	apply_filters('thwepo_extra_cost_unit_price_'.$name, $price, $product_price, $price_type);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_display_field_price

	apply_filters('thwepo_display_field_price', $show_price, $field->get_property('name'), $field->get_property('type'));

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_enable_html5_required_validation

	apply_filters('thwepo_enable_html5_required_validation', true, $name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_checkbox_field_label_wrap

	apply_filters('thwepo_checkbox_field_label_wrap', true, $name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_display_field_option_price

	apply_filters('thwepo_display_field_option_price', true, $name, $field->get_property('type'));

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_checkboxgroup_options_per_line

	apply_filters('thwepo_checkboxgroup_options_per_line', 1, $name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_date_picker_first_day

	apply_filters('thwepo_date_picker_first_day', 0, $name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php

### thwepo_date_picker_display_inline

	apply_filters('thwepo_date_picker_display_inline', false, $name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-field.php










/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils-price.php:


### thwepo_extra_cost_exclude_base_price

	apply_filters('thwepo_extra_cost_exclude_base_price', false, $product_id);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_exclude_base_price_single

	apply_filters('thwepo_extra_cost_exclude_base_price_single', $exclude_base_price, $product_id, $fname);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_show_product_price_suffix

	apply_filters('thwepo_show_product_price_suffix', true, $product);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_price

	apply_filters('thwepo_product_price', $price, $product, $is_default);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_field_price

	apply_filters('thwepo_product_field_price', $price, $price_type, $name, $price_info, $index);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_quantity

	apply_filters('thwepo_extra_cost_quantity', $quantity, $name, $value);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_unit_price_$name

	apply_filters('thwepo_extra_cost_unit_price_'.$name, $price, $product_price, $price_type);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_unit_price

	apply_filters('thwepo_extra_cost_unit_price', $price, $name, $product_price, $price_type);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_cost_unit_price_type_range_$name

	apply_filters('thwepo_extra_cost_unit_price_type_range_'.$name, false);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_field_extra_cost_$name

	apply_filters('thwepo_product_field_extra_cost_'.$name, $fprice, $product_price, $price_info);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_product_field_extra_cost

	apply_filters('thwepo_product_field_extra_cost', $fprice, $name, $price_info, $product_info);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_item_meta_price_prefix

	apply_filters('thwepo_item_meta_price_prefix', ' (', $name, $price, $data);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_item_meta_price_suffix

	apply_filters('thwepo_item_meta_price_suffix', ')', $name, $price, $data);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_item_meta_display_price

	apply_filters('thwepo_item_meta_display_price', $price_html, $name, $data);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price_sign

	apply_filters('thwepo_extra_option_display_price_sign', $price_sign, $unformatted_price, $field);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price

	apply_filters('thwepo_extra_option_display_price', $return, $price, $unformatted_price, $field);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price_formatted

	apply_filters('thwepo_extra_option_display_price_formatted', $return, $price, $unformatted_price, $field);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:

### thwepo_extra_option_display_price_plain

	apply_filters('thwepo_extra_option_display_price_plain', $return, $price, $unformatted_price, $field);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-price.php:



/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils-section.php:

### thwepo_show_section

	apply_filters('thwepo_show_section', $show, $section->name);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils-section.php




/var/www/html/wootest/wp-content/plugins/woocommerce-extra-product-options-pro/includes/utils/class-thwepo-utils.php:

### thwepo_advanced_settings

	apply_filters('thwepo_advanced_settings', $settings);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_ignore_wpml_translation_for_product_category

	apply_filters('thwepo_ignore_wpml_translation_for_product_category', false);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_file_upload_path

	apply_filters('thwepo_file_upload_path', $path);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_uploads_use_unique_folders

	apply_filters('thwepo_uploads_use_unique_folders', true);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_uploads_use_yearmonth_folders

	apply_filters('thwepo_uploads_use_yearmonth_folders', false);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_upload_path

	apply_filters('thwepo_upload_path', '/thwepo_uploads/');

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_woo_dynamic_pricing_plugin_enabled

	apply_filters('thwepo_woo_dynamic_pricing_plugin_enabled', $active);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_rightpress_dynamic_pricing_plugin_enabled

	apply_filters('thwepo_rightpress_dynamic_pricing_plugin_enabled', $active);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php

### thwepo_is_quick_view_plugin_active

	apply_filters('thwepo_is_quick_view_plugin_active', $quick_view);

#### Usage

#### Default value

#### Location

	includes/utils/class-thwepo-utils.php
