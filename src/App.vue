<template>
  <h3>Tooltip Directive</h3>
  <p>
    Temporary solution for input type text is to wrap input element in span
    element
  </p>
  <span v-tooltip.tooltip="'Tooltip text'">
    <input type="text" />
  </span>

  <ul>
    <li v-for="item in items" :key="item.id">
      <span v-tooltip:right.tooltip="item.text">{{ item.text }}</span>
    </li>
  </ul>
  <br />
  <button v-tooltip:top>Tooltip on top</button>
  <button v-tooltip:bottom>Tooltip on bottom</button>
  <button v-tooltip:right>Tooltip on right</button>
  <button v-tooltip:left>Tooltip on left</button>
  <br />
  <br />
  <hr />
  <h3>Tooltip Component</h3>

  <h3>Props</h3>
  <table>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Type</th>
      <th>Required</th>
      <th>Default</th>
    </tr>
    <tr>
      <td>tooltipText</td>
      <td>set tooltip text</td>
      <td>string</td>
      <td>-</td>
      <td>Tooltip text</td>
    </tr>
    <tr>
      <td>position</td>
      <td>
        set tooltip position: <br /><code
          >"top" | "right" | "bottom" | "left"</code
        >
      </td>
      <td>string</td>
      <td>-</td>
      <td>top</td>
    </tr>
  </table>

  <h3>Usage</h3>

  <p>Position</p>
  <Tooltip><button>Tooltip top</button></Tooltip>
  <Tooltip position="right"><button>Tooltip right</button></Tooltip>
  <Tooltip position="left"><button>Tooltip left</button></Tooltip>
  <Tooltip position="bottom"><button>Tooltip bottom</button></Tooltip>
  <br />
  <hr />
  <p>Tooltip text</p>
  <Tooltip :tooltipText="'custom text'"
    ><button>Tooltip custom text</button></Tooltip
  >
</template>

<script>
import Tooltip from "./components/Tooltip.vue";
export default {
  name: "App",
  components: {
    Tooltip,
  },
  data() {
    return {
      items: [
        {
          id: 0,
          text: "lorem",
          completed: false,
        },
        {
          id: 1,
          text: "lorem 1",
          completed: false,
        },
        {
          id: 2,
          text: "lorem 2",
          completed: true,
        },
      ],
    };
  },
};
</script>

<style lang="scss">
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
  td,
  th {
    border: 1px solid #dddddd;
    text-align: center;
    padding: 8px;
  }
}
</style>