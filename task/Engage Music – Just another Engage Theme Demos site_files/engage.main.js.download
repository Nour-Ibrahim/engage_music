( function($) {

	// Useful Variables
	 
	var $window             = $(window);
	var body                = $('body');
	var wrapper             = $('#wrapper');
	var pageTitleResized		= false;
	
	// Window resize actions
	
	$(window).resize(function() {
	    'use strict';
	
	    pageTitle();
	    adjustSidebarHeight();
	    
	    if ( $( '.col-has-padding' ).length > 0 ) {
	    	columnPadding();
	    }
	    
	});
	
	// Main actions

	( function() {
	
	    'use strict';
	
	    var isMobile = {
	        Android: function() {
	            return navigator.userAgent.match(/Android/i);
	        },
	        BlackBerry: function() {
	            return navigator.userAgent.match(/BlackBerry/i);
	        },
	        iOS: function() {
	            return navigator.userAgent.match(/iPhone|iPad|iPod/i);
	        },
	        Opera: function() {
	            return navigator.userAgent.match(/Opera Mini/i);
	        },
	        Windows: function() {
	            return navigator.userAgent.match(/IEMobile/i);
	        },
	        any: function() {
	            return (isMobile.Android() || isMobile.BlackBerry() || isMobile.iOS() || isMobile.Opera() || isMobile.Windows());
	        }
	    };
	    
	    var isMobileDev = false;
	    
	    if( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) ) {
	    	isMobileDev = true;
	    }
	    
	    
	    // FadeIn big images
	    
	    handleBGImages();
	    
	    // Handle Search
	    
	    handleSearch();
	    
	    // When rows loaded
	    
	    jQuery(document).on( 'vc-full-width-row', function() {
	    	
	    	if ( $('body').hasClass( 'rtl' ) ) { // is RTL
	    		$( '.vc_row' ).each( function() {
	    			var offset = $(this).css( 'left' );
	    			$(this).css({ 'right' : offset }); 			
	    		});
	    	}
	    	
	    	if ( $('.loader-wrapper').length > 0 ) {
	    		var timeout = 100;
	    		
	    		if ( $( '.grid-items' ).length > 0 ) timeout = 300;
	    		
	    		setTimeout( function() {
	    			$('.loader-wrapper').addClass('loaded');
	    		}, timeout ); // give it few more miliseconds for a better effect

	    	}
	    });
	    
	    jQuery(document).ready(function() {
	    
	    	if ( $('.loader-wrapper').length > 0 && $('.vc_row').length === 0 ) {
	    		setTimeout( function() {
	    		  $('.loader-wrapper').addClass('loaded');
	    		}, 100 );
	    	}
	    
	    	if ( $( '.col-has-padding' ).length > 0 ) {
	    		columnPadding();
	    	}
	    	// Video Background
	    	
	    	if ( $('.bgndVideo').length > 0 && isMobileDev == false ) {
	    	
	    	    $(".bgndVideo").each( function() {
	    	    	$(this).YTPlayer();
	    	    });
	    	}
	    	
	    	// Magnific Popup
	    	
	    	if ( $.fn.magnificPopup ) { 
	    	
			    $('.mp-gallery').magnificPopup({
			        delegate: 'a', // the selector for gallery item
			        type: 'image',
			        gallery: {
			          enabled:true
			        }
			    });
			    
			    $('.mp-single').magnificPopup({
			        type: 'image',
			    });
			    
			    $('.mp-video').magnificPopup({
			        type: 'iframe',
			    });
			    
			    $('.grid-gallery').magnificPopup({
			        type: 'image',
			        gallery: {
			          enabled:true
			        }
			    });
			    
			}
			
			// Fullwidth section
			
			$( '.fullwidth-section' ).each( function() {
			
				$(this).closest( '.vc_row' ).addClass( 'vc_row-fullwidth' );
			
			});
			
			// Fullscreen Section
			
			if( $('.fullscreen-section').length ) {
				
				var $height = $(window).height();
				var $extra = 0;
				
				if ( $('#wpadminbar').length ) {
					$extra = $extra + 32;
				}
				
				if ( jQuery('#topbar').length > 0 ) {
					$extra = $extra + jQuery('#topbar').height();
				}
				
				$('.veented-slider-holder.veented-slider-fullscreen,.veented-slider-holder.veented-slider-fullscreen .veented-slider-container,.fullscreen-section,.fullscreen-section .hero-container').css( 'height', $height - $extra );
				
				jQuery(window).resize(function () {
					var $height = $(window).height();
					if( $height > 400 ) {
						$( '.veented-slider-holder.veented-slider-fullscreen, .veented-slider-holder.veented-slider-fullscreen .veented-slider-container, .fullscreen-section,.fullscreen-section .hero-container' ).css( 'height', $height - $extra );
					}
	
				});
				
			}
			
			// Button Scroll After
			
			if ( $('.veented-scroll-after').length > 0 ) {
			
			    $(".veented-scroll-after").on( 'click', function() {
			    	var parent = $(this).closest( '.vntd-section' );
			    	var parentHeight = parent.height();
	    			var headerH = jQuery( '#header' ).outerHeight();
	
					jQuery('html,body').stop().animate({ 
						scrollTop: parent.offset().top + parentHeight - headerH + "px"
					}, 1200);
					event.preventDefault();
	
			    });
			}
			
			// Button Scroll After
					
			if ( $('.scroll-after').length > 0 ) {
			
			    $(".scroll-after").on( 'click', function() {
			    	var parent = $(this).closest( '.vc_row.vc_row-stretch' );
			    	var parentHeight = parent.outerHeight();
	    			var headerH = jQuery( '#header' ).outerHeight();
	
					jQuery('html,body').stop().animate({ 
						scrollTop: parent.offset().top + parentHeight - headerH + "px"
					}, 1200, "swing");
					event.preventDefault();
	
			    });
			}
			
			// Simple animations
			
			$( '.vntd-animated' ).appear(function() {
			
			    var elem = $(this);
			    var animation = elem.data( 'animation' );		
			    
			    if ( !animation ) {
			    	animation = 'moveUp';
			    }
			    
			    if ( !elem.hasClass( 'visible' ) ) {
			    	
			       	var animationDelay = elem.data( 'animation-delay' );
			       	if ( !animationDelay ) animationDelay = 200;
			       	
			       	if ( elem.hasClass( 'animated-delay1' ) ) {
			       		animationDelay = 200;
			       	} else if ( elem.hasClass( 'animated-delay2' ) ) {
			       		animationDelay = 300;
			       	} else if ( elem.hasClass( 'animated-delay3' ) ) {
			       		animationDelay = 400;
			       	} else if ( elem.hasClass( 'animated-delay4' ) ) {
			       		animationDelay = 500;
			       	}
			       	
			       	if ( elem.hasClass( 'animated-moveUpShort' ) ) {
			       		animation = 'moveUpShort';
			       	} else if ( elem.hasClass( 'animated-moveRightShort' ) ) {
			       		animation = 'moveRightShort';
			       	} else if ( elem.hasClass( 'animated-moveLeftShort' ) ) {
			       		animation = 'moveLeftShort';
			       	}
			       	
			       	setTimeout( function(){
			       	    elem.addClass( animation + " visible" );
			       	}, animationDelay );
			        
			    }
			    
			});
	    	
	    });
	    
	    pageTitle();
	    scrollTop();
	    handleLinks();
    
	}());
	
	// Page Title Vertical Align
	
	function pageTitle(){
		if ( $(window).width() >= 1000 && pageTitleResized == false ) {
		    $('#page-title').each(function() {
		    	var marginTop = 55;
		    	var extra = 0;
		    	var titleInner = $(this).find( '.page-title-inner' );
		    	var titleInnerHeight = titleInner.height();
		    	
		    	if( $('#header').length ) {
		    		extra = 90 / 2;
		    	}
		    	if( $('#topbar').length ) {
		    		extra += $('#topbar').height() / 2;
		    	}
		    	if( $('.bottom-nav-wrapper').length ) {
		    		extra += $('.bottom-nav-wrapper').height() / 2;
		    	}
	
		    	marginTop = titleInnerHeight / 2 - extra;
		        $(this).find( '.page-title-inner' ).css( 'margin-top', -marginTop );
		        
		        pageTitleResized = true;
		    });
		}
	}
	
	// Column Padding
	
	function columnPadding() {
		
		$( '.col-has-padding' ).each( function() {
			
			var $col = $(this);
			var width = $col.outerWidth();
			var padding = 0.14 * width;
			
			if ( $col.data( 'padding-all' ) || $col.data( 'padding-top' ) ) {
				//console.log( 'yes1: ' + $col.data( 'padding-top' ) + ' | ' + $col.data( 'padding-all' ) );
				$col.css({ 'padding-top' : padding });
			}
			if ( $col.data( 'padding-all' ) || $col.data( 'padding-bottom' ) ) {
				//console.log( 'yes2: ' + $col.data( 'padding-bottom' ) + ' | ' + $col.data( 'padding-all' ) );
				$col.css({ 'padding-bottom' : padding });
			}
		});
		
	}
	
	// Page Loader
	
	function pageLoader(){
	    if($('.loader-wrapper').length){
	        if($('.loader-wrapper').hasClass('loader-disabled')){
	            $('.loader-wrapper').addClass('loaded');
	        }else{
	            if($('.section-portfolio').length){
	                setTimeout(function() {
	                    $('.loader-wrapper').addClass('loaded');
	                },500);
	            }else{
	                setTimeout(function() {
	                    $('.loader-wrapper').addClass('loaded');
	                },200);
	            }
	        }
	    }
	}
	
	// Handle big background images
	
	function handleBGImages() {
		
		// Page Title BG 
		
		if ( $( '.page-title-bg' ).length > 0 ) {
			$( '.page-title-bg img' ).one( 'load', function() {
				$( '.page-title-bg' ).css({ 'opacity' : 1 });
			}).each(function() {
				if ( this.complete ) $(this).load();
			});
		}
		
		// Hero Section BG images
		
		if ( $( '.hero-bg-image' ).length > 0 && $( '.vntd-fake-image' ).length > 0 ) {
			$( '.vntd-fake-image' ).one( 'load', function() {
				$(this).closest( '.hero-bg-image' ).css({ 'opacity' : 1 });
			}).each(function() {
				if ( this.complete ) $(this).load();
			});
		}
		
		// Engage Swiper Images
		
		if ( $( '.fullscreen-video-holder' ).length > 0 && $( '.vntd-fake-image' ).length > 0 ) {
			$( '.vntd-fake-image' ).one( 'load', function() {
				$(this).closest( '.fullscreen-video-holder' ).css({ 'opacity' : 1 });
			}).each(function() {
				if ( this.complete ) $(this).load();
			});
		}
		
	}
	
	// Scroll Help
	
	function scrollHelp() {
	    if(!isFirefox){
	        var scrollTime = 0.4; //Scroll time
	        var scrollDistance = 300; //Distance. Use smaller value for shorter scroll and greater value for longer scroll
	        if ($('#wrapper').hasClass('left-nav') || $('#wrapper').hasClass('right-nav')) {
	            $('#main-content').on('mousewheel DOMMouseScroll', function(event) {
	                event.preventDefault();
	                var delta = event.originalEvent.wheelDelta / 120 || -event.originalEvent.detail / 3;
	                var scrollTop = $window.scrollTop();
	                var finalScroll = scrollTop - parseInt(delta * scrollDistance);
	                TweenMax.to($window, scrollTime, {
	                    scrollTo: {
	                        y: finalScroll,
	                        autoKill: true
	                    },
	                    ease: Power1.easeOut, //For more easing functions see http://api.greensock.com/js/com/greensock/easing/package-detail.html
	                    autoKill: true,
	                    overwrite: 5
	                });
	            });
	        } else {
	            if (wrapper.hasClass('boxed')) {
	                body.on('mousewheel DOMMouseScroll', function(event) {
	                    event.preventDefault();
	                    var delta = event.originalEvent.wheelDelta / 120 || -event.originalEvent.detail / 3;
	                    var scrollTop = $window.scrollTop();
	                    var finalScroll = scrollTop - parseInt(delta * scrollDistance);
	                    TweenMax.to($window, scrollTime, {
	                        scrollTo: {
	                            y: finalScroll,
	                            autoKill: true
	                        },
	                        ease: Power1.easeOut, 
	                        autoKill: true,
	                        overwrite: 5
	                    });
	                });
	            } else {
	                $('#wrapper').on('mousewheel DOMMouseScroll', function(event) {
	                    event.preventDefault();
	                    var delta = event.originalEvent.wheelDelta / 120 || -event.originalEvent.detail / 3;
	                    var scrollTop = $window.scrollTop();
	                    var finalScroll = scrollTop - parseInt(delta * scrollDistance);
	                    TweenMax.to($window, scrollTime, {
	                        scrollTo: {
	                            y: finalScroll,
	                            autoKill: true
	                        },
	                        ease: Power1.easeOut,
	                        autoKill: true,
	                        overwrite: 5
	                    });
	                });
	            }
	        }
	    }
	}
	
	// Adjust Sidebar Height
	
	function adjustSidebarHeight() {
	
		if( $('.section-page').hasClass('page-width-stretch') || $('.section-page').hasClass('page-width-stretch_no_padding') ) {
		    $('#sidebar-left, #sidebar-right, .sidebar-left, .sidebar-right, .sidebar').css('min-height', '');
		    $('.section-blog, .section-page, .section-portfolio').each(function() {
		        var blogHeight = $(this).height();
		        $('#sidebar-left, #sidebar-right, .sidebar-left, .sidebar-right, .sidebar').css('min-height', blogHeight);
		    });
		}
		
	}
	
	// Page Transition Effect
	
	function handleLinks() {

	   $('a[href=\'#\']').click(function(e) {
	        e.preventDefault();
	   });
	    
	    $('body:not(.one-page):not(.split-screen) #wrapper:not(.type-onepager)').on('click', '#main-menu li a, #main-aside-menu li a, .main-menu li a, figure a:not(.ajax-modal), .flexslider > a, .tools-btn, .fade-link', function(e) {
	        if (!$('#wrapper').hasClass('tour') && !$('html').hasClass('one-page') && !$(this).attr('target') && !$(this).hasClass('email-link')) {
	            e.preventDefault();
	            var targetLink = $(this).attr('href');
	            if (targetLink === '#' || targetLink === '' || $(this).hasClass('magnific')) {
	                return;
	            }
                
                if ( !$('#wrapper').hasClass( 'vntd-with-transition' ) ) {
	                window.location.href = targetLink;
                } else {
                    $('body').fadeOut(350, function() {
	                   window.location.href = targetLink;
	                });
                }
	            
	        }
	    });
	    
	    $('[data-link]').click(function() {
	        var targetLink = $(this).data('link');
	        if (targetLink !== undefined && targetLink !== '#') {
	            $('body').fadeOut(350, function() {
	               window.location.href = targetLink;
	            });
	        }
	    });
	}
	
	
	// Scroll to top button
	
	function scrollTop() {
	    if ($(this).scrollTop() > 100) {
	        $('.scrollup').fadeIn();
	    } else {
	        $('.scrollup').fadeOut();
	    }
	    $(window).scroll(function() {
	        if ($(this).scrollTop() > 100) {
	            $('.scrollup').fadeIn();
	        } else {
	            $('.scrollup').fadeOut();
	        }
	    });
	    $('.scrollup').click(function() {
	        $('html, body').animate({
	            scrollTop: 0
	        }, 1000);
	        return false;
	    });
	}
	
	// Handle Search
	
	function handleSearch() {
	  var wrapper = $('#wrapper'), toggleSearch = $('#toggle-search'), search = $('.search-overlay'), searchClose = $('.search-overlay-close'), searchStyle = $('#toggle-search').data('search-style');
	
	  $("[data-toggle-search]").click(function(e) {
	  
	    e.preventDefault();
	    var searchLayout = $(this).data('toggle-search');
	    /* SEARCH ON TOP */
	    if (searchLayout === 'top') {
	      setTimeout(function () {
	        $('#search.top-search, .search.top-search, body').toggleClass('search-open');
	      }, 100);
	      setTimeout(function () {
	        $('.top-search input').focus();
	      }, 200);
	      $('body').on('click', function(e) {
	        e.preventDefault();
	        if ($(e.target).parents('.search-tool').length || $(e.target).parents('.toggle-search').length || $(e.target).parents('#search').length || $(e.target).parents('.search').length) {
	          return;
	        }
	        if (body.hasClass('search-open') === true) {
	          $('#search.top-search, .search.top-search, body').removeClass('search-open');
	        }
	      });
	      $('.search-close a').on('click', function(e) {
	        e.preventDefault();
	        $('#search.top-search, .search.top-search, body').removeClass('search-open');
	      });
	      $('#search.top-search input').keypress(function(e) {
	        if (e.which === 13) {
	          $('#search.top-search, .search.top-search').submit();
	          return false;
	        }
	      });
	    }
	    /* SEARCH NAVIGATION REPLACE */
	    if (searchLayout === 'nav') {
	      setTimeout(function () {
	        $('.nav-search').toggleClass('search-open');
	        $('body').toggleClass('search-nav-open');
	      }, 100);
	      setTimeout(function () {
	        $('.nav-search input').focus();
	      }, 200);
	      $('body').on('click', function(e) {
	        e.preventDefault();
	        if ($(e.target).parents('.search-tool').length || $(e.target).parents('.toggle-search').length || $(e.target).parents('#search').length || $(e.target).parents('.search').length) {
	          return;
	        }
	        $('#search.nav-search, .search.nav-search').removeClass('search-open');
	        $('body').removeClass('search-nav-open');
	      });
	      $('.search-close a').on('click', function(e) {
	        e.preventDefault();
	        $('#search.nav-search, .search.nav-search').removeClass('search-open');
	        $('body').removeClass('search-nav-open');
	      });
	      $('#search.nav-search input, .search.nav-search input').keypress(function (e) {
	        if (e.which === 13) {
	          $('#search.top-search, .search.top-search').submit();
	          return false;
	        }
	      });
	    }
	    /* SEARCH FULLSCREEN */
	    if (searchLayout === 'fullscreen') {
	
	      search.addClass('open');
	      wrapper.addClass('search-overlay-open');
	
	      setTimeout(function () {
	        $('.search-overlay input').focus();
	      }, 200);
	      
	      $('.search-overlay-close').click(function(e) {
	        e.preventDefault();
	        search.removeClass('open');
	        wrapper.removeClass('search-overlay-open');
	      });
	      
	      $('body').on('click', function(e) {
	    
	        if ( $(e.target).parents('.search-tool').length || $(e.target).parents('form').length || $(e.target).parents('.btn').length || $(e.target).is('a') ) {
	          return;
	        }
	        if (search.hasClass('open') === true) {
	            search.removeClass('open');
	            wrapper.removeClass('search-overlay-open');
	        }
	      });
	    }
	  });
	}

} ) ( jQuery );