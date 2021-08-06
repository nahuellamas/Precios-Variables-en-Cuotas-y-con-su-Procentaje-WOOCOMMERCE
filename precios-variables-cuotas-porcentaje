<?php

/**
 * Precio en cuotas variables y % de descuento
 */
add_filter('woocommerce_available_variation', 'variation_price_custom_suffix', 10, 3 );
function variation_price_custom_suffix( $variation_data, $product, $variation ) {
	
	//print_r(array_keys($variation_data)); // muestra los valores del array
	$sale_price_variation = $variation_data['display_price'];
	$regular_price_variation = $variation_data['display_regular_price'];
	
	$saving_percentage = round ( ( ( ( $sale_price_variation * 100 ) / $regular_price_variation ) - 100 ) * -1 , 0 ) . '%';
	$cuotas_variation = round ( ( $sale_price_variation / 18 ), 0 );
	
    $variation_data['price_html'] .= sprintf( __('<p class="saved-sale"> <b> 18 CUOTAS SIN INTERES DE <em>$%s</em> - 🔥%s OFF ctdo🔥 </b> </p>', 'woocommerce' ), $cuotas_variation,  $saving_percentage );
	

    return $variation_data;
}
