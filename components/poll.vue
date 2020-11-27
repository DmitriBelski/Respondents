<template>
  <div class="card">
    <div class="header">
      <h1>Условие {{ number + 1 }}</h1>
      <div class="select">
        <select v-model="currentTab" class="select__body">
          <option value="" disabled selected>
            Выберите условие
          </option>
          <option v-for="(item, index) in options" :key="index">
            {{ item.value }}
          </option>
        </select>
      </div>
    </div>

    <div class="condition">
      <div class="component">
        <component
          :is="currentTabComponent"
          @changeRange="rangeChanged"
          @changeCardType="cardTypeChange"
          @changeCardStatus="cardStatusChange"
        />
      </div>
      <div class="delete" @click="deleteCondition">
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24">
          <path d="M0 0h24v24H0V0z" fill="none" />
          <path d="M14.12 10.47L12 12.59l-2.13-2.12-1.41 1.41L10.59 14l-2.12 2.12 1.41 1.41L12 15.41l2.12 2.12 1.41-1.41L13.41 14l2.12-2.12zM15.5 4l-1-1h-5l-1 1H5v2h14V4zM6 19c0 1.1.9 2 2 2h8c1.1 0 2-.9 2-2V7H6v12zM8 9h8v10H8V9z" />
        </svg>
        <span>Удалить условие</span>
      </div>
    </div>
  </div>
</template>

<script>
import Age from '@/components/age'
import CardType from '@/components/cardType'
import CardStatus from '@/components/cardStatus'
export default {
  components: { Age, CardType, CardStatus },
  props: {
    number: {
      type: Number,
      default: 0
    },
    condition: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      options: [{
        value: 'Возраст респондента',
        label: 'age'
      }, {
        value: 'Тип карты лояльности',
        label: 'cardType'
      }, {
        value: 'Статус карты лояльности',
        label: 'cardStatus'
      }],
      currentTab: ''
    }
  },
  computed: {
    currentTabComponent () {
      if (this.currentTab !== '') {
        const str = this.labelFromValue(this.currentTab)
        return str[0].toUpperCase() + str.slice(1)
      } else {
        return null
      }
    }
  },
  watch: {
    currentTabComponent () {
      this.$emit('changeCondition', this.currentTabComponent, this.number)
    },
    condition () {
      this.currentTab = this.valueFromLabel(this.condition)
    }
  },
  methods: {
    deleteCondition () {
      this.$emit('deleteCondition', this.number)
    },
    valueFromLabel (label) {
      if (label === null) {
        return ''
      } else {
        return this.options[this.options.findIndex(tab => tab.label === label[0].toLowerCase() + label.slice(1))].value
      }
    },
    labelFromValue (value) {
      return this.options[this.options.findIndex(tab => tab.value === value)].label
    },
    rangeChanged (range) {
      this.$emit('rangeToResult', range, this.number)
    },
    cardTypeChange (types) {
      this.$emit('typesToResult', types, this.number)
    },
    cardStatusChange (status) {
      this.$emit('statusToResult', status, this.number)
    }
  }
}
</script>

<style>
.card {
  display: flex;
  flex-direction: column;
  padding: 0 20px 20px 20px;
  border-bottom: 1px solid #ddd;
}

.header {
  display: flex;
  align-items: center;
  margin: 20px 0;
}

.header h1 {
  flex: 0 0 250px;
}

.condition {
  display: flex;
  align-items: flex-end;
}

.component {
  flex: 1 0 0%;
  margin-right: 15px;
  display: flex;
  flex-direction: column;
}

.delete {
  flex: 0 0 auto;
  display: flex;
  align-items: center;
  border: 1px solid tomato;
  border-radius: 3px;
  padding: 5px;
}

.delete:hover {
  box-shadow: 0 0 5px tomato;
  cursor: pointer;
}

.delete svg {
  flex: 0 0 25px;
  margin-right: 5px;
  fill: tomato;
}

.delete span {
  flex: 1 0 0%;
  white-space: nowrap;
  margin-right: 8px;
  color:tomato;
}

.select {
  flex: 1 0 0%;
  width: 400px;
  margin: 0 auto;
}
.select__body {
  display: block;
  font-size: 16px;
  font-family: sans-serif;
  font-weight: 700;
  color: #444;
  line-height: 1.3;
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
