<template>
  <v-container>
    <v-layout
      text-xs-center
      wrap
    >
      <v-flex xs12 text-xs-center pb-3>
            <div>
              <v-btn large color="#e13026" @click = "selectAlt(0)" :disabled = "disableWatched[0]" >{{pergDaVez.alts[0]}}</v-btn>
            </div>
            <div>
              <v-btn large color="#ff6633" @click = "selectAlt(1)" :disabled = "disableWatched[1]" >{{pergDaVez.alts[1]}}</v-btn>
            </div>
            <div>
              <v-btn large color="#dcac26" @click = "selectAlt(2)" :disabled = "disableWatched[2]" >{{pergDaVez.alts[2]}}</v-btn>
            </div>
            <div>
              <v-btn large color="#669933" @click = "selectAlt(3)" :disabled = "disableWatched[3]" >{{pergDaVez.alts[3]}}</v-btn>
            </div>

            <!-- <p>{{disableWatched}}</p> -->

      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>

export default {
  name: 'Respostas',
  props: ['pergDaVez', 'disable'],

  data() {
    return{
      disableWatched: [false,false,false,false]
    }
  },

  watch: {
    disable: function(newVal,oldVal)  {
        console.log(newVal)
        this.disableWatched = newVal
      },
  },

  methods: {
    selectAlt(alternativa) {
      this.$emit('altSelecionada', alternativa);
    }
  }
}

</script>

<style scoped>

</style>
