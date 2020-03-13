---
layout: post
title:  Repeat field or section based on product quantity of a specific category - WooCommerce Checkout Field Editor Pro
categories: WCFE
---

If you need to repeat a field or section based on quantity of products in a specific category, you can use below code snippet.

	add_filter('thwcfe_repeat_times', 'th27mb_override_repeat_count', 10, 3);
	function th27mb_override_repeat_count($rt, $name, $type){
		global $woocommerce;
		$count = array();
		$cart_object = WC()->cart->get_cart();
		$category = 'accessories'; // category slug

		if($cart_object){
			foreach($cart_object as $cart_item ) {
				if(has_term( $category, 'product_cat', $cart_item['product_id'])){
					$qty =  $cart_item['quantity'];
					array_push($count,$qty);
				}
			}
		}
		
		if(empty($count)){
			return $rt;
		}
		
		if($type == 'field'){
			
			if($name === 'test_field'){ // update field name
				$rt = array_sum($count);
			}
			
		}elseif($type == 'section'){

			if($name === 'test_section'){ // update section name
				$rt = array_sum($count);
			}
			
		}
		
		return $rt;
	}
