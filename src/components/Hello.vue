<template>
  <div id="hello">
    <md-toolbar>
      <h1 class="md-title">Como você quer seu Software?</h1>
    </md-toolbar>

    <div class="content">
      <div class="form-group rapido">
        <md-switch md-theme="orange" id="rapido" v-model="rapido">Rápido</md-switch>
      </div>
      <div class="form-group qualidade">
        <md-switch md-theme="green" id="qualidade" v-model="qualidade" class="md-primary">Qualidade</md-switch>
      </div>
      <div class="form-group barato">
        <md-switch md-theme="yellow" id="barato" v-model="barato" class="md-primary">Barato</md-switch>
      </div>

    </div>

  </div>
</template>

<script>
  export default {
    name: 'hello',
    data() {
      return {
        rapido: false,
        qualidade: true,
        barato: false,
      };
    },
    watch: {
      rapido(newVal) {
        if (newVal === true) {
          this.qualidade = false;
          this.barato = false;
        } else {
          // this.barato = true;
          // this.qualidade = true;
        }
      },
      qualidade(newVal) {
        if (newVal === true) {
          this.rapido = false;
          this.barato = false;
        } else {
          // this.barato = true;
          // this.rapido = true;
        }
      },
      barato(newVal) {
        if (newVal === true) {
          this.qualidade = false;
          this.rapido = false;
        } else {
          // this.barato = true;
          // this.qualidade = true;
        }
      },
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .form-group {
    zoom: 3;
    text-align: center;
  }
  .rapido .md-checked .md-switch-container{
    background-color: rgba(208, 0, 0, 0.87);
  }
  .qualidade .md-checked .md-switch-container{
    background-color: rgba(0, 208, 83, 0.87);
  }
  .barato .md-checked .md-switch-container{
    background-color: rgba(0, 0, 0, 0.87);
  }
</style>
