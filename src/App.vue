<template>
  <div id="app" :class="$style.app">
    <h1>vue-columns-grid</h1>

    <h2>Properties</h2>
    <table :class="$style.documentationTable">
      <thead>
        <tr>
          <th>Poperty</th>
          <th>Type</th>
          <th>Default Value</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>columns</td>
          <td>Number <code>2</code>, Array of Numbers <code>[1,3,1]</code></td>
          <td>2</td>
          <td>Number sets amount of equal width columns. Array sets each number as column with fractional width.</td>
        </tr>
        <tr>
          <td>auto</td>
          <td>"fill" or "fit"</td>
          <td></td>
          <td>
            "fill" let's the grid items span the space that's left over after filling a line. "fit" will leave the space as is.
            <strong>This property makes the columns property beeing ignored.</strong>
          </td>
        </tr>
        <tr>
          <td>width</td>
          <td>Any valid css value for <code>width</code></td>
          <td>10em</td>
          <td>Sets the minmal width a grid item when "auto" property is set.</td>
        </tr>
        <tr>
          <td>gap</td>
          <td>Any valid css value for <code>grid-gap</code></td>
          <td></td>
          <td>
            Sets the distance between the grid items. Can be a single value like <code>1em</code>, to set horizonal and vertical spacing.
            Or you can use multiple values like <code>1em 3em</code>, to set seperate values for vertical and horizontal spacing.
          </td>
        </tr>
      </tbody>
    </table>

    <h2>Default</h2>
    <columns-grid>
      <div v-for="n in 7" :key="`grid-item-${n}`" :class="$style.item">Item {{n}}</div>
    </columns-grid>

    <h2>With gap</h2>
    <columns-grid
      gap="1em"
      >
      <div v-for="n in 7" :key="`grid-item-${n}`" :class="$style.item">Item {{n}}</div>
    </columns-grid>

    <h2>Custom column count (equal width)</h2>
    <columns-grid
      gap="1em"
      :columns="3"
      >
      <div v-for="n in 7" :key="`grid-item-${n}`" :class="$style.item">Item {{n}}</div>
    </columns-grid>

    <h2>Custom columns (different widths)</h2>
    <columns-grid
      gap="1em"
      :columns="[1,3,1]"
      >
      <div v-for="n in 7" :key="`grid-item-${n}`" :class="$style.item">Item {{n}}</div>
    </columns-grid>

    <h2>Auto-fit collumns with default minimal width (resize window width)</h2>
    <columns-grid
      gap="1em"
      auto="fit"
      >
      <div v-for="n in 7" :key="`grid-item-${n}`" :class="$style.item">Item {{n}}</div>
    </columns-grid>

    <h2>Auto-fill collumns with default minimal width (resize window width)</h2>
    <columns-grid
      gap="1em"
      auto="fill"
      >
      <div v-for="n in 7" :key="`grid-item-${n}`" :class="$style.item">Item {{n}}</div>
    </columns-grid>
  </div>
</template>

<script>
import ColumnsGrid from './components/ColumnsGrid.vue'

export default {
  name: 'app',
  components: {
    ColumnsGrid
  }
}
</script>

<style module lang="scss">
.app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}

.item {
  border: 1px solid hsl(0, 0%, 60%);
  background-color: hsl(0, 0%, 90%);
  padding: 1em;
}

.documentationTable {
  border-collapse: collapse;
}

.documentationTable th,
.documentationTable td {
  text-align: start;
  padding: 0.5em;
  border: 1px solid hsl(0, 0%, 60%);
}

code {
  padding: 0.1em;
  background-color: hsl(0, 0%, 90%);
  border-radius: 0.1em;
}

</style>
