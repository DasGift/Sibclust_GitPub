<template>
  <v-container fluid>
    <span>Маршрут</span>
    <v-row align="center">
      <v-col class="d-flex" cols="12" sm="6">
        <v-select
            :items="items"
            filled
            label="Откуда забрать?"
            dense
        ></v-select>
      </v-col>
      <v-col class="d-flex" cols="12" sm="6">
        <v-select
            :items="items"
            filled
            label="Куда доставить?"
            dense
        ></v-select>
      </v-col>
    </v-row>
    <v-row align="center">
      <v-col>
        <v-radio-group v-model="fromAdresse" :mandatory="true">
          <v-radio label="Отправить из отделения" value="fromPost"></v-radio>
          <v-radio label="Забрать ко времени" value="FromTime"></v-radio>
        </v-radio-group>
        <v-row>
          <v-col>
            <v-btn-toggle
                tile
                color="#505050"
                group
                active-class="active-button"
            >
              <v-btn value="left" disabled>15.10.2020</v-btn>
              <v-btn value="center" disabled>10:30</v-btn>
              <v-btn value="center" disabled>11:00</v-btn>
            </v-btn-toggle>
          </v-col>
        </v-row>
      </v-col>
      <v-col>
        <v-radio-group v-model="toAdresse" :mandatory="true">
          <v-radio label="Доставить до отделения" value="toPost"></v-radio>
          <div style="display: flex; align-items: center">
            <v-radio label="Доставить ко времени" value="toTime"></v-radio>
            <v-tooltip v-model="show" bottom>
              <template v-slot:activator="{ on, attrs }">
                <v-btn icon v-bind="attrs" v-on="on">
                  <v-icon color="#1771E6" small style="margin-left: 5px">fas fa-ruble-sign</v-icon>
                </v-btn>
              </template>
              <span>Данная услуга предоставляется за отдельную плату</span>
            </v-tooltip>
          </div>
        </v-radio-group>
        <v-row>
          <v-col>
            <v-btn-toggle
                tile
                color="#505050"
                group
                active-class="active-button"
            >
              <v-btn value="left" disabled>20.10.2020</v-btn>
              <v-btn value="center" disabled>10:30</v-btn>
              <v-btn value="center" disabled>11:00</v-btn>
            </v-btn-toggle>
          </v-col>
        </v-row>
      </v-col>
    </v-row>

  </v-container>
</template>

<script>
export default {
  name: "Route",
  data: () => ({
    items: ['Москва', 'Казань', 'Томск', 'Владивосток'],
    fromAdresse: 'fromPost',
    toAdresse: 'toPost',
    show: false
  }),
}
</script>

<style lang="scss">
  //.v-text-field>.v-input__control>.v-input__slot:before,
  //.theme--light.v-text-field:not(.v-input--has-state):hover>.v-input__control>.v-input__slot:before,
  //.theme--light.v-text-field>.v-input__control>.v-input__slot:before {
  //  content: '';
  //  border: none;
  //}
</style>