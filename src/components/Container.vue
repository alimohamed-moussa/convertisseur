<template>
  <div class="conteneur">
    <div class="premier">
      <h2 class="center">Convertisseur de Minutes</h2>
      <div class="wrapper">
        <div class="conv-minutes">
          <h3 class="center">Minutes</h3>
          <input type="Number" id="minutes" v-model="minutes" class="argent" />
        </div>
        <div class="conv-centimes">
          <h3 class="center">Centimes</h3>
          <input
            type="text"
            id="centimes"
            name="centimes"
            class="argent"
            :value="calculatedCentimes"
            readonly
          />
        </div>
      </div>
    </div>
    <div class="block-conv-salaire">
      <h2 class="center">Convertisseur de Salaire</h2>
      <h3 class="center">
        SMIC au 1er Janvier 2021 - <span class="red">Métropole</span>
      </h3>
      <h4 class="center red">Coéfficient: 0.7801</h4>
      <div class="wrapper mb">
        <div class="smic">
          <label for="brut-unitaire">SMIC horaire BRUT</label>
          <input
            type="text"
            id="brut-unitaire"
            name="brutUnitaire"
            value="10.25 €"
            class="argent"
            readonly
          />
        </div>
        <div class="smic">
          <label for="net-unitaire"> SMIC horaire NET </label>
          <input
            type="text"
            id="net-unitaire"
            name="netUnitaire"
            class="argent"
            value="8.00 €"
            readonly
          />
        </div>
      </div>
      <div class="">
        <!-- Conversion de salaire Brut vers Net Metropole-->
        <h3 class="center">Conversion de salaire Brut vers Net</h3>
        <div class="wrapper mb">
          <div class="smic">
            <label for="brut"> Salaire brut </label>
            <input type="Number" id="brut" v-model="brut" class="argent" />
          </div>
          <div class="smic">
            <label for="net"> Salaire Net </label>
            <input
              type="text"
              id="net"
              name="net"
              class="argent"
              :value="calculatedNetMetropole"
              readonly
            />
          </div>
        </div>
      </div>
      <div class="class">
        <!-- Conversion de salaire Net vers Brut Metropole -->
        <h3 class="center">Conversion de salaire Net vers Brut</h3>
        <div class="wrapper mb">
          <div class="smic">
            <label for="net-conv"> Salaire Net </label>
            <input
              type="Number"
              id="net-conv"
              v-model="net_conv"
              class="argent"
            />
          </div>
          <div class="smic">
            <label for="brut-conv"> Salaire brut </label>
            <input
              type="text"
              id="brut-conv"
              name="brut_conv"
              class="argent"
              :value="calculatedBrutMetropole"
              readonly
            />
          </div>
        </div>
      </div>
    </div>
    <div class="block-conv-salaire">
      <h2 class="center">Convertisseur de Salaire</h2>
      <h3 class="center">
        SMIC au 1er Janvier 2021 - <span class="red">Alsace - Moselle</span>
      </h3>
      <h4 class="center red">Coéfficient: 0.7651</h4>
      <div class="wrapper mb">
        <div class="smic">
          <label for="brut-unitaire-al">SMIC horaire BRUT</label>
          <input
            type="text"
            id="brut-unitaire-al"
            name="brut alsace"
            class="argent"
            value="10.25 €"
            readonly
          />
        </div>
        <div class="smic">
          <label for="net-unitaire-al"> SMIC horaire NET </label>
          <input
            type="text"
            id="net-unitaire-al"
            name="net_alsace"
            class="argent"
            value="7.84 €"
            readonly
          />
        </div>
      </div>
      <div class="">
        <h3 class="center">Conversion de salaire Brut vers Net</h3>
        <div class="wrapper mb">
          <div class="smic">
            <label for="brut-unitaire-al-conv"> Salaire brut </label>
            <input
              type="Number"
              id="brut-unitaire-al-conv"
              v-model="brut_conv_al"
              class="argent"
            />
          </div>
          <div class="smic">
            <label for="net-unitaire-al-conv"> Salaire Net </label>
            <input
              type="text"
              id="net-unitaire-al-conv"
              name="net_conv_al"
              class="argent"
              :value="calculatedNetAlsace"
              readonly
            />
          </div>
        </div>
      </div>
      <div class="class">
        <h3 class="center">Conversion de salaire Net vers Brut</h3>
        <div class="wrapper mb">
          <div class="smic">
            <label for="net-al-conv-mos"> Salaire Net </label>
            <input
              type="Number"
              id="net-al-conv-mos"
              v-model="net_al_conv_mos"
              class="argent"
            />
          </div>
          <div class="smic">
            <label for="brut-al-conv-mos"> Salaire brut </label>
            <input
              type="text"
              id="brut-al-conv-mos"
              name="brut_al_conv_mos"
              class="argent"
              :value="calculatedBrutAlsace"
              readonly
            />
          </div>
        </div>
      </div>
    </div>
    <p class="center red">Copyright (c) Février 2021</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      minutes: 20,
      centimes: "",
      brut: "",
      net: "",
      net_conv: "",
      brut_conv: "",
      brut_conv_al: "",
      net_conv_al: "",
      net_al_conv_mos: "",
      brut_al_conv_mos: "",
    };
  },
  computed: {
    calculatedCentimes() {
      return (this.minutes / 60).toFixed(2) + " €";
    },
    calculatedNetMetropole() {
      return (this.brut * 0.7801).toFixed(2) + " €";
    },
    calculatedBrutMetropole() {
      return (this.net_conv / 0.7801).toFixed(2) + "€";
    },
    calculatedNetAlsace() {
      return (this.brut_conv_al * 0.7651).toFixed(2) + " €";
    },
    calculatedBrutAlsace() {
      return (this.net_al_conv_mos / 0.7651).toFixed(2) + " €";
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.conteneur {
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  margin: 2rem auto;
  max-width: 60rem;
}
.center {
  text-align: center;
}
.premier {
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  padding-bottom: 30px;
  margin: 2rem auto;
  max-width: 50rem;
}
.wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.mb {
  margin-bottom: 2rem;
}
.red {
  color: #d63031;
}
.smic {
  width: 45%;
}
.conv-minutes {
  width: 45%;
}
.argent {
  width: 100%;
  padding: 0.4rem;
}

input {
  font: inherit;
  border: 1px solid #ccc;
}
input:focus {
  outline: none;
  border-color: #6c5ce7;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
label {
  display: block;
  margin-bottom: 0.5rem;
}
.conv-centimes {
  width: 45%;
}
.block-conv-salaire {
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  padding-bottom: 30px;
  margin: 2rem auto;
  max-width: 50rem;
}
</style>
