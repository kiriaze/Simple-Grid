Simple Grid
======

A human friendly, semantic, hybrid grid framework utilizing data attributes and following Simple's philosophy of SOMA.

### Installation
_**If you're using either simple-framework, simple-child, or PressPlay - this is already included and handled via bower.**_

1. Import grid into project, `@import 'grid';`.
2. Import breakpoints mixin into project, `@import 'breakpoints'`;
	• Note about _breakpoints.scss - First of its kind.

### Settings
1. Classes are by default, .container, .row, .columns.
2. Variable Settings

```
$gutter: 			3% !default;
$docWidth: 			100% !default;

// this sets your class names
$container-class:	"container" !default; // optional
$row-class:			"row" !default;
$column-class:		"columns" !default;
$max-columns:		12 !default;

// Grid check
$gridDebug:			false !default; // If true, styles grid/columns for easy visibily while testing
```

### Syntax
1. Class Syntax
```
.columns-{percentage, double digit} for mixed columns
	.columns-70, .columns-30 = totaling to 100

.columns-{single digit number} for equal coloumns
	.columns-1
	.columns-2, .columns-2
	.columns-4, .columns-4, .columns-4, .columns-4
```

2. Gutter Classes

```
.no-gutter {
	@include set-gutter(0);
}
.reset-gutter {
	@include set-gutter($gutter);
}
```

### Usage
```
<div class="container"> // optional - for fixed with breakpoints
	<div class="row"> // required
		<div class="columns-2"> // required
        	<div class="row">  // Nesting
				<div class="columns-2"></div>
                <div class="columns-2"></div>
		    </div>
        </div>
		<div class="columns-2"></div> // required
	</div>
</div>

# For mixed widths, percentage based
<div class="row">
	<div class="columns-30"></div> // default classes
	<div class="customClass-4"></div> // custom classes
	<div data-columns=".3"></div> // Using data attributes
</div>

# For equal widths
<div class="row">
	<div class="columns-3"></div> // default classes
	<div class="customClass-3"></div> // custom classes
	<div data-columns="3"></div> // Using data attributes
</div>

# Scss
# @include container-fixed($gutter: $gutter, $padded: false);
# @include columns($num, $display: float, $gutter: $gutter);
# @include grid($display: float, $gutter: $gutter);
.example-wrapper {
	@include grid();
	.example-column {
		// note: including columns within breakpoint mixin is required.
		@include breakpoint($small) {
    		@include columns(2);
    	}
	}
}
```

### To Do's & Considerations
1. Consider re implementing inline block and flex as gridTypes.
```
// method for %ib layout fix for spacing consider
@font-face{
    font-family: 'NoSpace';
    src: url('../Fonts/zerowidthspaces.eot');
    src: url('../Fonts/zerowidthspaces.eot?#iefix') format('embedded-opentype'),
         url('../Fonts/zerowidthspaces.woff') format('woff'),
         url('../Fonts/zerowidthspaces.ttf') format('truetype'),
         url('../Fonts/zerowidthspaces.svg#NoSpace') format('svg');
}

body {
    font-face: 'OpenSans', sans-serif;
}

.inline-container {
    font-face: 'NoSpace';
}

.inline-container > * {
    display: inline-block;
    font-face: 'OpenSans', sans-serif;
}
```

### License
Simple Grid is licensed under the GPL v2 license. (http://opensource.org/licenses/GPL-2.0)
