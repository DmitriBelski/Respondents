<template>
  <div>
    <h1 class="add">
      Добавить опрос
    </h1>

    <div v-for="(poll, index) in result" :key="index" class="pollcard">
      <Poll
        :number="index"
        :condition="poll.condition"
        @changeCondition="conditionChanged"
        @deleteCondition="conditionDeleted"
        @rangeToResult="rangeUpdated"
        @typesToResult="typesUpdated"
        @statusToResult="statusUpdated"
      />
      <div class="and">
        <h1>
          И
        </h1>
      </div>
    </div>

    <div class="addcondition" @click="addCondition">
      <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24">
        <path d="M0 0h24v24H0V0z" fill="none" />
        <path d="M19 13h-6v6h-2v-6H5v-2h6V5h2v6h6v2z" />
      </svg>
      <span>
        <p>Нажмите, чтобы добавить новое условие выборки.</p>
        <p>Все условия связываются между собой логическими "И"</p>
      </span>
    </div>
    <div class="test">
      Протестировать опрос
    </div>
  </div>
</template>

<script>
import Poll from '@/components/poll'
export default {
  components: { Poll },
  data () {
    return {
      result: []
    }
  },
  methods: {
    addCondition () {
      this.result.push({ condition: null, data: [] })
      this.pollCount += 1
    },
    conditionChanged (condition, index) {
      this.result[index].condition = condition
    },
    conditionDeleted (index) {
      this.result.splice(index, 1)
    },
    rangeUpdated (range, index) {
      this.result[index].data = range
    },
    typesUpdated (types, index) {
      this.result[index].data = types
    },
    statusUpdated (status, index) {
      this.result[index].data = status
    }
  }
}
</script>

<style>
.and {
  width: 40px;
  height: 35px;
  border-radius: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  left: 20px;
  bottom: -18px;
  margin-top: -36px;
}

.and h1 {
  font-weight: 200;
  font-size: 14px;
}

.pollcard:nth-child(4n) {
  background-color: #eedeaa15;
}

.pollcard:nth-child(4n+1) {
  background-color: #eeaaed15;
}

.pollcard:nth-child(4n+2) {
  background-color: #aaeee915;
}

.pollcard:nth-child(4n+3) {
  background-color: #aab1ee15;
}

.pollcard:nth-child(4n+3) .and{
  background-color: #eae1c4;
}

.pollcard:nth-child(4n) .and{
  background-color: #ecccec;
}

.pollcard:nth-child(4n+1) .and{
  background-color: #cdeae8;
}

.pollcard:nth-child(4n+2) .and{
  background-color: #d0d2e8;
}

.pollcard:nth-last-child(3) .and{
  display: none;
}

.test {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 10px 100px;
  margin: 20px;
}

.test:hover {
  box-shadow: 0 0 5px #ddd;
  cursor: pointer;
}

.add {
  color: #aaa;
  padding-bottom: 15px;
  margin-left: 20px;
}

.addcondition {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 10px 100px;
  margin: 20px;
}

.addcondition:hover {
  box-shadow: 0 0 5px #ddd;
  cursor: pointer;
}

.addcondition svg{
  flex: 0 0 25px;
  fill: seagreen;
}

.addcondition span{
  white-space: normal;
  color: seagreen;
  text-align: center;
  width: 340px;
}
</style>
