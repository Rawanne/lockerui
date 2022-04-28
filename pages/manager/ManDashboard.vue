<template>
  <v-container>
    <v-row>
      <v-col>
        <v-banner color="#f87979" shaped
          ><v-icon>mdi-locker-multiple</v-icon> number of Used locker 150
        </v-banner>
      </v-col>
      <v-col>
        <v-banner color="#f87979" shaped><v-icon>mdi-cash</v-icon> SAR 5000 </v-banner>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="text-center">
        <div>
          <ApexChart
            width="650"
            height="350"
            type="bar"
            :options="chartOptions"
            :series="series"></ApexChart>
        </div>
      </v-col>
        <v-col>
        <div id="chart">
          <ApexChart type="donut" height="350" width="350" :options="chartOptions2" :series="series2"></ApexChart>
        </div>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="text-center">
        <div id="chart">
          <ApexChart type="line" height="350" :options="chartOptions" :series="series"></ApexChart>
        </div>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="text-center">
        <v-card max-width="450" class="mx-auto">
          <v-toolbar color="#f87979" dark>
            <v-toolbar-title>Last Month Activites</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon>
              <v-icon>mdi-magnify</v-icon>
            </v-btn>
          </v-toolbar>
          <v-list three-line>
            <template v-for="(item, index) in items">
              <v-subheader v-if="item.header" :key="item.header" v-text="item.header"></v-subheader>
              <v-divider v-else-if="item.divider" :key="index" :inset="item.inset"></v-divider>
              <v-list-item v-else :key="item.title">
                <v-list-item-avatar>
                  <v-img :src="item.avatar"></v-img>
                </v-list-item-avatar>
                <v-list-item-content>
                  <!--eslint-disable-next-line vue/no-v-html -->
                  <v-list-item-title v-html="item.title"></v-list-item-title>
                  <!--eslint-disable-next-line vue/no-v-html -->
                  <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </template>
          </v-list>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'BarChart',
  components: {},
  data() {
    return {
      chartOptions: {
        chart: {
          id: 'vuechart-example',
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
      },
      series: [
        {
          name: 'series-1',
          data: [30, 40, 35, 50, 49, 60, 70, 91],
        },
      ],
      items: [
        {header: 'Monthly Activites'},
        {
          avatar: '/logo.png',
          title: 'Adding new building',
          subtitle: `<span class="text--primary">lorem</span> &mdash; lab lab lab`,
        },
        {divider: true, inset: true},
        {
          avatar: '/logo.png',
          title: 'locker maintenance <span class="grey--text text--lighten-1">Succefful</span>',
          subtitle: `<span class="text--primary">lorem</span> &mdash; lab lab lab`,
        },
      ],
      series2: [44, 55, 41, 17, 15],
      chartOptions2: {
        chart: {
          type: 'donut',
        },
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200,
              },
              legend: {
                position: 'bottom',
              },
            },
          },
        ],
      },
    }
  },
}
</script>
