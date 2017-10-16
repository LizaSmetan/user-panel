Web Store
=====================

### Файлы папки app

Название файла     | Содержание файла
-------------------|----------------------
index.html         | Страница "General statistic"
details.html       | Страница "Details statistic"
payout.html        | Страница "Payout history"
personal-data.html | Страница "Personal data"
postback.html      | Страница "Create postback"
guide.html         | Страница со стандартными элементами

**Файлы папки app/css**

Название файла                    | Содержание файла
----------------------------------|----------------------------------
css/font-awesome.css              | Иконки Font-awesome
css/myfont.css                    | Сконвертированные иконки
css/style.css                     | Основные стили

**Файлы папки app/js**

Название файла               | Содержание файла
-----------------------------|-----------------------------
js/bootstrap.min.js          | Подключенные плагины Bootstrap 3
js/jquery.scrollbar.js       | Плагин для силизации скролла
js/jquery.formstyler.min.js  | Плагины формы количества товара JQuery
js/jquery.bpopup.min.js      | Плагин для запуска модальных окон
js/plugins.min.js            | Основные плагины
js/init.js                   | Основные плагины

---
**Файлы scss**

1.Component.scss
2.Custom-style.scss
3.Default-classes.scss
4.Fonts.scss
5.Jquery.formstyler.scss
6.Jquery.formstyler.theme.scss
7.Jquery.scrollbar.scss
8.Reset.scss
9.Variables.scss

---

***Внешние плагины***
    [JQuery-ui](https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css)

---

**Переменные**

```css

// Font var

$fontFamily: 'Roboto', sans-serif;
$fontLight: 300;
$fontRegular: 400;
$fontMedium: 500;
$fontBold: 700;
$lineHeight: 1;
$fontSize: 14px;

// Color var
$black: #333;
$darkGrey: #979797;
$grey: #bababa;
$lightGrey: #e3e3e3;
$xsLightGrey: #f5f5f2;

$orange: #f58220;
$orangeLight: #ffa200;
$green: #04ae00;
$lightGreen: #74b67a;
$xsLlightGreen: #96cc9b;

$red: #ff0000;
$pink: #de5252;
$lightPink: #ec7171;
$blue: #56819f;
$white: #fff;

// default padding

$defaultIndent: 18px;

//component var

//link component
$linkColor: #56819f;
$linkColorLight: #ffa200;
$linkFontSizeDefault: 13px;
$linkLargeFont: 16px;
$linkHoverColor: #ffa200;


//title component
$titleColor: #a6a6a6;
$titleFontSize: 16px;
$smallTitleFontSize: 14px;

// btn component
$btnFontSize: 18px;
$btnDefaultColor: #fff;
$btnDefaultBg: $darkGrey;
$btnDefaultBgHover: $grey;
$btnActionBg: $orange;
$btnActionBgHover: $orangeLight;
$btnDisableBg: $lightGrey;
$btnDisableBgHover: $lightGrey;

//table component
$tableFontSize: 13px;
$tableTrHover:#f1f3f3;

//color tab

$colorTabFontSize: 16px;
$colorTabTextColor: #a6a6a6;
$tabBgHoverActive: #f3f3f1;

//inputs

$inputColor: #a6a6a6;
$inputColorHover: #333;
$inputBorderDefault: #e3e3e3;
$inputBorderHover: #b1b1b1;
$textareaFont: 12px;

//notification

$notificationLineHeight: 42px;
$positiveNotificationBg: #96cc9b;
$positiveNotificationBgHover: #74b67a;
$negativeNotificationBg: #ec7171;
$negativeNotificationBgHover: #de5252;
 
//aside component

$asideBg: #191919;
$asideWidth: 188px;
$asideWidthMini: 160px;

//sidebar

$sidebarMobileWidth: 60px;

//default border

$defaultBorder: 1px solid $lightGrey;

//media

$mobBrP-size: 1280px;
$lg-size: 1199px;
$md-size: 991px;
$sm-size: 767px;
$xs-size: 599px;
$mini-size: 479px;


```

**Стандартные классы**

```css

//text-classes
.text-bold{
    font-weight: $fontBold;
}
.text-center{
  text-align: center;
}
.text-left{
    text-align: left;
}
.red-text{
    color: $red;
}
//class position fixed
.fixed-to-top{
    position: fixed;
    z-index: 99;
    top:0;
}

//class flexbox

.flex-container{
    display: flex;
}
.align-items-center{
    align-items: center;
}
.justify-content-sb{
    justify-content: space-between;
}
.flex-wrap{
    flex-wrap: wrap;
}
// columns

.third-width-col{
    width: 33.3333%;
}
.half-width-col{
    width: 50%;
}
.full-width{
    width: 100%;
}

// Content wrapper

.content-wrapper{
    padding: $defaultIndent;
    height: calc(100vh - 60px);
}

.scroll-x-wrap{
    overflow-x: scroll;
}

```

