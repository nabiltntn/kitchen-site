Version History
===============

0.9.11
------

- Fixed bug in forms: required checkbox fields are now really required

- Vertical menus `.nav-stacked` : menu item can have subitems (and parent item is collapsible)

- Fixed small issue with html parser: textarea had extra tab characted inside content


0.9.10
------

- Forms: for input type "select" now you can combine items from collection (lookup) with static items (input_items). Useful if you need first item to be static (usually empty) and rest of items from collection.

- Forms: added new input type: "crud". For fields with `"type": "array"` and `"array_item_type": "object"` you can define `"input": "crud"` and define `"crud_fields": [...]` - that will produce CRUD inside your form.

- Fixed few bugs and maybe made new ones :)


0.9.9
-----

- Looks like I am close to 1.0 but I am not: Next version will be 0.9.10 :)

- There was bug preventing user to change own profile. Fixed now. Check <a href="http://generator-accounts.meteor.com" target="_blank">example-accounts</a>.

- Built-in "form" component will show error (if any occurs) while writing data

- "page" object now have "back_route" property and if you set this, button with left arrow will appear just before page title

- "component" and "page" objects now have "title_icon_class" property, so you can add for example "fa fa-home" and that will appear before page title



0.9.8
-----

- Minor bugfixes


0.9.7
-----

- CLI: Fixed bug in forms with checkbox when field type is "bool" (checkbox was not displayed)

- CLI: Fixed bug with accessing restricted pages: in some circumstances, authenticated user without access rights was able to access restricted page by directly entering page url (user was not able to see data if your collection is properly secured)


0.9.6
-----

- Added "container_class" property to "page" and "zone" objects. CSS class to be added to page container. For example "container-fluid". Default: "container"

- Added "icon_class" property to "menu_item" object. If set, "span" with this class will be added to menu item before title. So, now you can set menu item icons.


0.9.5
-----

- GUI: Fixed bug - sometimes multiple editors for single field appeared

- GUI: Added javascript hints in editor

- CLI: Fixed bugs in HTML to JADE converter


0.9.4
-----

- GUI: Added two examples

- GUI: Added syntax check (lints) into JSON and JS editors

- CLI: Fixed json parser bug: if key name is a string it's now properly stringified to javascript: { "\"x.y\"": 1 } now becomes { "x.y": 1 }

- CLI: Fixed bug related to query object: if some component's query doesn't have a name, generator reported error. Now it just ignores queries without names.


0.9.3
-----

- GUI: integrated <a href="http://codemirror.net/" target="_blank">CodeMirror</a> editor

- GUI: few improvements

- GUI: tree editor and object editor pages were generator plugins - now they are changed to regular components. 

- CLI: Page now can have "zoneless" property. If set to true page will be accessible both for authenticated and non-authenticated users.


0.9.2
-----

- GUI: fixed **many bugs**

- GUI: added possibility to delete object from array (that was somehow missing)

- Added new component type "custom_component" with possibility to provide custom HTML and JS code. Component of type "custom" is deprecated now (still working for backward compatibility). 

- Changed how plugins work


0.9.1
-----

- Reset password form was broken. It's fixed now.

- GUI - object properties form: while form submit is in progress, button is now in disabled state.


0.9.0
-----

- Added <a href="{{urlFor 'login'}}">kitchen-GUI</a> - visual application generator. Built (of course) with meteor-kitchen itself. Just <a href="{{urlFor 'login'}}">login</a> and enjoy! :)

- Fixed some bugs with HTML parser


0.8.0
-----

- Added new example: simple **invoicing application**. See it <a href="http://generator-invoices.meteor.com" target="_blank">live</a>, source is <a href="https://github.com/perak/kitchen-examples/tree/master/example-invoices" target="_blank">here</a>.

- Fixed some bugs


0.7.9
-----

- Added "bootswatch-paper" theme


0.7.8
-----

- First run is now much faster - meteor-kitchen now adds all packages in a single "meteor add ..." command.

- Added "route_params" property to MenuItem object.


0.7.7
-----

- Input file now can be in <a href="http://www.yaml.org/" target="_blank">YAML</a> format. Input YAML file must have extension ".yml" or ".yaml". You need to install <a href="https://www.npmjs.org/package/yaml2json" target="_blank">yaml2json</a>.

- Fixed few bugs


0.7.6
-----

- Input file argument now can be URL

- Improved processing custom components

- Fixed some minor bugs related to Meteor 1.0


0.7.5
-----

- Meteor 1.0 support

- Query object now has "options" member (second argument to collection.find and collection.findOne). See <a href="http://www.meteorkitchen.com/api_reference#query">query</a> object.

- You can specify date format for "datepicker" form controls. See <a href="http://www.meteorkitchen.com/api_reference#field">field</a> object, property "format".

- Collection field "default" property now can be "today" (current date) and "now" (current date and time).

- Fixed some bugs in HTML parser and improved parsing performance.


0.7.4
-----

- Added **datepicker input** control into Form component. You need to set `"type": "date"` and `"input": "datepicker"` into field definition.

- Added **export to CSV/TSV/JSON** button into DataView component. You need to set `"exportable": true` into field definitions. Clicking "Export" button will download data currently shown in DataView with fields marked as "exportable". Download is done client side using URI download and HTML5 download attribute (I didn't tested with IE, but I guess it doesn't work). See live example <a href="http://generator-dataview.meteor.com/customers" target="_blank">here</a>.


0.7.3
-----

- Added built-in **change password form**. Now along with "login", "logout", "register" and "forgot_password" pre-built templates, there is also "change_pass". See accounts example <a href="http://generator-accounts.meteor.com" target="_blank">here</a> (login and go to profile settings).

- Markup for dropdown menu item (menu item with sub-items) is now properly generated.

- DataView now can search fields that have dot inside name (for example "profile.name").
