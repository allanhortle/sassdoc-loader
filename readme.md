# sassdoc-loader

```
npm install sassdoc-loader --save-dev
```

Uses [SassDoc] to load your docs as a javascript object. Useful for rolling your own sassdoc theme.  


## Usage

```
var myDocs = require("!!sassdoc-loader!./sassfile.scss");
```

_Note: The double !! before the loader makes sure to disable all loaders specified in the config file. See: [webpack loader order]_


## Caveats

Sassdoc and Webpack traverse files in different ways; sassdoc uses a globbing mechanism while webpack only uses files that are explicitly required from the entry point. Because of this we use [sass-import-resolve] to find all the files inside the required sass file. If you don't have one standard entry point to your sass you may need to create a separate `docs.scss` file that lists all individual files.

Any better solutions to this problem would be much appreciated. 


[sass-import-resolve]: https://www.npmjs.com/package/sass-import-resolve
[webpack loader order]: https://webpack.github.io/docs/loaders.html#loader-order
[SassDoc]: http://sassdoc.com/