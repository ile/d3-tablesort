d3-tablesort
============

Sortable, scrollable table for [D3](http://d3js.org/).

## Install

Download the css and js files or do `bower install d3-tablesort`.

## Usage

### HTML

```html
<link rel="stylesheet" type="text/css" href="d3-tablesort/d3-tablesort.css">
<script src="d3-tablesort/d3-tablesort.js"></script>
```

### JavaScript

Creating the table:

```javascript
    TableSort(
        table_id,
        array_of_columns,
        array_of_data,
        dimensions
        );
```

#### table id

This should be a string like `"#my_table"`.

#### array of columns

*Array of columns* should be in the form of array of objects:

```javascript
    [
	    { text: 'Kunta', sort: TableSort.alphabet },
    	{ text: 'Osuus', sort: TableSort.numeric, sort_column: true }
	]
```

In the object a sorting function can be used if sorting wants to be enabled for that columns. There are two sorting functions available:

- `TableSort.alphabetic`
- `TableSort.numeric`

The column that will used for sorting by default can be denoted by `sort_column: true` property.

#### array of data

*Array of data* should be in the form of nested arrays. These should correspond to the array of columns, ie. the first item in the array (index 0) should correspond to index 0 in *array of columns*.

```javascript
	[
		[ 'Rautavaara', '99.73 %' ],
		[ 'Pelkosenniemi', '99.69 %' ],
		[ 'Kiikoinen', '99.68 %' ],
		[ 'Luhanka', '99.63 %' ],
		[ 'Reisjärvi', '99.6 %' ],
		[ 'Savukoski', '99.57 %' ]
	]
```

Data can also be given in the form of:

```javascript
	[
		{ attribute1: '...', attribute2: '...', attributeN: '...', data: [ 'Rautavaara', '99.73 %' ] },
		{ attribute1: '...', attribute2: '...', attributeN: '...', data: [ 'Pelkosenniemi', '99.69 %' ] },
		{ attribute1: '...', attribute2: '...', attributeN: '...', data: [ 'Kiikoinen', '99.68 %' ] },
		{ attribute1: '...', attribute2: '...', attributeN: '...', data: [ 'Luhanka', '99.63 %' ] },
		{ attribute1: '...', attribute2: '...', attributeN: '...', data: [ 'Reisjärvi', '99.6 %' ] },
		{ attribute1: '...', attribute2: '...', attributeN: '...', data: [ 'Savukoski', '99.57 %' ] }
	]
```

.. where attributes will be set to each row (`<tr>`). For example, you can bind [datasets](http://www.w3.org/TR/2011/WD-html5-20110113/elements.html) (e.g. `data-id`) to each row this way.

#### dimensions

For example:

```javascript
{ width: '400px', height: '700px' }
```

## Example output

![image](https://f.cloud.github.com/assets/433707/1214836/72cb2996-264c-11e3-8d98-50e671631df5.png)

## Credits

Inspired by, and initial code by: [http://devforrest.com/examples/table/table.php](http://devforrest.com/examples/table/table.php)
