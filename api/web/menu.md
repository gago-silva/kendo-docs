---
title: kendo.ui.Menu
meta_title: Configuration, methods and events of Kendo UI Menu
meta_description: How to configure all animations in Menu UI widget, enable and disable, remove specified items and use code examples for all methods and events supported.
slug: api-web-menu
relatedDocs: gs-web-menu-overview
tags: api,web
publish: true
---

# kendo.ui.Menu

Represents the Kendo UI Menu widget. Inherits from [Widget](/api/framework/widget).

## Configuration

### animation `Object`

A collection of **Animation** objects, used to change default animations. A value of false will disable all animations in the widget.

Available animations for the **Menu** are listed below.  Each animation has a reverse options which is used for the **close** effect by default, but can be over-ridden
by setting the **close** animation.  Each animation also has a direction which can be set off the animation (i.e. **slideIn:Down**).

#### *slideIn*

Menu content slides in from the top

#### *fadeIn*

Menu content fades in

#### *expand*

Menu content expands from the top down. Similar to slideIn.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            animation: { open: { effects: "fadeIn" } }
        });
    </script>

### animation.close `Object`

The animation that will be used when closing sub menus.

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            animation: { close: { effects: "slideIn:up" } }
        });
    </script>

### animation.close.effects `String`

Effect to be used for closing of the popup.

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            animation: { close: { effects: "slideIn:up" } }
        });
    </script>

### animation.close.duration `Number`

Defines the animation duration in milliseconds.

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
             animation: { open: {
                 effects: "slideIn:down",
                 duration: 100
             } }
         });
    </script>

### animation.open `Object`

The animation that will be used when opening sub menus.

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            animation: { open: { effects: "slideIn:down" } }
        });
    </script>

### animation.open.effects `String`

Effect to be used for opening of the popup.

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            animation: { open: { effects: "slideIn:down" } }
        });
    </script>

### animation.open.duration `Number`

Defines the animation duration in milliseconds.

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            animation: { open: {
                effects: "zoomIn",
                duration: 100
            } }
         });
    </script>

### closeOnClick `Boolean`*(default: true)*

 Specifies that sub menus should close after item selection (provided they won't navigate).

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            closeOnClick: false
        });
    </script>

### direction `String`*(default: "default")*

 Specifies Menu opening direction. Can be "top", "bottom", "left", "right".
You can also specify different direction for root and sub menu items, separating them with space. The example below will initialize the root menu to open upwards and
its sub menus to the left.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            direction: "top left"
        });
    </script>

### hoverDelay `Number`*(default: 100)*

 Specifies the delay in ms before the menu is opened/closed - used to avoid accidental closure on leaving.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            hoverDelay: 200
        });
    </script>

### openOnClick `Boolean`*(default: false)*

 Specifies that the root sub menus will be opened on item click.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            openOnClick: true
        });
    </script>

### orientation `String`*(default: "horizontal")*

 Root menu orientation. Could be horizontal or vertical.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            orientation: "vertical"
        });
    </script>

### popupCollision `String`

Specifies how Menu should adjust to screen boundaries. By default the strategy is **"fit"** for a sub menu with a horizontal parent,
meaning it will move to fit in screen boundaries in all directions, and **"fit flip"** for a sub menu with vertical parent, meaning it will fit vertically and flip over
its parent horizontally. You can also switch off the screen boundary detection completely if you set the **popupCollision** to false.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        $("#menu").kendoMenu({
            popupCollision: false
        });
    </script>

## Methods

### append

Appends an item to a **Menu** in the specified referenceItem's sub menu.

