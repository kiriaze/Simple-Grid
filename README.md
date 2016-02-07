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
