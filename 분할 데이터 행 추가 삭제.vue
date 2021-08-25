<template>
  <div class="AddRemv">
    <div style="width: 321px">
      <ul v-for="(row, index) in data" :key="row">
        {{
          index
        }}
        <li v-for="(row1, index1) in row.resourceList" :key="row1.file">
          {{ row1.file }} <input />
        </li>
        <div v-for="(row2, index2) in row.metricList" :key="row2">
          {{ row.metricList }} / {{ index2 }}
          <li v-for="test in row2" :key="test.name">
            {{ test.name }}<input :v-bind="test.value" />
          </li>
          <td>
            <button
              @click="removeRow(index2, row.metricList)"
              v-if="index2 != 0"
            >
              Remove
            </button>
          </td>
        </div>
        <td>
          <button class="button btn-primary" @click="addRow()">
            Add row
          </button>
        </td>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [
        {
          resourceList: [{ file: "filename" }],
          metricList: [
            [
              { name: "test1", namek: "테스트1", value: "" },
              { name: "test2", namek: "테스트2", value: "" },
              { name: "test3", namek: "테스트3", value: "" }
            ]
          ]
        }
      ]
    };
  },
  methods: {
    addRow() {
      let ml = this.data[0].metricList;
      ml.push(ml[0]);
    },
    removeRow(index) {
      let ml = this.data[0].metricList;
      ml.splice(index, 1);
    }
  },
  computed: {}
};
</script>
