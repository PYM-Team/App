<template>
    <Page>
        <ActionBar title="Plan your murder !"/>
        <ScrollView>
            <StackLayout class="home-panel">
                <!--Add your page content here-->
               <TextField v-model = "textFieldValue" 
                          hint = "Entrez votre code" 
                          maxLength = "6" 
                          keyboardType = "number"
                          fontSize = "40"
                          textAlignment = "center"/>
                <Button text = "Valider" 
                        @tap = "buttonTapped(textFieldValue)"
                        fontSize = "20"/>
            </StackLayout>
        </ScrollView>
    </Page>
</template>

<script>
export default {
    methods : {
        buttonTapped(input) {
            //vérifier si input == code de partie reçu par l'API
            console.log(input);
        }
    },
    data () {
        return {
            textFieldValue:""
        };
    },
}
</script>

<style scoped>
.home-panel {
    vertical-align: center;
    font-size: 20;
    margin: 15;
}

.description-label {
    margin-bottom: 15;
}
</style>