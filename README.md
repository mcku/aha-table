# &lt;aha-table&gt; ![Bower Version](https://badge.fury.io/bo/aha-table.svg)

> A Polymer element for a searchable, sortable, paginatable, inline-editable, selectable, copyable, removable table/grid.

## Demo

[Check it live!](http://liuwenchao.github.io/aha-table)

[Performance Test!](http://liuwenchao.github.io/aha-table/performance.html)


## Usage

1. Install the component using [Bower](http://bower.io/):

    ```sh
    $ bower install aha-table --save
    ```

2. Import Web Components' polyfill:

    ```html
    <script src="bower_components/platform/platform.js"></script>
    ```

3. Import Custom Element:

    ```html
    <link rel="import" href="bower_components/aha-table/dist/aha-table.html">
    ```

4. Start using it!

    ```html
    <aha-table></aha-table>
    ```

    ```html
    <aha-table
          selectable="true" 
          copyable="true"
          seachable="true"
          pagesize="20" 
          pagesizetitle="Page Size:" 
          summarytitle="Viewing">

          <aha-column name="title" 
              type="string" 
              sortable="true"
              searchable="true"
              required="true"
              editable="false"
              placeholder="Empty Field Placeholder Text" 
              default="" 
              hint="a hint in column header">
          </aha-column>
     </aha-table>
    ```

## Options

Attribute       | Options       | Default   | Description
---             | ---           | ---       | ---
`data`          | *Array*       | []        | data for this table, need to set in JS.
`selectable`    | *Boolean*     | True      | if selection box is displayed
`searchable`    | *Boolean*     | True      | if search row is displayed
`copyable`      | *Boolean*     | True      | if copy handler is displayed
`removable`     | *Boolean*     | True      | if remove handler is displayed
`pagesize`      | *Number*      | 10        | record set size for each page
`data-sizelist` | *Array*       | [5, 10, 20, 50, 100]      | list for page size dropdown
`selecttitle`   | *String*      | undefined | title for select checkbox
`selectalltitle`| *String*      | undefined | title for selectall checkbox
`copytitle`     | *String*      | undefined | title for copy indicator
`deletetitle`   | *String*      | undefined | title for remove indicator
`sorttitle`     | *String*      | undefined | title for sortable column
`edittitle`     | *String*      | undefined | title for editable data cell
`searchtitle`   | *String*      | undefined | title for search filter row toggler
`firsttitle`    | *String*      | undefined | title for first page clicker
`previoustitle` | *String*      | undefined | title for previous page clicker
`nexttitle`     | *String*      | undefined | title for next page clicker
`lasttitle`     | *String*      | undefined | title for last page clicker
`copyclass`     | *String*      | undefined | customized class for copy handler
`removeclass`   | *String*      | undefined | customized class for remove handler
`hintclass`     | *String*      | undefined | customized class for hint element in header
`pagetext`      | *String*      | undefined | text before current page number
`pageoftext`    | *String*      | undefined | text between page range and total page number
`pagesizetext`  | *String*      | undefined | text before page size dropdown
`summarytitle`  | *String*      | undefined | text before pagination summary
`itemoftext`    | *String*      | undefined | text between item count range and total item number
`filtershownclass`    | *String*      | undefined | customized class of filterrow when filter row is shown
`filterhiddenclass`   | *String*      | undefined | customized class of filterrow when filter row is hidden


## Options for aha-column

Attribute           | Options                   | Default               | Description
---                 | ---                       | ---                   | ---
`name`              | *String*                  | undefined             | name of the column
`label`             | *String*                  | undefined             | this text woll be displayed as the column name in table header.
`type`              | *String*                  | undefined             | one of: string, text, choice, boolean, date, time, datetime
`sortable`          | *Boolean*                 | True                  | if this column is sortable
`searchable`        | *Boolean*                 | True                  | if this column is searchable
`editable`          | *Boolean*                 | True                  | if this column is editable
`required`          | *Boolean*                 | True                  | if this column is required, Event 'after-invalid' will be invoked
`placeholder`       | *String*                  | undefined             | this text will be displayed when this cell is empty
`default`           | *String*                  | undefined             | default value, applied at creation
`data-choices`      | *Array*                   | []                    | options for select dropdown, in editing and searching.
`hint`              | *String*                  | undefined             | this text will be displayed at the column header for instruction.
`searchplaceholder` | *String*                  | undefined             | this text will be displayed in search filter input box.

## Events

Name                    | Arguments | Description
---                     | ---       | ---
`after-invalid`         | `Event`   | call after saving a cell by it's invalid
`after-td-click`        | `Event`   | call after user click a cell, usually after this cell is editable
`after-td-dbclick`      | `Event`   | call after user dbclick a cell
`before-create`         | `Event`   | call before a record is created internally
`after-create`          | `Event`   | call after a record is created internally
`before-copy`           | `Event`   | call before a record is copyed from another internally
`after-copy`            | `Event`   | call after a record is copyed from another internally
`before-remove`         | `Event`   | call before a record is removed internally
`after-remove`          | `Event`   | call after a record is removed internally

## Browser Compatability

By following http://www.polymer-project.org/docs/polymer/databinding-compat.html ,
this should be working on all latest version of browsers.

![IE](https://raw.github.com/paulirish/browser-logos/master/internet-explorer/internet-explorer_48x48.png) | ![Chrome](https://raw.github.com/paulirish/browser-logos/master/chrome/chrome_48x48.png) | ![Firefox](https://raw.github.com/paulirish/browser-logos/master/firefox/firefox_48x48.png) | ![Opera](https://raw.github.com/paulirish/browser-logos/master/opera/opera_48x48.png) | ![Safari](https://raw.github.com/paulirish/browser-logos/master/safari/safari_48x48.png)
--- | --- | --- | --- | --- |
IE 10+ ✔ | Latest ✔ | Latest ✔ | Latest ✔ | Latest ✔ |


## Development

In order to run it locally you'll need to fetch some dependencies and a basic server setup.

1. Install [Bower](http://bower.io/) & [Grunt](http://gruntjs.com/):

    ```sh
    $ [sudo] npm install -g bower grunt-cli
    ```

2. Install local dependencies:

    ```sh
    $ bower install && npm install
    ```

3. To test your project, start the development server and open `http://localhost:8000`.

    ```sh
    $ grunt
    ```

4. Once you finish developing it, build the distribution files and publish it on Bower.

    ```sh
    $ grunt build
    $ bower register aha-table https://github.com/liuwenchao/aha-table
    ```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

For detailed changelog, check [Releases](https://github.com/liuwenchao/aha-table/releases).

## License

[MIT License](http://opensource.org/licenses/MIT)
