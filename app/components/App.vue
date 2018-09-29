<template>
    <Page>
        <ActionBar title="AtChecker"/>
        <DockLayout stretchLastChild="true" >
          <Label dock="left" width="40" />
          <Label dock="top" height="40" />
          <Label dock="right" width="40" />
          <Label dock="bottom" />

          <FlexboxLayout flexDirection="column">
            <Label class="p-20" textWrap=true height=70 text="Sistema de Control de Asistencia"/>

            <TextField class="center" v-model="studentId" hint="Codigo estudiantil..." />
            <TextField secure="true" class="center" v-model="password" hint="Contraseña..." />

            <Button text="Iniciar Sesión" @tap="login" />
          </FlexboxLayout>  
      </DockLayout>
    </Page>
</template>

<script>
import Info from "../components/Info";
import * as http from "http";

export default {
  data() {
    return {
      msg: "Hello World!",
      detailPage: Info,
      studentId: "",
      password: "",
      studenName: ""
    };
  },
  methods: {
    login() {
      const str = "https://hqnode.azurewebsites.net/api/login/" + this.studentId + "/" + this.password;      
        http
          .getJSON(str)
          .then(
            result => {              
              const student = JSON.parse(JSON.stringify(result));
              if (student.Id !== -1) {
                alert('Bienvenido ' + student.NombreUsuario);
                this.$navigateTo(Info);                
              } else {
                alert(student.NombreUsuario);
              }
            },
            error => {
              alert("error");
              // console.log(error);
            }
          );

      // alert('Your message');
      // this.$navigateTo(Info);
    }
  }
};
</script>

<style scoped>
ActionBar {
  background-color: #343434;
  color: #fcfaf1;
}

Page {
  background-color: #fcfaf1;
}

button {
  background-color: #343434;
  color: #fcfaf1;
}

.message {
  vertical-align: center;
  text-align: center;
  font-size: 20;
  color: #333333;
}

.center {
  text-align: center;
}
</style>
