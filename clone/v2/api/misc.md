---
title: Miscellaneous
layout: v2
class: apidoc
---

{% include v2/api-tabs.html %}


### <a name="version"></a> riot.version

The current version number as String: `'{{ site.v2_version }}'`


### <a name="brackets"></a> riot.settings.brackets

A global Riot setting to customize the start and end tokens of the expressions. For example


``` js
riot.settings.brackets = '[% %]'
```

let's you write expressions `<p>[% like_this %]</p>`. The start and end is separated with a space character.

### <a name="asyncrendertimeout"></a> riot.settings.asyncRenderTimeout

It allows you to change the `riot.renderAsync` timeout (default 1000ms)

```js
riot.settings.asyncRenderTimeout = 2000 // ms
```

### <a name="tmpl-errors"></a> riot.util.tmpl.errorHandler

Utility hook function to catch all the errors swallowed by the riot template engine

```js
riot.util.tmpl.errorHandler = function (err) {
  console.error(err.message + ' in ' + err.riotData.tagName) // your error logic here
}
```

### <a name="vdom"></a> riot.vdom

Expose the internal riot tags cache in order to query, debug, filter.. all the tags instances created

```js
  riot.tag('foo', '<p>{ msg }</p>', function() {
    this.msg = 'hi'
  })
  riot.mount('foo')
  console.log(riot.vdom[0].msg) // 'hi'
```
