<template>
    
     <Page>
        <ActionBar title="AtChecker - Control de Asistencia"/>
        <StackLayout colums="5" rows="5">
            <Label class="message" :text="'Seleccione Mes'"/>            
            <ListPicker :items="listOfItems" width="50%" horizontalAlignment="center"/>
            <StackLayout orientation="horizontal">
                <Button width="45%">Mostrar Reporte</Button>
                <Button width="45%">Hoy!</Button>
            </StackLayout>
        </StackLayout>
    </Page>

</template>

<style scoped>
label {
  text-align: center;
  margin-top: 1cm;
  color: cornflowerblue;
}
button {
  background-color: #f0f0f0;
  margin-left: 5mm;
  margin-right: 5mm;
  height: 50;
}

Message {
  top: 2cm;
  font-size: 1rem;
}

ListPicker {
  height: 80;
}
</style>

<script>
export default {
  data() {
    return {
      listOfItems: [
        "Enero",
        "Febrero",
        "Marzo",
        "Abril",
        "Mayo",
        "Junio",
        "Julio",
        "Agosto",
        "Septiembre",
        "Octubre",
        "Noviembre",
        "Diciembre"
      ],
      selectedItem: 0
    };
  }
};
</script>
