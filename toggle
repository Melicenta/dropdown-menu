function systemMenu(currentMenuContainer, currentListContainer) {
    var $ = jQuery; /*jQuery*/

    var menuContainer = $('.' + currentMenuContainer); /*container*/
    var menuButton = $(menuContainer).children('.smart-menu-button');/*toggle button container*/
    var button = $(menuButton).children('a'); /*button itself*/
    var menuList = $(menuContainer).children('.' + currentListContainer); /* dropdown list with menu items*/

    var visible; /*visibillity flag*/
    var firstClick; /*little trick*/

    firstClick = true;


    var hidden = function() {
        $(menuList).css('display', 'none');
        $(menuButton).removeClass('menu-button-pushed');
    };
    /*hides dropdown list and removes pushed visual effect from toggle button*/

    var shown = function() {
        $(menuList).css('display', 'block');
        $(menuButton).addClass('menu-button-pushed');
    };
    /*shows dropdown list and adds pushed visual effect to toggle button*/

    var getCurrentStyle = function() {
        if ($(menuList).css('display') === 'none') {
            visible = false;
        } else visible = true;
    };
    /*really current*/
    
    function toggleList() {
        getCurrentStyle();
        if (visible === true) {
            hidden();
            visible = false;
        } else shown();
    }
    /* the key function*/

    $(button).on('click', function() {
        toggleList();
    });
    /*and this is the call*/


    $(document).on('click', function(e) {
            if (!firstClick && !($(button).is(e.target) ||
                    $(menuList).is(e.target)) &&
                    (($(button).has(e.target).length === 0) &&
                    ($(menuList).has(e.target).length === 0))) {
                hidden();
            }
            firstClick = false;
    });
    /*out of focus click event*/

}
