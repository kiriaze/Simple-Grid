S-Grid
======

A human friendly, semantic, hybrid grid framework following Simple's philosophy of SOMA.
It utilizes data attributes with fallbacks to classes and easily extendable. No bloat. Drop in friendly.


### Installation

_**If you're using either simple-framework, simple-child, PressPlay, SFE or Espresso - this is already included and handled via bower.**_

1. Import grid into project, `@import 'grid';`.
2. Import breakpoints mixin into project, `@import 'breakpoints'`;
	* Simple's breakpoint mixin is the first of its kind - stupid simple and mobile first approach.

### Settings

Classes are by default, .container, .row, .columns.

	$gutter: 			3% !default;
	$docWidth: 			100% !default;

	// this sets your class names
	$container-class:	"container" !default; // optional
	$row-class:			"row" !default;
	$column-class:		"columns" !default;
	$max-columns:		12 !default;

	// Grid check
	$gridDebug:			false !default; // If true, styles grid/columns for easy visibily while testing


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

### Basic Usage

	<section>

        <div class="container">

            <div class="row">

                <div class="columns-2">

                    A column with a width of 50%. Fixed to 2 columns.

                </div>

                <div class="columns-2">

                    A column with a width of 50%. Fixed to 2 columns.

                </div>

            </div>

            <div class="row">

                <div class="columns-50">

                    An alternate method for a column with 50% width. This should be used for multiple columns with different widths, all equaling to 100%.

                </div>

                <div class="columns-30">

                    A column with 30% width.

                </div>

                <div class="columns-20">

                    A column with 20% width.

                </div>

            </div>

        </div>

	</section>

	<div class="container"> // optional - for fixed with breakpoints

		<div class="row"> // required

			<div class="columns-2">

	        	<div class="row">  // Nesting

					<div class="columns-2">

					</div>

	                <div class="columns-2">

	                </div>

			    </div>

	        </div>

			<div class="columns-2">

			</div>

		</div>

	</div>


## Advanced usage

By setting the custom class variables for your columns and container in your _base.scss, _settings.scss, or _variables.scss you can work with Espresso more semantically.

	# For mixed widths, percentage based

	<div class="row">

		<div class="columns-30"> // default classes

		</div>

		<div class="customClass-4"> // custom classes

		</div>

		<div data-columns=".3"> // Using data attributes

		</div>

	</div>

	# For equal widths

	<div class="row">
		<div class="columns-3"> // default classes

		</div>

		<div class="customClass-3"> // custom classes

		</div>

		<div data-columns="3"> // Using data attributes

		</div>

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
