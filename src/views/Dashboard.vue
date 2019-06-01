<template>
  <div class="dashboard">
    <h1 class="subheading grey--text">Dashboard</h1>

    <v-container class="my-5">

      <v-card v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project Title</div>
            <div>{{project.title}}</div>
          </v-flex>
          <v-flex xs12 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-flex>
          <v-flex xs12 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div class="right">
              <v-chip small :class="`${project.status} white--text camption my-2`">{{project.status}}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  data(){
    return{
      projects:[
        {title: 'New website', person: 'Majstor Lux', due:'05.06.2019.', status:'ongoing', content:'  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!'},
        {title: 'New Footer', person: 'Majstor Mrkonja', due:'02.06.2019.', status:'complete', content:'  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!'},
        {title: 'New header', person: 'Majstor Brajstor', due:'03.06.2019.', status:'complete', content:'  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!'},
        {title: 'New whatever', person: 'Majstor Koji', due:'01.06.2019.', status:'overdue', content:'  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!'},
      ]
    }
  }
};
</script>

<style>
.project.complete{
  border-left:4px solid #3cd1c2
}
.project.ongoing{
  border-left:4px solid orange
}
.project.overdue{
  border-left:4px solid tomato
}
.v-chip.complete{
  background: #3cd1c2;
}
.v-chip.ongoing{
  background: #ffaa2c;
}
.v-chip.overdue{
  background: #f83e70;
}
</style>
