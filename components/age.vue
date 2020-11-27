<template>
  <div style="display:flex; flex-direction:column;">
    <div v-for="(blank, index) in property" :key="index" class="blank">
      <div class="title">
        <div v-if="index + 1 > 1" class="or">
          или
        </div>
        <h1>Диапазон {{ index + 1 }}</h1>
      </div>
      <div class="range">
        <div class="from">
          <span>
            От
          </span>
          <input type="text" @input="fromChanged(index, $event.target.value)">
        </div>
        <div class="to">
          <span>
            До
          </span>
          <input type="text" @input="toChanged(index, $event.target.value)">
        </div>
      </div>
    </div>
    <div class="addproperty">
      <div class="addbutton" @click="addproperty">
        <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24">
          <path d="M0 0h24v24H0V0z" fill="none" />
          <path d="M19 13h-6v6h-2v-6H5v-2h6V5h2v6h6v2z" />
        </svg>
        <span>Добавить диапазон</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      property: 1,
      result: [{ from: null, to: null }],
      changes: 0
    }
  },
  watch: {
    property () {
      this.result.push({ from: null, to: null })
    },
    changes () {
      this.$emit('changeRange', this.result)
    }
  },
  methods: {
    addproperty () {
      this.property += 1
    },
    fromChanged (index, from) {
      this.result[index].from = from
      this.changes += 1
    },
    toChanged (index, to) {
      this.result[index].to = to
      this.changes += 1
    }
  }
}
</script>

<style>
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

.range {
  flex: 0 0 auto;
  display: flex;
}

.from {
  flex: 1;
  display: flex;
  align-items: center;
  margin-right: 5px;
}

.from span{
  margin-right: 10px;
}

.to {
  flex: 1;
  display: flex;
  align-items: center;
  margin-right: 5px
}

.to span{
  margin-right: 10px;
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

.range input {
  padding-left: 10px;
  margin-right: 15px;
  height: 30px;
  color: #aaa;
  outline: none;
  border-radius: 3px;
  border: 1px solid #ddd;
  font-size: 1.4rem;
  background: white;
  font-size: 11px;
  flex: 1 0 0;
}
</style>