#### Example

    <ul id="menu"></ul>
    <script>
        // get a reference to the menu widget
        var menu = $("#menu").data("kendoMenu");
        //
        menu.append(
            [{
                text: "Item 1",
                cssClass: "myClass",                         // Add custom CSS class to the item, optional, added 2012 Q3 SP1.
                url: "http://www.kendoui.com"                // Link URL if navigation is needed, optional.
            },
            {
                text: "<b>Item 2</b>",
                encoded: false,                              // Allows use of HTML for item text
                content: "text"                              // content within an item
            },
            {
                text: "Item 3",
                imageUrl: "http://www.kendoui.com/test.jpg", // Item image URL, optional.
                items: [{                                    // Sub item collection
                     text: "Sub Item 1"
                },
                {
                     text: "Sub Item 2"
                }]
            },
            {
                text: "Item 4",
                spriteCssClass: "imageClass3"                // Item image sprite CSS class, optional.
            }],
            referenceItem
        );
    </script>

#### Parameters

##### item `Selector`

Target item, specified as a JSON object. Can also handle an array of such objects.

##### referenceItem `Selector`

A reference item to append the new item in.

#### Returns

`kendo.ui.Menu` Returns the Menu object to support chaining.

### close

Closes a sub-menu of a specified item(s) in a **Menu**.

#### Example

    <ul id="menu">
        <li id="Item1">Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        // get a reference to the menu widget
        var menu = $("#menu").data("kendoMenu");
        // close the sub menu of "Item1"
        menu.close("#Item1");
    </script>

#### Parameters

##### element `Selector`

Target item selector.

#### Returns

`kendo.ui.Menu` Returns the Menu object to support chaining.

### destroy
Prepares the **Menu** for safe removal from DOM. Detaches all event handlers and removes jQuery.data attributes to avoid memory leaks. Calls destroy method of any child Kendo widgets.

> **Important:** This method does not remove the Menu element from DOM.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        var menu = $("#menu").data("kendoMenu");

        // detach events
        menu.destroy();
    </script>

### enable

Enables or disables an item of a **Menu**. This can optionally be accomplished on
initialization by setting the **disabled="disabled"** on the desired menu item html element.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li id="secondItem">Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        // get a reference to the menu widget
        var menu = $("#menu").data("kendoMenu");
        // disable the li menu item with the id "secondItem"
        menu.enable("#secondItem", false);
    </script>

#### Parameters

##### element `Selector`

Target element

##### enable `Boolean`

Desired state

#### Returns

`kendo.ui.Menu` Returns the Menu object to support chaining.

### insertAfter

Inserts an item into a **Menu** after the specified referenceItem.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        // get a reference to the menu widget
        var menu = $("#menu").data("kendoMenu");
        //
        menu.insertAfter(
            [{
                text: "Item 1",
                url: "http://www.kendoui.com"                // Link URL if navigation is needed, optional.
            },
            {
                text: "<b>Item 2</b>",
                encoded: false,                                 // Allows use of HTML for item text
                content: "text"                                 // content within an item
            },
            {
                text: "Item 3",
                imageUrl: "http://www.kendoui.com/test.jpg", // Item image URL, optional.
                items: [{                                    // Sub item collection
                     text: "Sub Item 1"
                },
                {
                     text: "Sub Item 2"
                }]
            },
            {
                text: "Item 4",
                spriteCssClass: "imageClass3"                // Item image sprite CSS class, optional.
            }],
            "li:last-child"
        );
    </script>

#### Parameters

##### item `Selector`

Target item, specified as a JSON object. Can also handle an array of such objects.

##### referenceItem `Selector`

A reference item to insert the new item after.

#### Returns

`kendo.ui.Menu` Returns the Menu object to support chaining.

### insertBefore

Inserts an item into a **Menu** before the specified referenceItem.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        // get a reference to the menu widget
        var menu = $("#menu").data("kendoMenu");
        //
        menu.insertBefore(
            [{
                text: "Item 1",
                url: "http://www.kendoui.com"                // Link URL if navigation is needed, optional.
            },
            {
                text: "<b>Item 2</b>",
                encoded: false,                                 // Allows use of HTML for item text
                content: "text"                                 // content within an item
            },
            {
                text: "Item 3",
                imageUrl: "http://www.kendoui.com/test.jpg", // Item image URL, optional.
                items: [{                                    // Sub item collection
                     text: "Sub Item 1"
                },
                {
                     text: "Sub Item 2"
                }]
            },
            {
                text: "Item 4",
                spriteCssClass: "imageClass3"                // Item image sprite CSS class, optional.
            }],
            "li:first-child"
        );
    </script>

