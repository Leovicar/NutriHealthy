<template>
    <div id ="arepas">
        <form @submit.prevent="AddNourritures">
            <div class="div-connexion">
                <p>Ajoutez une nourriture</p>
                <input class="texte-connexion" type="text" v-model="newNourritures.ingredient" placeholder="Entrez le nom de votre ingredient"/>
                <br/>
                <input class="texte-connexion" type="number" v-model="newNourritures.quantite" placeholder="Quel quantité en avez vous mangé ?(en grammes)"/>
                <br/>
                <input class="texte-connexion" type="number" v-model="newNourritures.calories" placeholder="Combien de calories avez vous absorber ?"/>
            </div>
            <br/>
            <div class="div-button">
                <button class="button-connexion" type="submit" href="#/suivi">Envoyer</button>
            </div>
        </form>
    </div>
</template>

<script>
module.exports = {
  props: {
      sports: {type: Array, default: []},
      nourritures: {type: Array, default: []},
  },
  data() {
      return {
          newSport:{
              activite: "",
              temps: "",
              calories: ""
          },
            newNourritures:{
                ingredient: "",
                quantite: "",
                calories: ""
            },
      };
  },
  methods: {
      AddSport(){
          this.newSport.temps=parseInt(this.newSport.temps)
          this.newSport.calories=parseInt(this.newSport.calories)
          this.$emit("add-sport", this.newSport);
      },
    AddNourritures(){
            this.newNourritures.quantite=parseInt(this.newNourritures.quantite)
          this.newNourritures.calories=parseInt(this.newNourritures.calories)
          this.$emit("add-nourritures", this.newNourritures);
      },
  },
};

</script>