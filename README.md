## 说明
 
### 解决原版在多入口打包CSS的情况下的BUG

## Install

```node
npm install rollup-plugin-less-loader --save
```

## usage

```js
import './test.less';
//generate css will be auto insert to the head tag if you set insert be true
```

```js
import { rollup } from 'rollup';
import less from 'rollup-plugin-less-loader';

rollup({
    entry: 'main.js',
    plugins: [
        less()
    ]
});
```


## Options

### insert

+ Default: `false`
+ Type: `Boolean`

If you specify `true`, the plugin will insert compiled CSS into `<head/>` tag.

### output

+ Default: `rollup.build.css`

+ Type: `String|Function`

If you specify a string, it will be the path to write the generated CSS.
If you specify a function, call it passing the generated CSS as an argument.

### include

+ Default: `[ '**/*.less', '**/*.css' ]`

+ Type: `String|Array`

Minimatch pattern or array of minimatch patterns to determine which files are transpiled by the plugin.

### exclude

+ Default: `node_modules/**`

+ Type: `String|Array`

Minimatch pattern or array of minimatch patterns to determine which files are explicitly not transpiled by the plugin, overrules the `include` option.

### option

+ Type: `Object`

Options for [less](http://lesscss.org/usage/#programmatic-usage).
