<template>
  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <SideBar></SideBar>
    <v-divider class="mt-1" color="white"></v-divider>
    <v-container>
      <v-row>
        <v-col cols="12" sm="12">
          <v-toolbar class="mt-n5" flat color="rgba(0,0,0,0)">
            <v-toolbar-title>Dashboard</v-toolbar-title>
          </v-toolbar>
          <v-row class="px-5 mt-n6 ml-5">
            <v-col cols="12" sm="3" v-for="(list,index) in lists" :key="index">
              <v-card
                align="center"
                color="#f9faf0"
                class="rounded-circle border pt-10"
                width="200"
                height="200"
                flat
              >
                <v-icon size="60" color="#2ebfaf">{{ list.icon }}</v-icon>
                <v-card-text class="grey--text text-lg-h6">
                  {{ list.title }}
                </v-card-text>
                <v-btn
                  absolute
                  color="#2Ebfaf"
                  class="white--text"
                  fab
                  left
                  top
                >
                  <h2>{{ list.count }}</h2>
                </v-btn>
              </v-card>
            </v-col>
          </v-row>
          <v-row class="mt-n5">
            <v-col cols="12" sm="7">
              <History></History>
            </v-col>
            <v-col cols="12" sm="5"> <Appointment /></v-col>
          </v-row>
          <v-row class="mt-n12">
            <v-col cols="12" sm="12">
              <Table />
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import SideBar from "../components/SideBar.vue";
import Table from "../components/Table.vue";
import History from "../components/History.vue";
import Appointment from "../components/Appointment.vue";
export default {
  components: {
    SideBar,
    History,
    Appointment,
    Table,
  },
  data: () => ({
    lists: [
      {
        icon: "fas fa-user-md",
        title: "Active Doctors",
        count: 21,
      },
      {
        icon: "fas fa-procedures",
        title: "Active Patients",
        count: 41,
      },
      {
        icon: "fas fa-user-nurse",
        title: "Active Nurses",
        count: 35,
      },
      {
        icon: "fas fa-hospital",
        title: "Representative",
        count: 15,
      },
    ],
  }),
};
</script>

<style scoped>
.border {
  border: 2px solid #2ebfaf;
}
.v-btn--fab.v-size--default.v-btn--absolute.v-btn--top {
  top: 65px !important;
}
.v-btn--absolute.v-btn--left,
.v-btn--fixed.v-btn--left {
  left: -26px !important;
}
</style>
