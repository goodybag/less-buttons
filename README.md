# Buttons

__Usage:__

package.json

```javascript
"dependencies": {
  "less-buttons": "goodybag/less-buttons"
}
```

```less
@import "./node_modules/less-buttons/index.less";

// Initialize default settings
#components > .btns();
#components > .btn-groups( 640px ); // Must specify breakpoint

.btn {
  // Add Default sizing
  #components > .btn-size(
    40px          // Height
  , 18px          // Left/Right padding
  , 1px           // Border width
  , 1px           // Border-bottom width
  , 14px          // Font Size
  );

  // Default Color
  #components > .btn-theme(
    #fff        // Background
  , #555        // Text Color
  );

  // Large sizing
  .btn-large {
    #components > .btn-size( 50px, 22px, 1px, 2px, 18px );    
  }

  // Themes
  .btn-primary    { #components > .btn-theme( red, white ); }
  .btn-secondary  { #components > .btn-theme( blue, white ); }
  .btn-tertiary   { #components > .btn-theme( green, white ); }
}

.btn-group {
  // Setup default button group theme
  #components > .btn-group-theme(
    #eee    // @background
  , #efefef // @background-hover
  , #e5e5e5 // @background-active
  , #555    // @text-color
  , #555    // @border-color
  );

  // Default butotn group sizing
  > & {
    #components > .btn-size( 32px, 22px, 0, 0, 12px );
  }
}
```

This module is split up into two kinds of APIs:

__Top-Level__

Top-Level APIs create classes, and setup the basic structure and naming conventions for a component.

__Class-Level__

Class-Level APIs rely on the consumer to mixin to an existing class. These are for theming and changing sizing.

## API

### Top-Level

#### `.btns()`

Creates the `.btn` class and basic structure for all Goodybag buttons.

#### `.btn-groups( @breakpoint )`

Creates the `.btn-group` class and basic structure for Button Groups

__Parameters__

* `@breakpoint` - Describes when the button group changes layout (horizontal vs. vertical)

### Class-Level

#### `.btn-size( @height, @side-padding, @bwidth, @bbwidth, @font-size )

Mixes in size-related properties into a button. This is also used to control the size of a button group.

__Parameters__

* `@height` - Height of the button (padding and border included)
* `@side-padding` - Left and right padding
* `@bwidth` - Base border width
* `@bbwidth` - Border Bottom Width
* `@font-size` - Size of font

#### `.btn-theme( @background, @color )`

Sets the color scheme for a button. Calls the more specific version `.btn-theme(...)` but with the rest of the arguments gleaned by changing alpha values of @background/@color.

#### `.btn-theme( @bg, @bg-hover, @bg-active, @border-color, @color )`

Sets the color scheme for a button.

__Parameters__

* `@bg` - background color
* `@bg-hover` - background hover color
* `@bg-active` - background active color
* `@border-color` - Border color
* `@color` - text color

#### `.btn-group-theme( @bg, @bg-hover, @bg-active, @border-color, @color )`

Sets the color scheme for a button group.

__Parameters__

* `@bg` - background color
* `@bg-hover` - background hover color
* `@bg-active` - background active color
* `@border-color` - Border color
* `@color` - text color