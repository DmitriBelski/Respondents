<template>
  <div style="display:flex; flex-direction:column;">
    <div v-for="(blank, index) in property" :key="index" class="blank">
      <div class="title">
        <div v-if="index + 1 > 1" class="or">
          или
        </div>
        <h1>Статус {{ index + 1 }}</h1>
      </div>
      <div class="type">
        <div class="select">
          <select class="select__body" @change="statusChanged(index, $event.target.value)">
            <option value="" disabled selected>
              Выберите статус карты
            </option>
            <option v-for="(item, Oindex) in options" :key="Oindex">
              {{ item }}
            </option>
          </select>
        </div>
      </div>
    </div>
    <div class="addproperty">
      <div class="addbutton" @click="addproperty">
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24">
          <path d="M0 0h24v24H0V0z" fill="none" />
          <path d="M19 13h-6v6h-2v-6H5v-2h6V5h2v6h6v2z" />
        </svg>
        <span>Добавить статус</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      options: ['Активна', 'Заблокирована'],
      property: 1,
      result: [],
      changes: 0
    }
  },
  watch: {
    changes () {
      this.$emit('changeCardStatus', this.result)
    }
  },
  methods: {
    addproperty () {
      this.property += 1
    },
    statusChanged (index, card) {
      this.result[index] = card
      this.changes += 1
    }
  }
}
</script>

<style scoped>
.blank {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
}

.blank h1{
  flex: 0 0 250px;
  font-size: 15px;
}

.title {
  flex: 0 0 250px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.or {
  border-radius: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  margin-left: 20px;
  font-weight: 200;
  font-size: 14px;
}

.type {
  flex: 0 0 auto;
  display: flex;
}

.addproperty{
  display: flex;
}

.addbutton {
  flex: 0 0 100px;
  display: flex;
  align-items: center;
  border: 1px solid  #92D050;
  border-radius: 3px;
  padding: 5px;
  margin: 20px 0 0 250px;
}

.addbutton:hover {
  box-shadow: 0 0 5px #92D050;
  cursor: pointer;
}

.addbutton svg {
  flex: 0 0 25px;
  margin-right: 5px;
  fill:  #92D050;
}

.addbutton span {
  flex: 1 0 0%;
  white-space: nowrap;
  margin-right: 8px;
  color: #92D050;
}

.select {
  flex: 1 0 0%;
  width: 400px;
  margin: 0 auto;
}
.select__body {
  display: block;
  font-size: 14px;
  font-family: sans-serif;
  font-weight: 600;
  color: #444;
  line-height: 1.2;
  padding: .6em 1.4em .5em .8em; width: 100%;
  max-width: 100%;
  box-sizing: border-box;
  border: 1px solid #aaa;
  box-shadow: 0 1px 0 1px rgba(0,0,0,.04);
  border-radius: .5em;
  -moz-appearance: none;
  -webkit-appearance: none;
  appearance: none;
  background-color: #fff;
  background-repeat: no-repeat, repeat;
  background-position: right .7em top 50%, 0 0;
  background-size: .65em auto, 100%;
}
.select__body::-ms-expand { display: none; }
.select__body:hover { border-color: #888; }
.select__body:focus { border-color: #aaa;
  box-shadow: 0 0 1px 3px rgba(59, 153, 252, .7);
  box-shadow: 0 0 0 3px -moz-mac-focusring;
  color: #222;
  outline: none;
}
.select__body option {
  font-weight: normal;
}
</style>
