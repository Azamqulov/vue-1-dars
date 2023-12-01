<template>
  <header>
    <div class="box">
      <h1>Sanoq {{ Sanoq }}</h1>
      <h2>boldi soni {{ soni }}</h2>
      <a href="#" @click="qosh">qo'sh </a>
      <a href="#" @click="ayir"> ayir</a>
    </div>
    <input type="text" :placeholder="placeholder" v-model="inputVal"><br>
    {{ inputVal }}
    <div class="btn" @click="addtask"><button>send</button></div>
    <ol v-for="task in tasks">
      <li>{{ task }} <button @click="btnDet"> delet</button></li>
    </ol>
  </header>
</template>

<script>

export default {
  data() {
    return {
      Sanoq: 0,
      soni: 0,
      placeholder: 'Email',
      inputVal: '',
      tasks: ['']

    }
  },
  methods: {
    ayir() {
      if (this.Sanoq === 0) {
        this.Sanoq = 10
        this.soni--
      } else if (this.soni === 0) {
        return
      }
      this.Sanoq--
    },
    qosh() {
      if (this.Sanoq == 10) {
        this.Sanoq = 0
        this.soni++
      }
      this.Sanoq++
    },
    addtask() {
      this.tasks.unshift(this.inputVal)
      this.inputVal = ''
    },
    btnDet() {
      
      this.tasks = ''
    }
  }
}
</script>

<style>
a {
  padding: 10px 25px;
  border: 1px solid black;
  margin: 0 10px;
  font-weight: 700;
  text-decoration: none;
}

input {
  margin: 50px 0;
  font-size: 25px;
}

.btn button {
  padding: 1px 25px;
  font-weight: 700;
  font-size: 25px;
  margin: 25px 0;
}

header {
  margin: 0 auto;
  text-align: center;
}
</style>

