# Bootstrap 3
============
Author: Shawn Wildermuth
Started: 11082014
Fished: _

## Getting Started
* can have more than one container class on a page - guarentees own *vertical* space
* grids have a type for screen size

1. .col-lg-xx: >= 1200px (desktop)
2. .col-md-xx: >= 992px (landscape tablet)
3. .col-sm-xx: >= 768px (portrait tablet)
4. .col-xs-xx: < 768px (phone)

* give multiple classes to enable different allocations depending on screen size
* can download a customised bootstrap distribution
* media queries allow custom styling based on screen size
* subtractive approach means smallest devices need to render the most css because media queries are additive
* pull-left and pull-right classes give you float like capability
* img-thumbnail gives you responsively sized images
* hidden classes let you hide things in a responsive way, e.g. hidden-sm
* inversly, can use visible classes
* can add in a bootstrap theme, see bootswatch.com

## Bootstrap 3 Basics
### Typography
* class 'lead' on a p will give you an abstract like functionality
* there are 'text-[xx]' classes that give you styling on text, e.g. text-success 

### Buttons
* base class is 'btn'
* can add 'btn-success' etc
* can apply btn classes to a's to represent links as buttons

### Icons
* bootstrap ships with icons in fonts file
* changing size classes, e.g. icon in btn-sm will be smaller than icon in btn-lg

### Navs and Navbars
* 'navbar' and 'navbar-default' are top level container
* 'navbar-header' for brand etc
* 'navbar-nav' for actual navigation items, each item with a 'nav' class
* 'active' on 'nav' items shows active page etc
* can surrond nav with 'navbar-collapse collapse' which indiactes section should be hidden when screen is too small (doesnt get rid of out of dom)
* can use navbar-toggle class on a button, combine with data-toggle='collaps' and data-target=".navbar-collapse"
* 'navbar-fixed-top' will give you a fixed menu that takes full width at stays at top of screen when scrolling.  Need to add a top margin to body to stop content overlapping the fixed header.

### Lists
* 'list-unstyled' removes indent and decoration (bullets etc)
* 'list-inline' ... makes inline
* 'list-group' on ul and 'list-item' on li gives you full widht lists with block like styling
* can use a span with class 'badge' in li to give you icon like capability

### Tables
* class 'table' gives you some default responsiveness by default.  Wraps as we get smaller.
* 'table-striped' gives you alterate colored rows
* 'table-bordered'
* 'table-hover' : gives you highlight on hover
* 'table-condensed' tightens up padding
* 'table-responsive' on CONTAINING element, e.g. div.  Stops excessive wrapping on small screens, gives you horizontal scroll bar

### Forms
* wrap controls in a div with 'form-group'
* use 'form-control' on inputs for basic styling (selects text etc)
* by default forms will fill container, wrap in a dedicated container to control the width
* bootstrap support horizontal forms (label to left of input)
	* put 'form-inline' on form
	* labels need 'control-label' and a width e.g. 'col-md-2'
	* wrap inputs in containing div.  and give a width e.g. 'col-md-10'
	* can wrap buttons in a 'control-group' and using 'col-md-offset-x'
	* bootstrap converts form to vertical on smaller screen sizes

## Bootstrap Components

### Page Header and Breadcrumbs
* 'page-header' creates a section on top of page with spacing, seperated with horizontal rule
* breadcrumbs with ol with 'breadcrumb'.  Then li's for crumbs.  Apply 'active' for indication of place in breadcrumb

### Button Groups
* wrap buttons in a div with 'btn-group'.  Makes buttons look like a single control
* can add 'active' to make one seem ... active
* alternative to radio buttons
* 'btn-group-vertical' is another option
* to get toggle functionality
	* wrap in an input, with the same button classes e.g. 'btn'
	* put a checkbox input inside label to submit with form
	* add data-toggle="buttons" in container div
	* you can use radios to get a single select functionality 