#### Parameters

##### item `Selector`

Target item, specified as a JSON object. Can also handle an array of such objects.

##### referenceItem `Selector`

A reference item to insert the new item before

#### Returns

`kendo.ui.Menu` Returns the Menu object to support chaining.

### open

Opens a sub-menu of a specified item(s) in a **Menu**.

#### Example

    <ul id="menu">
        <li id="Item1">Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        // get a reference to the menu widget
        var menu = $("#menu").data("kendoMenu");
        // open the sub menu of "Item1"
        menu.open("#Item1");
    </script>

#### Parameters

##### element `Selector`

Target item selector.

#### Returns

`kendo.ui.Menu` Returns the Menu object to support chaining.

### remove

Removes a specified item(s) from a **Menu**.

#### Example

    <ul id="menu">
        <li id="Item1">Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
        // get a reference to the menu widget
        var menu = $("#menu").data("kendoMenu");
        // remove the item with the id "Item1"
        menu.remove("#Item1");
    </script>

#### Parameters

##### element `Selector`

Target item selector.

#### Returns

`kendo.ui.Menu` Returns the Menu object to support chaining.

## Events

### close

Fires before a sub menu gets closed. You can cancel this event to prevent closure.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         $("#menu").kendoMenu({
             close: function(e) {
                 // handle event
             }
         });
    </script>

#### To set after initialization

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         // get a reference to the menu widget
         var menu = $("#menu").data("kendoMenu");
         // bind to the close event
         menu.bind("close", function(e) {
             // handle event
         });
    </script>

#### Event Data

##### e.item `Element`

The closed item

### open

Fires before a sub menu gets opened. You can cancel this event to prevent opening the sub menu.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         $("#menu").kendoMenu({
             open: function(e) {
                 // handle event
             }
         });
    </script>

#### To set after initialization

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         // get a reference to the menu widget
         var menu = $("#menu").data("kendoMenu");
         // bind to the open event
         menu.bind("open", function(e) {
             // handle event
         });
    </script>

#### Event Data

##### e.item `Element`

The opened item

### activate

Fires when a sub menu gets opened and its animation finished.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         $("#menu").kendoMenu({
             activate: function(e) {
                 // handle event
             }
         });
    </script>

#### To set after initialization

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         // get a reference to the menu widget
         var menu = $("#menu").data("kendoMenu");
         // bind to the activate event
         menu.bind("activate", function(e) {
             // handle event
         });
    </script>

#### Event Data

##### e.item `Element`

The activated item

### deactivate

Fires when a sub menu gets closed and its animation finished.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         $("#menu").kendoMenu({
             deactivate: function(e) {
                 // handle event
             }
         });
    </script>

#### To set after initialization

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         // get a reference to the menu widget
         var menu = $("#menu").data("kendoMenu");
         // bind to the deactivate event
         menu.bind("deactivate", function(e) {
             // handle event
         });
    </script>

#### Event Data

##### e.item `Element`

The deactivated item

### select

Fires when a menu item gets selected.

#### Example

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         $("#menu").kendoMenu({
             select: function(e) {
                 // handle event
             }
         });
    </script>

#### To set after initialization

    <ul id="menu">
        <li>Item 1
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
        <li>Item 2
            <ul>
                <li>Sub Item 1</li>
                <li>Sub Item 2</li>
                <li>Sub Item 3</li>
            </ul>
        </li>
    </ul>
    <script>
         // get a reference to the menu widget
         var menu = $("#menu").data("kendoMenu");
         // bind to the select event
         menu.bind("select", function(e) {
             // handle event
         });
    </script>

#### Event Data

##### e.item `Element`

The selected item
