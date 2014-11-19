jQuery Templates plugin 1.0.1
====

This is the fork of jQuery Templates that we use internally here at Kanban Solutions. We have fixed all known and encountered bugs as well as changing the syntax from the standard.


Docs
====

[jQuery.tmpl()](http://web.archive.org/web/20120921051311/http://api.jquery.com/jquery.tmpl/),
[jQuery.template()](http://web.archive.org/web/20120920134621/http://api.jquery.com/jQuery.template/)


.tmpl( [data] [, options] )
----

Take the first element in the matched set and render its content as a template, using the specified data. Identical to the [.tmpl() method](http://web.archive.org/web/20120921052001/http://api.jquery.com/tmpl/) of the original jQuery Templates.

* `data` - the data to render. If `data` is an array, the template is rendered once for each data item in the array.
* `options` - an optional map of user-defined key-value pairs. Extends the tmplItem data structure, available to the template during rendering.


.template( [name] )
----

Returns a compiled template, created from the content of the first matched element. If the `name` parameter is provided, the compiled template is stored as a named template, and can be referenced using the specified string. Identical to the [.template() method](http://web.archive.org/web/20120921051534/http://api.jquery.com/template/) of the original jQuery Templates.


{%= fieldNameOrExpression %}
----

Used for insertion of data values in the rendered template. Evaluates the specified field (property) on the current data item, or the specified JavaScript function or expression. Identical to the [${} tag](http://web.archive.org/web/20120919114126/http://api.jquery.com/template-tag-equal/) of the origional jQuery Templates.


{%html fieldNameOrExpression %}
----

Used for insertion of HTML markup strings in the rendered template. Evaluates the specified field on the current data item, or the specified JavaScript function or expression. Identical to the [{{html}} tag](http://web.archive.org/web/20120921045613/http://api.jquery.com/template-tag-html/) of the origional jQuery Templates.


{%if fieldNameOrExpression %}
----

Used for conditional insertion of content. Renders the content between the opening and closing template tags only if the specified data item field, JavaScript function or expression does not evaluate to false (or to zero, null, type "undefined", or the empty string). Identical to the [{{if}} tag](http://web.archive.org/web/20120919113534/http://api.jquery.com/template-tag-if/) of the origional jQuery Templates.


{%elif fieldNameOrExpression %}
----

Used in association with the `{{if}}...{{/if}}` tag to provide alternative content based on the values of one or more expressions. The `{%elif%}` tag can be used with a parameter, as in: `{%if a%}...{%elif b%}...{%/if%}`.

_Added because the old system actualy overloaded the else tag to handle elif as well and I didnt like that_


{%else%}
----

Used in association with the `{{if}}...{{/if}}` tag to provide alternative content based on the values of one or more expressions. The `{%else%}` tag can be used without a parameter, as in: `{%if a%}...{%elif b%}...{%else%}...{%/if%}`

Almost identical to the [{{else}} tag](http://web.archive.org/web/20120921044917/http://api.jquery.com/template-tag-else/) of the origional jQuery Templates, but I removed the ability to do `{{else _test_}}`.


{%each( index, value ) collection %}
----

Used to iterate over a data array, and render the content between the opening and closing template tags once for each data item. Identical to the [{{each}} tag](http://web.archive.org/web/20120919111023/http://api.jquery.com/template-tag-each/) of the origional jQuery Templates.


{%tmpl( [data] [, options] ) template %}
----

Used for composition of templates. Identical to the [{{tmpl}} tag](http://web.archive.org/web/20120921050105/http://api.jquery.com/template-tag-tmpl/) of the original jQuery Templates.

* `data` - the data to render. If `data` is an array, the template is rendered once for each data item in the array.
* `options` - an optional map of user-defined key-value pairs. Extends the tmplItem data structure, available to the template during rendering.
* `template` - a template's name (see `.template()` and `jQuery.template()`) or the HTML markup to use as a template. Note: the parameter **can't be a jQuery selector** as in the original jQuery Templates.


{%wrap( [data] [, options] ) template %}
----

The tag is similar to the `{%tmpl%}` tag, except that it provides additional support for incorporating wrapped HTML content into the rendered output. Identical to the [{{wrap}} tag](http://web.archive.org/web/20120921043756/http://api.jquery.com/template-tag-wrap/) of the original jQuery Templates.
