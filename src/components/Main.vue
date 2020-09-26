<template>
  <div id="main">
    <v-app>
      <h1>Подбор исполнителей</h1>
      <span>Заполните все поля для рассчёта оптимального маршрута и подбора подходящих исполнителей</span>
      <ButtonToggle />
      <Route />
      <Gabarits />
      <Checkpoints />
      <Speed />
    </v-app>
  </div>
</template>

<script>
  import ButtonToggle from './ButtonToggle'
  import Route from './Route'
  import Gabarits from './Gabarits'
  import Checkpoints from './Checkpoints'
  import Speed from './Speed'

  export default {
    components: {
      ButtonToggle,
      Route,
      Gabarits,
      Checkpoints,
      Speed
    }
  }
</script>

<style scoped>

#main {
  display: flex;
  flex-direction: column;
  width: 875px;
}
</style>