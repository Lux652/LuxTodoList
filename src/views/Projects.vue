<template>
  <div class="projects">
    <h1 class="subheading grey--text">Projects</h1>

    <v-container class="my-5">

      <v-expansion-panel>
        <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
          <div slot="header">{{project.title}}</div>
          <v-card>
            <v-card-text class="px-4 grey--text">
              <div class="font-weight-bold">due by {{project.due}}</div>
              <div>{{project.content}}</div>
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-container>
  </div>
</template>

<script>
export default {
  data(){
    return{
      projects: [
        {
          title: "New website",
          person: "Majstor Luka",
          due: "05.06.2019.",
          status: "ongoing",
          content:
            "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!"
        },
        {
          title: "New Footer",
          person: "Majstor Luka",
          due: "02.06.2019.",
          status: "complete",
          content:
            "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!"
        },
        {
          title: "New header",
          person: "Majstor Brajstor",
          due: "03.06.2019.",
          status: "complete",
          content:
            "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!"
        },
        {
          title: "New whatever",
          person: "Majstor Koji",
          due: "01.06.2019.",
          status: "overdue",
          content:
            "  Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quaerat dicta aliquid explicabo!"
        }
      ]
    }
  },
  computed:{
    myProjects(){
      return this.projects.filter(project =>{
        return project.person === 'Majstor Luka'
      })
    }
  }
};
</script>
