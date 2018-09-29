<template>
    
     <Page>
        <ActionBar title="AtChecker - Control de Asistencia"/>
        <GridLayout colums="*" rows="*">
            <Label class="message" :text="'Seleccione la Fecha'" col="0" row="0"/>            
            <ListPicker :items="listOfItems" />
        </GridLayout>
    </Page>

</template>

<style scoped>
    Label{
        text-align: center;
    }

    ListPicker{
        background-color: antiquewhite;
        height: 100;
    }
    GridLayout{
        background-color: beige;
    }
</style>

<script>
export default {
    data(){
        return{
            listOfItems: ['Enero', 'Febrero' , 'Marzo'],
            selectedItem:0
        }
    }
}
</script>
