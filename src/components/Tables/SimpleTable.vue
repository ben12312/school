<template>
  <div>
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Name">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Country">{{ item.country }}</md-table-cell>
        <md-table-cell md-label="City">{{ item.city }}</md-table-cell>
        <md-table-cell md-label="Salary">{{ item.salary }}</md-table-cell>
      </md-table-row>
      <md-table-pagination
        :md-page-size="2"
        :md-page-options="[1,2,3,4,5,6]"
        :md-update="updatePagination"
        :md-data="users"
        :md-paginated-data.sync="paginatedUsers" />
    </md-table>
  </div>
</template>

<script>
export default {
  name: "simple-table",
  props: {
    tableHeaderColor: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      selected: [],
      paginatedUsers: [],
      users: [
        {
          id: 1,
          name: "Dakota Rice",
          salary: "$36,738",
          country: "Niger",
          city: "Oud-Turnhout",
        },
        {
          id: 2,
          name: "Minerva Hooper",
          salary: "$23,738",
          country: "Curaçao",
          city: "Sinaai-Waas",
        },
        {
          id: 3,
          name: "Sage Rodriguez",
          salary: "$56,142",
          country: "Netherlands",
          city: "Overland Park",
        },
        {
          id: 4,
          name: "Philip Chaney",
          salary: "$38,735",
          country: "Korea, South",
          city: "Gloucester",
        },
        {
          id: 5,
          name: "Doris Greene",
          salary: "$63,542",
          country: "Malawi",
          city: "Feldkirchen in Kārnten",
        },
        {
          id: 6,
          name: "Mason Porter",
          salary: "$78,615",
          country: "Chile",
          city: "Gloucester",
        },
      ],
    };
  },
  methods: {
    updatePagination() {
      console.log('masuk');
    }
  }
};
</script>