### Dropdowns
* add a class to div 'dropdown'
* inside that put a ul with class 'dropdown-menu' (other options available)
* use tabindex="-1" on the li's to avoid them being in the tab order
* can add 'disabled' to li.  Will still show it in drop down, but greyed out
* can use an empty li with a class 'divider' to get a horizontal rule seperator in the dropdown
* need something to activate the drop down, e.g. a button.  Add a data-toggle="dropdown" to this activation element.  Will work if it is a child of 'dropdown' div and a sibling to 'dropdown-menu' ul

### Button Dropdowns
* can use dropdown in button group
* use span with 'caret' to add a drop down icon to button

### Replacing a select with a dropdown
* nothing magical here, can replace a drop down with a button group
* need to get the data into form post data (e.g. hidden field)

### Input groups
* input groups are a way to add context to an input, e.g. '@' in email.
* wrap an input in a div with 'input-group' and add a sibling span with 'input-group-addon'
* can be before or after

### Pagination
* use a ul with 'pager
* best to use <a> in li's for prev next etc.
* use 'previous' and 'next' in lis to float to left and right edges of container
* can also use 'pagination-sm' and 'pagination-lg'
* can add 'active' to li
* can add 'disabled' to li for next and previous when on first or last page

### Thumbnails
* can layout pictures using grid, e.g. 'col-md-4' but this wont resize images, you will get overlap
* can add 'img-responsive' to <img> to have them resize, but still not thumbnails
* add 'thumbnail' to containing <a>, will give you border box
* to use captions wrap in a div and add 'thumbnail' there instead, then add a child div with 'caption' and put html in there (e.g. h2, p)

### Panels
* add 'panel' to a div to group content
* 'panel-body' will apply padding etc to content inside panel
* panels can also have headers with 'panel-heading'
* can use panel theme colors, e.g. 'panel-default', 'panel-primary', 'panel-brand'
* within a panel header better to use 'panel-title'
* also use a 'panel-footer' in a similar way

### Wells
* idea of wells is to create a bordered section in your design that looks 'sunken'
* use <div> with 'well'
* can also reduce/increase padding with 'well-sm' and 'well-lg'

## Bootstrap Plugins

### Collapse
* can use <a> with a data-toggle = 'collapse' and with href set to id of div to collapse.  The div to collapse must also have class 'collapse'
* can use 'in' on div to show it on initial load

### Accordion
* can use a combination of panels in a 'panel-group' and 'collapse' to build an accordion
	* give top level div and id, e.g. 'accordion' and class 'panel-group'
	* add a panel heading section with an anchor that has
		* data-toggle='collapse'
		* data-parent='#accordion'6

### Modal Markup
* use an outter div with 'modal' and an id
* inside that a div with 'modal-dialog'
* inside that a div with 'modal-content'
* inside 'modal-content' you can have 'modal-header', 'modal-body', 'modal-footer'
* this will be invisible by default can use an anchor with a href matching the 'modal' div id.  also needs a data-toggle='modal'
* to close dialog you can use a data-dismiss="modal" on close button
* for 'x' in upper right hand corner use an anchor with class="close" and data-dismiss="modal" and content of &times;


