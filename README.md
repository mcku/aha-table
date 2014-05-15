# &lt;aha-table&gt; ![Bower Version](https://badge.fury.io/bo/aha-table.svg)

> A Polymer element for a searchable, sortable, paginatable, inline-editable, selectable table/grid.

## Demo

[Check it live!](http://liuwenchao.github.io/aha-table)

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

## Options

Attribute       | Options       | Default   | Description
---             | ---           | ---       | ---
`data`          | *Array*       | []        | data for this table
`selectable`    | *Boolean*     | True      | if selection box is displayed
`searchable`    | *Boolean*     | True      | if search row is displayed
`copyable       | *Boolean*     | True      | if copy handler is displayed
`removable`     | *Boolean*     | True      | if remove handler is displayed
`copyclass`     | *Boolean*     | undefined | customized class for copy handler
`removeclass`   | *Boolean*     | undefined | customized class for remove handler
`pagesize`      | *Boolean*     | 10        | record set size for each page
`searchtitle`   | *Boolean*     | undefined | text for search row
`pagesizetitle` | *Boolean*     | undefined | text before page size dropdown
`summarytitle`  | *Boolean*     | undefined | text before pagination summary
`data-sizelist` | *Boolean*     | [5, 10, 20, 50, 100]      | list for page size dropdown


## Options for aha-column

Attribute           | Options                   | Default               | Description
---                 | ---                       | ---                   | ---
`name`              | *String*                  | undefined             | name of the column
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

## Envents

Name                    | Arguments                 | Description
---                     | ---                       | ---
`after-invalid`         | `Object` *detail*         | call after saving a cell by it's invalid
`after-td-click`        | `Object` *detail*         | call after user click a cell, usually after this cell is editable
`after-td-dbclick`      | `Object  *detail*         | call after user dbclick a cell
`after-create`          | `Object` *new record*     | call after a record is created internally
`after-copy`            | `Object` *new record*     | call after a record is copyed from another internally
`after-remove`          | `Object` *removed record* | call after a record is removed internally

## Compatability

By following http://www.polymer-project.org/docs/polymer/databinding-compat.html ,
this should be working on all latest version of browsers 


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
