<template>
  <div class="AddRemove">
    <div>
      <ul>
        <li v-for="(row, index) in rows">
          <p>name : <input type="text" /></p>
          <p>job : <input type="text" /></p>
          <a @click="removeRow(index)">Remove</a>
        </li>
      </ul>
      <div>
        <button class="button btn-primary" @click="addRow">Add row</button>
      </div>
    </div>
  </div>
</template>

<script>
import Axios from "axios";

export default {
  data() {
    return {
      rows: [{ name: "", job: "" }]
    };
  },
  methods: {
    addRow: function() {
      this.rows.push({ name: "", job: "" });
    },
    removeRow: function(row) {
      this.rows.splice(index, 1);
    }
  },
  computed: {}
};
</script>
