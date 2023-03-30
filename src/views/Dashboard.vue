<template>
  <div class="team">
    <h1 class="subheading grey--text">Dashboard</h1>
    <v-container >
      <v-layout row wrap>
         <v-flex
        sm6
        xs12
        md6
        lg3
      >
       <v-card class="ma-3">
    <v-list-item  >
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-btn class="ma-2">
      <v-sheet color="green" width="80" height="80" elevation="10">        
            <v-icon dark large  style="color: white;">mdi-hospital-building</v-icon>        
      </v-sheet>
    </v-btn>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">Hospital</div>
        <v-list-item-title class="headline mb-1 text-right" >160</v-list-item-title>
        <div><v-divider></v-divider></div>
      </v-list-item-content> 
    </v-list-item>
    <v-card-actions>
      <v-icon text class="ma-2">mdi-hospital-building</v-icon>
      <div class="overline">Hospital</div>
    </v-card-actions>
  </v-card>
      </v-flex>
       <v-flex
        sm6
        xs12
        md6
        lg3
      >
       <v-card class="ma-3">
    <v-list-item>
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-btn class="ma-2">
        <v-sheet color="#F44336" width="80" height="80" elevation="10">
              <v-icon dark large style="color: white;">mdi-monitor-dashboard</v-icon>
        </v-sheet>
      </v-btn>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">Server</div>
        <v-list-item-title class="headline mb-1 text-right" >+200</v-list-item-title>
        <div><v-divider></v-divider></div>
      </v-list-item-content> 
    </v-list-item>
    <v-card-actions>
      <v-icon text class="ma-2">mdi-monitor-dashboard</v-icon>
      <div class="overline">Server&Storage</div>
    </v-card-actions>
  </v-card>
      </v-flex>
       <v-flex
        sm6
        xs12
        md6
        lg3
      >
       <v-card class="ma-3">
    <v-list-item>
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-btn class="ma-2">
        <v-sheet color="#03A9F4" width="80" height="80" elevation="10">
              <v-icon dark large  style="color: white;">mdi-finance</v-icon>
        </v-sheet>
      </v-btn>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">Statistics</div>
        <v-list-item-title class="headline mb-1 text-right" >150</v-list-item-title>
        <div><v-divider></v-divider></div>
      </v-list-item-content> 
    </v-list-item>
    <v-card-actions>
      <v-icon text class="ma-2">mdi-finance</v-icon>
      <div class="overline">Statistics</div>
    </v-card-actions>
  </v-card>
      </v-flex>
       <v-flex
        sm6
        xs12
        md6
        lg3
      >
       <v-card class="ma-3">
    <v-list-item >
       <v-list-item-avatar
        tile
        class="mt-n7"
      >
      <v-btn class="ma-2">
        <v-sheet color="#FFC107" width="80" height="80" elevation="10">
              <v-icon dark large  style="color: white;">mdi-account-wrench</v-icon>
        </v-sheet>
      </v-btn>
      </v-list-item-avatar>
      <v-list-item-content>
        <div class="overline text-right">P.M.</div>
        <v-list-item-title class="headline mb-1 text-right" >273</v-list-item-title>
        <div><v-divider></v-divider></div>
      </v-list-item-content> 
    </v-list-item>
    <v-card-actions>
      <v-icon text class="ma-2">mdi-account-wrench</v-icon>
      <div class="overline">P.M.</div>
    </v-card-actions>
  </v-card>
      </v-flex>      
      <!-- add -->
          
      <v-row class="mt-n6">
            <v-col cols="12" sm="7">
              <v-chart class="chart mt-2" :option="option" />
            </v-col>
          <v-col cols="12" md="5" sm="12">
           <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n2">
          <v-toolbar-title>Callhome</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn rounded small >See All</v-btn>
          </v-toolbar>
            <v-simple-table class="grey lighten-3">
              <template v-slot:default>
                <tbody>
                  <tr
                    v-for="item in orders"
                    :key="item.name"
                  >
                    <td>{{ item.id }}</td>
                    <td>{{ item.title }}</td>
                    <td>{{ item.state }}</td>
                    <td>{{ item.count }}</td>
                    <td><v-icon small>{{ item.icon }}</v-icon></td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
          </v-col>
          </v-row>
      <!-- end -->

      <v-flex xs24 sm12 md12 lg12 xl12>
          <v-card
            class="mx-auto"            
            prepend-icon="mdi-home"
          >          
        </v-card>
      </v-flex>
        <v-flex xs6 sm6 md6 lg4 xl4 v-for="person in team" :key="person.name">
              <v-card class="text-center ma-3">
                <v-responsive class="pt-4">
                   <v-avatar size="100" class="red lighten-2">
                     <img :src="person.avatar" alt="" >
                   </v-avatar>
                </v-responsive>
                <v-card-text>
                  <div class="subheading">{{person.name}}</div>
                  <div class="grey--text">{{person.role}}</div>
                </v-card-text>
                <v-card-actions>
                    <v-btn outlined color="orange">
                        <v-icon small left >message</v-icon>
                        <span>Message</span>
                    </v-btn>
                </v-card-actions>
              </v-card>
        </v-flex>
       
      </v-layout>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { PieChart } from "echarts/charts";
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent
} from "echarts/components";
import VChart, { THEME_KEY } from "vue-echarts";
use([
  CanvasRenderer,
  PieChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent
]);

export default {
  name: 'team',
  data : () => ({
    team: [
      {name: 'Iyad', role: 'web developer', avatar:'/img1.png'},
      {name: 'Reda', role: 'Graphic designer', avatar:'/img2.png'},
      {name: 'Zineb', role: 'web developer', avatar:'/img3.png'}
    ],
    orders: [
          {
            id: 'SCG',
            title: 'DELL',
            state: 'Secure Connect Gateway',
            count: 6,
            icon: 'fas fa-ellipsis-h'
          },
           {
            id: 'XCA',
            title: 'LENOVO',
            state: 'XClarity Administrator',
            count: 8,
            icon: 'fas fa-ellipsis-h'
          },
          {
            id: 'iLOAP',
            title: 'HPE',
            state: 'iLO Amplifier Pack',
            count: 4,
            icon: 'fas fa-ellipsis-h'
          },
          {
            id: 'CHS',
            title: 'Huawei',
            state: '--',
            count: 4,
            icon: 'fas fa-ellipsis-h'
          },
         
        ],
        option: {
        title: {
          text: "Physical Hardware",
          left: "left"
        },
        tooltip: {
          trigger: "item",
          formatter: "{a} <br/>{b} : {c} ({d}%)"
        },
      
        series: [
          {
            name: "Traffic Sources",
            type:"pie",
            radius: "55%",
            center: ["45%", "50%"],
            data: [
              { value: 335, name: "EMC" },
              { value: 310, name: "Huawei" },
              { value: 234, name: "DELL" },
              { value: 135, name: "HPE" },
              { value: 1548, name: "LENOVO" }
            ],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0)"
              }
            }
          }
        ]
        }

        }),
        components: {
          VChart          
        },
        provide: {
          [THEME_KEY]: "green"
        } 
      }

</script>
