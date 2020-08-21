# xpack
An algorithm conducts circle packing by best satisfying node horizontal constraints of input data items.

The algorithm was used in generating the conversational thread visualization in a journal paper: J. Zhao, N. Cao, Z. Wen, Y. Song, Y.-R. Lin, and C. Collins, [#FluxFlow: Visual Analysis of Anomalous Information Spreading on Social Media.](https://www.jeffjianzhao.com/papers/fluxflow.pdf) IEEE Transactions on Visualization and Computer Graphics (Proceedings of VAST 2014), 20(12), pp. 1773-1782, Dec 2014. [Bibtex](https://www.jeffjianzhao.com/papers/fluxflow.bib)

<a href="http://www.cs.toronto.edu/~jianzhao/webapp/FluxFlow/example/example.html"><img src="http://www.cs.toronto.edu/~jianzhao/webapp/FluxFlow/example/example.png" /></a>

## var pack = xpack();
Creates a new pack layout with the default settings.

### pack.xpos([<i>xpos</i>])
If <i>xpos</i> is specified, sets the accessor to the specified function. If <i>xpos</i> is not specified, returns the current accessor, which assumes that the input data is an object with a numeric <i>x</i> attribute.

### pack.radius([<i>radius</i>])
If <i>radius</i> is specified, sets the accessor to the specified function. If <i>radius</i> is not specified, returns the current accessor, which assumes that the input data is an object with a numeric <i>r</i> attribute.

### pack.score([<i>score</i>])
If <i>score</i> is specified, sets the accessor to the specified function. If <i>score</i> is not specified, returns the current accessor, which assumes that the input data is an object with a numeric <i>score</i> attribute.

### pack(<i>data</i>, [<i>packscore</i>])
Runs the pack layout that represents all the input <i>data</i> items above the <i>packscore</i> threshold as circles by best satisfying their horizontal constraints. If <i>packscore</i> is not specified, the default is 0. Assumes <i>data</i> is an arrary of objects with numeric attributes: <i>x</i>, <i>r</i>, and <i>score</i>. If <i>score</i> is not specified with the input objects, simply packs all the data items (so that <i>packscore</i> is redudant).

Returns an object with the following information. <br />
<i>nodes</i> - the packed nodes with <i>px</i> and <i>py</i> as their positions; <br />
<i>rect</i> - the bounding box of the layout: {<i>xMin</i>, <i>xMax</i>, <i>yMin</i>, <i>yMax</i>}; <br />
<i>outline</i> - the upper and lower border nodes of the packed layout: {<i>up</i>, <i>down</i>}.

## How to use

##### Choice 1. Global

Adding this library via ```<script>``` tag is the simplest way. By doing this, ```xpack``` is available in the global scope.

```
<script src="xpack.js"></script>
```

##### Choice 2: AMD

If you use requirejs, xpack support AMD out of the box.

```
require(['path/to/xpack'], function(xpack) {
  // do something
});
```

##### Choice 3: CommonJS

xpack also supports usage in commonjs style.

```
var xpack = require('path/to/xpack');
```
