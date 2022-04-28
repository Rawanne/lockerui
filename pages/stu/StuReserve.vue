<template>
 <v-app>
  <v-container fluid>
    <div>
        <v-responsive :aspect-ratio="40 /12">
          <form action="">
            <v-row align="center">
              <v-col class="d-flex" cols="12" sm="4">
                <v-select :items="cbuilding" label="Choose Building Number" color="#D43256"></v-select>
              </v-col>
              <v-col class="d-flex" cols="12" sm="4" >
                <v-select :items="clocker" label="Choose number of Locker" color="#D43256"></v-select>
              </v-col>
              <v-col class="d-flex" cols="12" sm="4">
                <v-select  :items="cterm" label="Choose subscription term" color="#D43256"></v-select>
              </v-col>
            </v-row>
            <v-row justify="center">
              <v-col align="center">
                <v-dialog v-model="dialog" persistent max-width="450" >
                  <template  #activator="{on, attrs}">
                    <v-btn  color="#D43256"  rounded dark v-bind="attrs" v-on="on">confirm</v-btn>    
                  </template>
                  <v-card>
                    <v-card-title class="text-h5">
                      Are you sure about this information?
                    </v-card-title>
                    <v-card-text>
                      if you are sure about this informtaion thats you mean you are agreed in our
                      term of service and privcy.
                    </v-card-text>
                    <v-card-actions>
                      <v-spacer></v-spacer>
                      <v-btn color="red darken-1" text @click="dialog = false"> Disagree </v-btn>
                      <v-btn color="green darken-1" text @click="dialog = false"> Agree </v-btn>
                    </v-card-actions>
                  </v-card>
                </v-dialog>
              </v-col>
             
            </v-row>
          </form>
          
        </v-responsive> 
   <img src="/vectortwo.png"  width="80%" />
  
    </div>
  </v-container>
   </v-app>
</template>

<script>
export default {
  name: 'StuReserve',
  data: () => ({
    cbuilding: ['Building 1', 'Building 2', 'Building 3', 'Building 4'],
    clocker: ['Locker 1', 'Locker 2', 'Locker 3'],
    cterm: ['Term 1', 'Term 2'],
    dialog: false,
  }),
}
</script>
<style scoped>
#app{
  height: 308.72px;
}
.v-responsive {
  display: flex;
  align-items: center;
}
</style>