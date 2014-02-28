# Changelog

## 1.1.0

### Major changes

- `jquery__config` uses jQuery 2.x by default for modern browsers ([#319](https://github.com/bem/bem-core/issues/319)).
- Ability to use any BEMJSON as value of attributes in BEMHTML templates added ([#290](https://github.com/bem/bem-core/issues/290)).
- Dependencies in `i-bem__collection` fixed ([#292](https://github.com/bem/bem-core/issues/292)).
- `page` block's touch styles removed ([#306](https://github.com/bem/bem-core/issues/306)).
- `page` BEMHTML wrapping in production mode fixed ([#309](https://github.com/bem/bem-core/issues/309)).
- possible JavaScript error in script injection in IE<9 in `next-tick` fixed ([#324](https://github.com/bem/bem-core/issues/324)).
- `FastClick` initialisation in `jquery__event_type_pointerclick` of `touch.blocks` fixed ([#332](https://github.com/bem/bem-core/issues/332)).
- `node.js` tech bug on Windows systems fixed ([#274](https://github.com/bem/bem-core/issues/274)).
- `i-bem__dom_elem-instances` bug with `onElemSetMod` fixed ([#340](https://github.com/bem/bem-core/issues/340)).
- bemhtml from [bem-xjst](https://github.com/bem/bem-xjst) used ([#329](https://github.com/bem/bem-core/issues/329)).

### Other changes

- [ym](https://github.com/ymaps/modules) was updated to 0.0.12 ([#326](https://github.com/bem/bem-core/issues/326)).
- Do not flood `console` with messages if `i-bem__i18n` is not in debug mode ([#285](https://github.com/bem/bem-core/issues/285)).
- jsdoc for `dropElemCache()` method of `i-bem__dom` module fixed ([#296](https://github.com/bem/bem-core/issues/296)).
- Development infrastructure was updated to
  [bem-pr@v0.5.x](https://github.com/narqo/bem-pr/blob/0.5.3/HISTORY.md) ([#323](https://github.com/bem/bem-core/issues/323)).
- Russian documentation for `i-bem.js` was updated.
- [List of supported browsers](https://github.com/bem/bem-core/blob/v1/README.md#supported-browsers)
  was specified in project's README.