### Modal Events
* usually will need to interact with modal in javascript
* bootstrap using jquery plugin style, e.g. $('#myModal').modal(options)
* can handle other modal events e.g. $myModal.on('hidden.bs.modal'), function(){ // stuff here});

### Tabs
* use an unordered list for navigation. can use 'nav' and 'nav-tabs' to get look and feel
* use div with ids matching hrefs in ul for tab content
* li's also need data-toggle="tab" and divs need class 'tab-pane'
* wrap content panels in a container div with 'tab-content'
* can add 'active' to li and div to select a default tab
* to make tabs take entire container width add 'nav-justified' to ul

### Tooltips
* because searching every element with a title is computationally expensive, you need to wire tooltips up manually in js
* the element you want a tooltip for needs a title attribute and a data-toggle="tooltip"
* then in js use something like $('#myInput').tooltip();
* can pass an options object to tooltip func, e.g. {placement: 'left'}
* can also do most things through data attributes, e.g. data-placement="left", data-delay="500"
* options in js will override data-attributes
* sometimes data attributes can not do what you are after e.g. delay { show: 500, hide: 0}
* can also use data-html="true" then put html in title attribute

### Alerts
* use base class 'alert' and add classes like 'alert-warning' for styling.
* can add an anchor to close the alert, needs data-dismiss="alert" and class="close"
* can hide by default by adding a 'collapse' class and then showing the alert via js when relevant
* data-dismiss attribute will remove alert html from dom, to get around this you can use js events on the alert, e.g. alert.on("close.bs.alert", function(){ // do stuff}). Import to return false to stop event propogation.

### Carousel Markup
* create an outer div with 'carousel'  can use 'slide' or 'fade' on this div to control the animation
* create a child div with 'carousel-inner' and put divs with 'item' inside this.
* need to init carousels in js, e.g. $('#theCarousel').carousel();
* need to give one of the items the 'active' class to start with
* can control delay through js option or data-interval attribute (in milliseconds)
* can hide carousel on smaller screens by defining 'visible-md visible-lg'

### Carousel Indicators
* use ol for navigation indicators with 'carousel-indicators'
* lis dont need content but need data-target=[id of carousel] and data-slide-to=[ordered number]
* need to add an active for default behaviour

### Carousel Navigation
* to get left/right navigation use a with
	* href = #theCarouselId
	* class = 'carousel-control left|right'
	* data-slide = "prev|next"
	* inside this put a span with class = 'icon-prev|icon-next'

### Carousel Captions
* can div with class='carousel-caption' as sibling of carousel item

## Migrating to Bootstrap 3
### General summary of differences
* in bootstrap 3
	* mobile first and responsive by default.  Default look and feel is for mobile, and enhances as you go to large devices.
	* fewer classes -> has been simplified and streamlined
	* 'fluid' layout is gone, everything is based on fixed layouts now
	* less collision with custom css
* things you have to take into account when migrating from bootstrap 2 to bootstrap 3
	* because 3 is mobile first, you css also needs to be mobile first
	* means if you where using @media queries with max-width gates, need to reverse to min-width gates
	* no more need to include bootstrap-responsive.[min].css
* class renaming
	* all 'fluid' classes are gone
	* some classes are 'namespaced', e.g. 'list-unstyled' vs 'unstyled'
	* sizes have been standadized to lg, md, sm, xs
	* docs [here](http://bootstrapdocs.com/v3.0.3/docs/getting-started/#migration)
* things that have been removed entirely
	* .form-actions
	* .form-search
	* .controls
	* .navbar-inner
	* .divider-vertical
	* .dropdown-submenu
	* .tabs-left, .tabs-right, .tabs-center
	* .nav-list
* gylphicons pngs are replaced with fonts so they can be resized

### Migrating the Grid
* remove any fluids
* replace spans with col sizes, e.g. span3 with col-md-3.  Best to replace span with md's.  Add other col sizes as needed

### Migrating the NavBar
* rename nav-collapse to navbar-collapse
* the navbar needs to be on ul not div
* some other class changes needed

### Misc
* pagination 
	* classes on ul's not div'
	* 'pull-right' instead of 'pagination-right'
	* 'pagination-sm' instead of 'pagination-small'
* lists
	* 'unstyled' and 'inline' no longer exist. Replace with 'list-unstyled' and 'list-inline'
* icons
	* instead of 'icon-x' need 'glypicon glyphicon-x'
	* 'icon-right|left' no changed to 'chevron-right|left'
* input-append no longer exists, use input-group
* img-polaroid replaced with img-thumbnail
* replace 'accordion' with 'panel'

### Migrating Custom CSS
* you may have overrides in your own css that override bootstrap classes that no loner exist, or you are longer using
* need to reverse media queries








