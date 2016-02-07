# [S-Grid](http://getsimple.io)

S-Grid is a modern CSS framework based on [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes).

## Quick install

Try it out now:

```npm install sgrid```

Feel free to raise an issue or submit a pull request. In the meantime, check the [documentation](https://gist.github.com/kiriaze/463b12ac9958189ae0b4).

## Copyright and license

Code copyright 2014 Constantine Kiriaze. Code released under [the GNU public license](https://github.com/kiriaze/s-grid/blob/master/LICENSE).

---

A human friendly, semantic, hybrid grid framework following Simple's philosophy of SOMA.
It utilizes data attributes with fallbacks to classes and easily extendable. No bloat. Drop in friendly.


### Installation

_**If you're using either simple-child, PressPlay, SFE or Juice - this is already included and handled via bower.**_

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

3. Default Usage https://gist.github.com/kiriaze/463b12ac9958189ae0b4
```
<div class="container"> // optional
	<div class="row">
		<div class="columns-2"></div>
		<div class="columns-2"></div>
	</div>
</div>
```

4. Custom Usage
```
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
1. Consider re implementing inline block and flex as gridTypes? Or stick to fallback to floats with Modernizr or just have the user pick which grid to implement through param.
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
