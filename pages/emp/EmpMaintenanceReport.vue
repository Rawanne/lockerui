<template>
  <v-data-table
    v-model="selected"
    :headers="headers"
    :single-select="singleSelect"
    item-key="name"
    show-select
    :items="reports"
    sort-by="stuID"
    class="elevation-1">
    <template #top>
      <v-toolbar flat>
        <v-toolbar-title>Maintenance Reports</v-toolbar-title>
        <v-divider class="mx-4" inset vertical></v-divider>
        <v-spacer></v-spacer>
        <v-dialog v-model="dialog" max-width="500px">
          <template #activator="{on, attrs}">
            <v-btn color="primary" dark class="mb-2" v-bind="attrs" v-on="on"> New Report </v-btn>
          </template>
          <v-card>
            <v-card-title>
              <span class="text-h5">{{ formTitle }}</span>
            </v-card-title>

            <v-card-text>
              <v-container>
                <v-row>
                  <v-col cols="12" sm="6" md="4">
                    <v-text-field v-model="editedItem.name" label="Student name"></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6" md="4">
                    <v-text-field v-model="editedItem.stuID" label="Student ID"></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6" md="4">
                    <v-text-field v-model="editedItem.BuN" label="Building Number"></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6" md="4">
                    <v-text-field v-model="editedItem.LoN" label="Locker Number"></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6" md="4">
                    <v-text-field
                      v-model="editedItem.porblemDesc"
                      label="Problem desc"></v-text-field>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="blue darken-1" text @click="close"> Cancel </v-btn>
              <v-btn color="blue darken-1" text @click="save"> Save </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
        <v-dialog v-model="dialogDelete" max-width="515px">
          <v-card>
            <v-card-title class="text-h5"
              >Are you sure you want to check this report as done?</v-card-title
            >
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="blue darken-1" text @click="closeDelete">Cancel</v-btn>
              <v-btn color="blue darken-1" text @click="deleteItemConfirm">Yes</v-btn>
              <v-spacer></v-spacer>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-toolbar>
    </template>
    <template #[`item.actions`]="{item}">
      <v-icon small class="mr-2" @click="editItem(item)"> mdi-pencil </v-icon>
      <!-- <v-icon small @click="deleteItem(item)"> mdi-check </v-icon> -->
    </template>
    <template #no-data>
      <v-btn color="primary" @click="initialize"> Reset </v-btn>
    </template>
  </v-data-table>
</template>
<script>
export default {
  data: () => ({
    singleSelect: false,
    selected: [],
    dialog: false,
    dialogDelete: false,
    headers: [
      {
        text: 'Student Name',
        align: 'start',
        sortable: false,
        value: 'name',
      },
      {text: 'Student ID', value: 'stuID'},
      {text: 'Building number', value: 'BuN'},
      {text: 'Locker number', value: 'LoN'},
      {text: 'Problem desc', value: 'porblemDesc'},
      {text: 'Actions', value: 'actions', sortable: false},
    ],
    reports: [],
    editedIndex: -1,
    editedItem: {
      name: '',
      stuID: 0,
      BuN: 0,
      LoN: 0,
      porblemDesc: 'I cant open it',
    },
    defaultItem: {
      name: '',
      stuID: 0,
      BuN: 0,
      LoN: 0,
      porblemDesc: 'I cant open it',
    },
  }),

  computed: {
    formTitle() {
      return this.editedIndex === -1 ? 'New Report' : 'Edit Report'
    },
  },

  watch: {
    dialog(val) {
      val || this.close()
    },
    dialogDelete(val) {
      val || this.closeDelete()
    },
  },

  created() {
    this.initialize()
  },

  methods: {
    initialize() {
      this.reports = [
        {
          name: 'Rawan Yogurt',
          stuID: 159,
          BuN: 6.0,
          LoN: 24,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan sandwich',
          stuID: 237,
          BuN: 9.0,
          LoN: 37,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan Eclair',
          stuID: 262,
          BuN: 16.0,
          LoN: 23,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan Cupcake',
          stuID: 305,
          BuN: 3.7,
          LoN: 67,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan Gingerbread',
          stuID: 356,
          BuN: 16.0,
          LoN: 49,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan Jelly bean',
          stuID: 375,
          BuN: 0.0,
          LoN: 94,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan Lollipop',
          stuID: 392,
          BuN: 0.2,
          LoN: 98,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan Honeycomb',
          stuID: 408,
          BuN: 3.2,
          LoN: 87,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan Donut',
          stuID: 452,
          BuN: 25.0,
          LoN: 51,
          porblemDesc: 'I cant open it',
        },
        {
          name: 'Rawan KitKat',
          stuID: 518,
          BuN: 26.0,
          LoN: 65,
          porblemDesc: 'I cant open it',
        },
      ]
    },

    editItem(item) {
      this.editedIndex = this.reports.indexOf(item)
      this.editedItem = Object.assign({}, item)
      this.dialog = true
    },

    deleteItem(item) {
      this.editedIndex = this.reports.indexOf(item)
      this.editedItem = Object.assign({}, item)
      this.dialogDelete = true
    },

    deleteItemConfirm() {
      this.reports.splice(this.editedIndex, 1)
      this.closeDelete()
    },

    close() {
      this.dialog = false
      this.$nextTick(() => {
        this.editedItem = Object.assign({}, this.defaultItem)
        this.editedIndex = -1
      })
    },

    closeDelete() {
      this.dialogDelete = false
      this.$nextTick(() => {
        this.editedItem = Object.assign({}, this.defaultItem)
        this.editedIndex = -1
      })
    },

    save() {
      if (this.editedIndex > -1) {
        Object.assign(this.reports[this.editedIndex], this.editedItem)
      } else {
        this.reports.push(this.editedItem)
      }
      this.close()
    },
  },
}
</script>
