Simple Grid
======

A human friendly, semantic, hybrid grid framework utilizing data attributes.

### Installation
_**If you're using either simple-framework, simple-child, or PressPlay - this is already included and handled via bower.**_

1. Import grid into project, `@import 'grid';`.
2. Import breakpoints mixin into project, `@import 'breakpoints'`;
3. Classes are by default, .container, .row, .columns.
4. Variable Settings
```
$container-class: 'foo';
$row-class: 'foo';
$column-class: 'bar';
$gutter: 3%; // spacing between columns
$max-columns: 6; //  @for loop class declarations
```
5. Class Syntax
```
.columns-{percentage, double digit}
.columns-70, .columns-30 = totaling to 100

.columns-{single digit number}
.columns-1
.columns-2, .columns-2
.columns-4, .columns-4, .columns-4, .columns-4
```
6. Gutter Classes
```
.no-gutter {
@include set-gutter(0);
}
.reset-gutter {
@include set-gutter($gutter);
}
```

### How to use
```
<div class="container"> // optional
	<div class="row"> // required
		<div class="columns-2"> // required
			50% column
    	</div>
		<div class="columns-2">
			50% column
    	</div>
	</div>
</div>
```

```
# For mixed widths, percentage based
<div class="row">
	<div class="columns-30"></div>
	<div class="columns-70"></div>
</div>

# Using data attributes
<div data-columns=".3"></div>
<div data-columns=".7"></div>

# For equal widths
<div class="columns-3"></div>
<div class="columns-3"></div>
<div class="columns-3"></div>

# Using data attributes
<div data-columns="3"></div>
<div data-columns="3"></div>
<div data-columns="3"></div>

# Nesting
<div class="columns-2">
	<div class="row">
		<div class="columns-2"></div>
    </div>
</div>
<div class="columns-2">
	<div class="row">
		<div class="columns-2"></div>
    </div>
</div>

# Scss
# @include container-fixed($gutter: $gutter, $padded: false);
# @include columns($num, $display: float, $gutter: $gutter);
# @include grid($display: float, $gutter: $gutter);
.example-element {
	@include breakpoint($small) {
    	@include columns(2);
    }
}
```

### License
Simple Grid is licensed under the GPL v2 license. (http://opensource.org/licenses/GPL-2.0)
