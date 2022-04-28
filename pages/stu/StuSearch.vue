<template>
  <v-card color="#f87979" dark :loading="isUpdating">
    <template #progress>
      <v-progress-linear absolute color="green lighten-3" height="4" indeterminate>
      </v-progress-linear>
    </template>
    <v-img height="200" src="/bannar.jpg">
      <v-row>
        <v-col class="text-right" cols="12">
          <v-menu bottom left transition="slide-y-transition">
            <template #activator="{on, attrs}">
              <v-btn icon v-bind="attrs" v-on="on">
                <v-icon>mdi-dots-vertical</v-icon>
              </v-btn>
            </template>
            <v-list>
              <v-list-item @click="isUpdating = true">
                <v-list-item-action>
                  <v-icon>mdi-cog</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                  <v-list-item-title>Update</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-menu>
        </v-col>
        <v-row class="pa-4" align="center" justify="center">
          <v-col class="text-center">
            <h3 class="text-h5">Search for locker</h3>
            <span class="white--text text--lighten-1">looking for available lockers</span>
          </v-col>
        </v-row>
      </v-row>
    </v-img>
    <v-form>
      <v-container>
        <v-row>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="name"
              :disabled="isUpdating"
              filled
              color="blue lighten-2"
              label="Building Number"></v-text-field>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="title"
              :disabled="isUpdating"
              filled
              color="blue-grey lighten-2"
              label="Locker number"></v-text-field>
          </v-col>
          <v-col cols="12">
            <v-autocomplete
              v-model="results"
              :disabled="isUpdating"
              :items="lockersgroup"
              filled
              chips
              color="blue-grey lighten-2"
              label="Select"
              item-text="name"
              item-value="name"
              multiple>
              <template #selection="data">
                <v-chip
                  v-bind="data.attrs"
                  :input-value="data.selected"
                  close
                  @click="data.select"
                  @click:close="remove(data.item)">
                  <v-avatar left>
                    <v-img :src="data.item.avatar"></v-img>
                  </v-avatar>
                  {{ data.item.name }}
                </v-chip>
              </template>
              <template #item="data">
                <template v-if="typeof data.item !== 'object'">
                  <v-list-item-content v-text="data.item"></v-list-item-content>
                </template>
                <template v-else>
                  <v-list-item-avatar>
                    <img :src="data.item.avatar" />
                  </v-list-item-avatar>
                  <v-list-item-content>
                    <!-- eslint-disable vue/no-v-html -->
                    <v-list-item-title v-html="data.item.name"></v-list-item-title>
                    <v-list-item-subtitle v-html="data.item.group"></v-list-item-subtitle>
                    <!--eslint-enable-->
                  </v-list-item-content>
                </template>
              </template>
            </v-autocomplete>
          </v-col>
        </v-row>
      </v-container>
    </v-form>
    <v-divider></v-divider>
    <v-card-actions>
      <v-switch
        v-model="autoUpdate"
        :disabled="isUpdating"
        class="mt-0"
        color="green lighten-2"
        hide-details
        label="Auto Update"></v-switch>
      <v-spacer></v-spacer>
      <v-btn
        :disabled="autoUpdate"
        :loading="isUpdating"
        color="blue-grey darken-3"
        depressed
        @click="isUpdating = true">
        <v-icon left> mdi-update </v-icon>
        Update Now
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  data() {
    const srcs = {
      1: '/logo.png',
      2: '/logo.png',
      3: '/logo.png',
      4: '/logo.png',
      5: '/logo.png',
    }

    return {
      autoUpdate: true,
      results: [],
      isUpdating: false,
      name: 'Search for locker',
      lockersgroup: [
        {header: 'Group 1'},
        {name: 'locker 1', group: 'Group 1', avatar: srcs[1]},
        {name: 'locker 2', group: 'Group 1', avatar: srcs[2]},
        {name: 'locker 3', group: 'Group 1', avatar: srcs[3]},
        {name: 'locker 4', group: 'Group 1', avatar: srcs[2]},
        {divider: true},
        {header: 'Group 2'},
        {name: 'locker 5', group: 'Group 2', avatar: srcs[4]},
        {name: 'locker 6 ', group: 'Group 2', avatar: srcs[5]},
        {name: 'locker 7', group: 'Group 2', avatar: srcs[1]},
        {name: 'locker 8', group: 'Group 2', avatar: srcs[3]},
      ],
      title: 'looking for available lockers',
    }
  },

  watch: {
    isUpdating(val) {
      if (val) {
        setTimeout(() => (this.isUpdating = false), 3000)
      }
    },
  },

  methods: {
    remove(item) {
      const index = this.results.indexOf(item.name)
      if (index >= 0) this.results.splice(index, 1)
    },
  },
}
</script>