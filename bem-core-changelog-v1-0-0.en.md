# Changelog

## 1.0.0

### Major changes

- Modular system [ym](https://github.com/ymaps/modules) is used.
- All deprecated methods from `i-bem` and `i-bem__dom` were removed.
- `i-bem` now has no dependency on jQuery. `i-bem__dom` still depends on jQuery.
- BEMHTML-template can be written with [JS-syntax](https://gist.github.com/veged/6150760).
- New tech `bemtree` (based on [bem-xjst](https://github.com/bem/bem-xjst))
  for describing dynamic generation of BEM-tree was introduced.
- New tech `vanilla.js` for JS-implementations that does not depend on particular JS-engine was introduced.
- New techs `browser.js` и `node.js` for JS-implementations targeted corresponding engines was introduced.
  For backward compatibility we assume that `.js`-files contains `browser.js` implementation.
- Polyfill (`jquery__event_type_pointer` and `jquery__event_type_pointerclick` as a jQuery-plugins)
  for universalize desktop and touch pointer events was introduced.
- System for unit testing and blocks examples generation was introduced.
- "Simple" modifiers' (modifiers without value) support in `i-bem` and BEMHTML was introduced.

### Other changes

- Prefixes in all block names (except `i-bem`) were removed.
- Block `i-bem__dom` becomes a module (in terms of [ym](https://github.com/ymaps/modules))
  and all `BEM.DOM`-block must define additions to `i-bem__dom` ([example](https://github.com/bem/bem-core/blob/v1/common.bundles/index/blocks/b-square/b-square.js)).
- Method for blocks declaration (`.decl()`) does not accept object with `name` field as first parameter.
  Required form with `block` field: `BEM.decl({ block: 'b1', modName: 'm', modVal: 'v' }, ...)`.
- `nextTick` method as replacement for `afterCurrentEvent` method
  for ensure of block existence in callback invocation time was introduced.
  `BEM.afterCurrentEvent` is **deprecated**.
- New `channels` module instead of `BEM.channel` were introduced. `BEM.channel` is **deprecated**.
- `changeThis` is **deprecated**. Use native `bind` instead.
- `del` method from `i-bem` block was removed.
- `getWindowSize` method from `i-bem__dom` block was removed. Use `BEMDOM.win.width()` and `BEMDOM.win.height()`.
- `jquery` module-wrapper for providing jQuery was introduced.
  If jQuery already included into the page module-wrapper provides it. Otherwise it loads jQuery (version 1.10.1) on its own.
- `$.observable` becomes `events` module and not longer depends on jQuery.
- `$.inherit` becomes `inherit` module and not longer depends on jQuery.
- `$.identify` becomes `identify` module and not longer depends on jQuery.
- `$.throttle` splits into two modules: `functions__throttle` and `functions__debounce`, they both not longer depend on jQuery.
- `$.decodeURI`, `$.decodeURIComponent` moves to `querystring__uri` module and not longer depends on jQuery.
- `$.cookie` becomes `cookie` module and not longer depends on jQuery.
- `ua` module instead of `$.browser` (with same interface) was introduced.
- Use `pointerclick` instead of `leftclick`. It provides by `jquery__event_type_pointerclick` polyfill.
- `i-system` block splits into two modules: `idle` and `tick`.
- Triggers for modifiers changes now splitted into two groups:
  before setting new value (`beforeSetMod` and `beforeElemSetMod`)
  and after the value has been set (`onSetMod` and `onElemSetMod`).
  Cancellation of modifiers change is possible only from `before*`-triggers.
- Using of `{ onSetMod : { js : function() { ... } } }` is **deprecated**, use `onSetMod: { js : { inited : ... } } }`.
- `destruct` method from `i-bem` block is **deprecated**.
  Use supplementary trigger for `_js` modifiers:
  `onSetMod: { js : { inited : ... } } }` — `{ onSetMod : { js : { '' : ... } } }`.
- `exractParams` method from `i-bem__dom` block is **deprecated**.
  Use `elemParams` method for access to elements params.
- `trigger` method from `i-bem` block is **deprecated** in flavor of `emit` method.
- `onFirst` method from `i-bem` block is **deprecated** in flavor of `once` method.
- **Deprecated** field `e.block` that provided block-target of BEM-events was removed. Use `e.target` field instead.
- Field `e.data.domElem` that provided DOM-element of block in DOM-events was removed. Use `$(e.currentTarget)` (provided by jQuery).
- Parameter for `findElem` method that allows to search elements
  of particular block instance (in case of nested blocks with same name) was introduced.
- Possibility to point particular function in `unbindFrom*` methods was introduced.
- `objects` module for work with JS-objects was introduced. It contains methods: `extend`, `isEmpty`, `each`.
- `functions` module for work with JS-functions was introduced. It contains methods: `isFunction`, `noop`.
- `dom` module for work with DOM-tree was introduced.
- `querystring` module for work with URL-based strings was introduced.
- `loader_type_js` module for JS loading was introduced.
- `vow` module for Promises/A+ was introduced.
- `next-tick` module as polyfill for `nextTick`, `setImmediate`, `setTimeout(0, ...` and etc was introduced.
- `strings__escape` module for XML, HTML and attributes escaping was introduced.
- `inherit` module now supports mixins.
- `invokeAsap` parameter for `functions__throttle` module that allows to delay first invocation was introduced.