**Плагины**

```js
;(function(){
  // sidebar mobile
  var menuBtn = $('.menu-btn');
  var body = $('body');
  var mobileSidebarClass = '_mobileSidebar';
  var mobileBreakPoint = 1280;
  var openInMobileClass = '_openInmobile';

  menuBtn.on('click', function(e){
    
    var width = $(window).width();
    body.toggleClass(mobileSidebarClass);
    if(width < mobileBreakPoint){
      body.toggleClass(openInMobileClass);
    }

  });

  $(window).on('resize load', function(e){
    var width = $(this).width();
    
    if(width < mobileBreakPoint && !body.hasClass(openInMobileClass)){
      body.addClass(mobileSidebarClass);
    } else if(width > mobileBreakPoint){
      body.removeClass(mobileSidebarClass);
      body.removeClass(openInMobileClass);
    }

  });

  // loader hide
  var loader = $('#loading');

  $(window).on('load', function(e){
    loader.addClass('hide');
  });


  // dropdown menu
  var dropdownWrap = $('.dropdown-wrap');

  dropdownWrap.on('click', function(e){
    e.preventDefault();
    var dropdown = $(this).find('.dropdown-menu');
    dropdown.slideToggle();
  });

})();

```

```js

$( function() {

    // dateoicker init
    var dateFormat = "mm/dd/yy",
        from = $("#from")
            .datepicker({
                defaultDate: "+1w",
                changeMonth: true,
                numberOfMonths: 1
            })
            .on("change", function () {
                to.datepicker("option", "minDate", getDate(this));
            }),
        to = $("#to").datepicker({
            defaultDate: "+1w",
            changeMonth: true,
            numberOfMonths: 1
        })
            .on("change", function () {
                from.datepicker("option", "maxDate", getDate(this));
            });

    function getDate(element) {
        var date;
        try {
            date = $.datepicker.parseDate(dateFormat, element.value);
        } catch (error) {
            date = null;
        }

        return date;
    }


    // chart init
    var ctx = document.getElementById("myChart");
    if (ctx) {
        var myChart = new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ["01", "02", "04", "05", "06", "07", "08", "09", "10"],
                datasets: [{
                    label: 'Signups',
                    data: [100, 175, 135, 190, 100, 150, 175, 143, 110],
                    backgroundColor: [
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                        'rgba(128, 191, 202, 1)',
                    ],

                },
                    {
                        label: 'FTD',
                        data: [190, 120, 200, 210, 150, 175, 143, 110, 130],
                        backgroundColor: [
                            'rgba(255, 154, 56, 1)',
                            'rgba(255, 154, 56, 1)',
                            'rgba(255, 154, 56, 1)',
                            'rgba(255, 154, 56, 1)',

                            'rgba(255, 154, 56, 1)',
                            'rgba(255, 154, 56, 1)',
                            'rgba(255, 154, 56, 1)',
                            'rgba(255, 154, 56, 1)',
                            'rgba(255, 154, 56, 1)',
                        ],

                    }
                ]
            },
            options: {
                responsive: true,
                scales: {
                    yAxes: [{
                        ticks: {
                            beginAtZero: true
                        }
                    }]
                }
            }
        });
    }


    // modal init
    var modalBtns = $('[data-modal]');

    modalBtns.on('click', function (event) {
        event.preventDefault();

        var target = $(this).attr('data-modal');

        $(target).bPopup({
            closeClass:'close'
        });
    });

    // scrollbar init
    $('.scrollbar-inner').scrollbar();


    // range slider init
    var handle = $( "#custom-handle" );
    var range = $( "#slider" );
    range.slider({
        value: 60,
        orientation: "horizontal",
        range: "min",
        animate: true,
        max: 200,

        create: function(event, ui) {
            handle.append('<span class="value">'+$( this ).slider( "value" )+'hours</span>');
            var value = handle.find('.value');
            range.slider('option', 'valueSpan', value);
        },
        slide: function( event, ui ) {
            range.slider( "option" ,"valueSpan").text(ui.value + 'hours');
        }
    });

    // formstyler

    $('select').styler();

} );

```