(function($, window, document, undefined) {
	'use strict';

	var gridContainer = $( '.grid-items' ),
		filtersContainer = $( '.grid-filters' ),
		wrap, filtersCallback;  

	gridContainer.each( function() {
	
		var $grid = $(this);
	
		var layoutMode = 'grid';
		
		if ( $grid.data('layout') == 'mosaic' ) {
			layoutMode = 'mosaic';
		} else if ( $grid.data( 'layout' ) == 'masonry' ) {
			layoutMode = 'masonry';
		}

		var cols = 3;
		var colsTablet = 2;
		var colsMobile = 1;
		
		if ( $grid.data( 'cols' ) ) cols = $grid.data( 'cols' );
		if ( $grid.data( 'cols-tablet' ) ) colsTablet = $grid.data( 'cols-tablet' );
		if ( $grid.data( 'cols-mobile' ) ) colsMobile = $grid.data( 'cols-mobile' );
		
		$grid.cubeportfolio({
	        filters: '#'+$(this).data('filters'),
	        loadMore: '#loadMore-container1',
	        loadMoreAction: 'click',
	        layoutMode: layoutMode,
	        sortToPreventGaps: true,
	        defaultFilter: '*',
	        animationType: $(this).data('animation'),
	        gapHorizontal: $(this).data('item-gap'),
	        gapVertical: $(this).data('item-gap'),
	        gridAdjustment: 'responsive',
	        mediaQueries: [
	        	{ width: 1000, cols: cols },
	        	{ width: 690, cols: colsTablet },
	        	{ width: 1, cols: colsMobile },
	        ],
	        caption: '',
	        //displayType: 'sequentially',
	        displayTypeSpeed: 80,
	
	        // lightbox
	        lightboxDelegate: '.cbp-image-lightbox',
	        lightboxGallery: true,
	        lightboxTitleSrc: 'data-title',
	        lightboxCounter: '<div class="cbp-popup-lightbox-counter">{{current}} of {{total}}</div>',

    	});
    	
    	$grid.on( 'initComplete.cbp', function() {
    		$(this).css({ 'opacity' : 1 });
    	});
    
    });
    
    // Blog Masonry
    
    var blogMasonryContainer = $( '.blog-style-masonry' ),
		wrap, filtersCallback;  

	blogMasonryContainer.each( function() {
	
		var $grid = $(this);
	
		var layoutMode = 'grid';

		var cols = 3;
		var colsTablet = 2;
		var colsMobile = 1;
		
		if ( $grid.data( 'cols' ) ) cols = $grid.data( 'cols' );
		if ( $grid.data( 'cols-tablet' ) ) colsTablet = $grid.data( 'cols-tablet' );
		if ( $grid.data( 'cols-mobile' ) ) colsMobile = $grid.data( 'cols-mobile' );
		
		$grid.cubeportfolio({
	        filters: '#'+$(this).data('filters'),
	        loadMore: '#loadMore-container1',
	        loadMoreAction: 'click',
	        layoutMode: layoutMode,
	        sortToPreventGaps: true,
	        defaultFilter: '*',
	        animationType: $(this).data('animation'),
	        gapHorizontal: $(this).data('item-gap'),
	        gapVertical: $(this).data('item-gap'),
	        gridAdjustment: 'responsive',
	        mediaQueries: [
	        	{width: 1000, cols: cols},
	        	{width: 768, cols: colsTablet},
	        	{width: 1, cols: colsMobile},
	        ],
	        caption: '',
	        //displayType: 'sequentially',
	        displayTypeSpeed: 80,
	
	        // lightbox
	        lightboxDelegate: '.cbp-image-lightbox',
	        lightboxGallery: true,
	        lightboxTitleSrc: 'data-title',
	        lightboxCounter: '<div class="cbp-popup-lightbox-counter">{{current}} of {{total}}</div>',

    	});
    	
    	$grid.on( 'initComplete.cbp', function() {
    	
    		if ( typeof handleVideo !== "undefined") { 
    			handleVideo();
    		}
    		
    	    // your functionality
    	    
    	    //engage_swiper_slider();
    	    $grid.cubeportfolio( 'layout', function() {
    	    	console.log( 'relayouting' );
    	    } );
    	    //console.log( 'hi' );
    	});
    	
    	$grid.on( 'pluginResize.cbp', function() {
    		$grid.cubeportfolio( 'layout' );
    	});
    
    });
    
    $(window).on( 'resize', function() {
    	blogMasonryContainer.cubeportfolio( 'layout' );
    });
   	

})(jQuery, window, document);