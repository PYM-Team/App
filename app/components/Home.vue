<template>
  <Page>
    <ActionBar title="Plan your murder !" />
    <ScrollView>
      <StackLayout class="home-panel">
        <!--Add your page content here-->
        <TextField
          v-model="textFieldValue"
          hint="Entrez votre code"
          maxlength="6"
          keyboardType="number"
          fontSize="40"
          textAlignment="center"
        />
        <Button text="Valider" @tap="buttonTapped(textFieldValue)" fontSize="20" />
      </StackLayout>
    </ScrollView>
  </Page>
</template>

<script>
import * as http from "http";
export default {
  methods: {
    buttonTapped(input) {
      //GET
      http
        .getJSON("https://rpplanner-api.herokuapp.com/api/games/" + input)
        .then(
          result => {
            this.gameJson = result;
            console.log(JSON.stringify(this.gameJson));
          },
          error => {
            console.log(error);
          }
        );
    },
    data() {
      return {
        textFieldValue: ""
      };
    }
  }
};
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