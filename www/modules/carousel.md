---
layout: modules
title: Mobify.js Carousel Module
---

<link rel="stylesheet" href="{{ site.baseurl }}/static/examples/css/carousel.css">
<link rel="stylesheet" href="{{ site.baseurl }}/static/examples/css/carousel-controls.css">
<style>
/* styling for this page */
.m-carousel {
  padding-bottom: 30px;
}
.m-item {
  margin-right: 20px;
}
.m-carousel .m-item img {
    margin: 0;
    padding: 0;
    max-width: none;
	width: 100%;
    -webkit-box-shadow: rgba(0,0,0,0.5) 0 5px 10px;
    -moz-box-shadow: rgba(0,0,0,0.5) 0 5px 10px;
    box-shadow: rgba(0,0,0,0.5) 0 5px 10px;
}
</style>

# Carousel

Image carousel module for all your image rotating needs. Try it out:

<div class="m-carousel m-carousel-example-4 m-center m-fluid">
  <!-- Carousel items -->
  <div class="m-carousel-inner">
    <div class="m-item">
        <img src="{{ site.baseurl }}/static/examples/img/helmets.jpg">
    </div>
    <div class="m-item">
        <img src="{{ site.baseurl }}/static/examples/img/blossoms.jpg">
    </div>
    <div class="m-item">
        <img src="{{ site.baseurl }}/static/examples/img/glacier.jpg">
    </div>
    <div class="m-item">
        <img src="{{ site.baseurl }}/static/examples/img/parliament.jpg">
    </div>
    <div class="m-item">
        <img src="{{ site.baseurl }}/static/examples/img/pods.jpg">
    </div>
  </div>
  <!-- Carousel controls -->
  <div class="m-carousel-controls m-carousel-bulleted">
    <a class="carousel-control right" href="#myCarousel" data-slide="1">1</a>
    <a class="carousel-control right" href="#myCarousel" data-slide="2">2</a>
    <a class="carousel-control right" href="#myCarousel" data-slide="3">3</a>
    <a class="carousel-control right" href="#myCarousel" data-slide="4">4</a>
    <a class="carousel-control right" href="#myCarousel" data-slide="5">5</a>
  </div>
</div>


[See more examples]({{ site.baseurl }}/modules/carousel-examples)

## Using mobify-carousel.js

To initialize a carousel use the markup documented below,
and call the jQuery initializer:

    $('.m-carousel').carousel()

## Options

When you initialize the carousel, you can pass a variety of options
as an object as the first argument.

| Name          | Type      | Default   | Description                                                           |
| classPrefix   | string    | "m-"      | A prefix used to namespace all the class names used by the carousel.  |

## Markup

The basic markup is composed out a viewport div `.m-carousel`, a sliding div `m-carousel-inner`, and numerous item divs `.m-item`.
Additionally, the any `data-slide` attributes within the viewport div, `.m-carousel`, can be bound to actions "next", "previous",
or to move the slider to particular index.


    <div class="m-carousel">
        <div class="m-carousel-inner">
            <div class="m-item m-active">
                <img src="...">
            </div>
            <div class="m-item">
                <img src="...">
            </div>
            <div class="m-item">
                <img src="...">
            </div>
            <div class="m-item">
                <img src="...">
            </div>
            <div class="m-item">
                <img src="...">
            </div>
        </div>

        <div>
            <a href="#" data-slide="prev">Previous</a>
            <a href="#" data-slide="1" class="m-active">1</a>
            <a href="#" data-slide="2">2</a>
            <a href="#" data-slide="3">3</a>
            <a href="#" data-slide="4">4</a>
            <a href="#" data-slide="5">5</a>
            <a href="#" data-slide="next">Next</a>
        </div>
    </div>

Note: the currently active `.m-item` and any currently active `[data-slide=N]`
gains the class `.m-active`.


## Markup Options

A few other classes are provided that give you additional control. These
are applied to the viewport `.m-carousel`.


| Class       | Description                                                                                       |           
| `.m-fluid`  | Causes the the width of the `.m-item` divs to resize to match the viewport `.m-carousel`'s width. |
| `.m-center` | Causes the items to be center aligned, not left aligned (the default).                            |

In the absence of the `.m-fluid` class, the width of the `.m-item`s is determined by their content and/or by any styling that restricts their width.


## Methods

### .carousel(options)

Initializes the carousel with the options (an `object`) given.

    $('.m-carousel').carousel({
        classPrefix: "m-"
    });

### .carousel('next')

Moves the carousel one item to the right.

    $('.m-carousel').carousel('next');

### .carousel('prev')

Moves the carousel one item to the left.

    $('.m-carousel').carousel('prev');

### .carousel('move', x)

Moves the carousel to a specific index (1-based).

    $('.m-carousel').carousel('move', 1);

### .carousel('unbind')

Removes any tap, mouse, and other event handlers from the carousel.

    $('.m-carousel').carousel('unbind');

### .carousel('bind')

Restores the tap, mouse, and other event handlers for the carosel.

    $('.m-carousel').carousel('bind');

### .carousel('destroy')

Unbinds the events from the carousel, and removes it from the DOM.

    $('.m-carousel').carousel('destroy');


## Events

The viewport element, `.m-carousel`, emits the follow events.

| Name          | Arguments                 | Description                               |   
| beforeSlide   | previousIndex, newIndex   | Fired before the carousel moves.          |
| afterSlide    | previousIndex, newIndex   | Fired after the carousel begins moving.   |



<script src="{{ site.baseurl }}/static/examples/js/carousel.js"></script>
<script>
    $(function() { $('.m-carousel').carousel(); });
</script>