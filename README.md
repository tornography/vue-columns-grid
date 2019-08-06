# vue-columns-grid

This is a [vuejs](https://vuejs.org/) component to replace the commonly used [bootstrap grid](https://getbootstrap.com/docs/4.3/layout/grid/) or the corresponding [bootstrap vue components](https://bootstrap-vue.js.org/docs/components/layout). It's ment to use css grid on the parent, to simplify the usage of common grid setups.

## Usage
```
import ColumnsGrid from 'vue-columns-grid'
```

## Example

This example shows the usage of all possible properties. See table below to see combinations and overrides.

```
<columns-grid gap="1em">
    <!-- items -->
</columns-grid>
```

## Properties

| Poperty | Type | Default Value | Description |
|---------|------|---------------|-------------|
| columns | Number 2, Array of Numbers [1,3,1] | 2 | Number sets amount of equal width columns. Array sets each number as column with fractional width. |
| auto | "fill" or "fit" | | "fill" let's the grid items span the space that's left over after filling a line. "fit" will leave the space as is. This property makes the columns property beeing ignored. |
| width | Any valid css value for width | 10em | Sets the minmal width a grid item when "auto" property is set. |
| gap | Any valid css value for grid-gap | | Sets the distance between the grid items. Can be a single value like 1em, to set horizonal and vertical spacing. Or you can use multiple values like 1em 3em, to set seperate values for vertical and horizontal spacing. |


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Run your unit tests
```
npm run test:unit
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
