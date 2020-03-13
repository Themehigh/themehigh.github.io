---
layout: post
title:  Repeat field or section based on largest quantity of product in cart items  - WooCommerce Checkout Field Editor Pro
categories: jekyll update
---

If you need to repeat a field or section, you can add repeat rule in field or section settings.

Recently there is a request to modify the repeat count based on the largest quantity of product in cart items.

	add_filter('thwcfe_repeat_times', 'th34ed_override_repeat_count', 10, 3);
	function th34ed_override_repeat_count($rt, $name, $type){
		global $woocommerce;
		$cart_count = array();
		$cart_object = WC()->cart->get_cart();

		if($cart_object){
			foreach($cart_object as $cart_item ) {
				$qty =  $cart_item['quantity'];
				array_push($cart_count,$qty);
			}
		}
		
		if(empty($cart_count)){
			return $rt;
		}
		
		if($type == 'field'){
			
			if($name === 'test_field'){ // update your field name
				$rt = max($cart_count);
			}
			
		}elseif($type == 'section'){

			if($name === 'test_section'){ // update your section name
				$rt = max($cart_count);
			}
			
		}
		
		return $rt;
	}
