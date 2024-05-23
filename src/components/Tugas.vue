<template>
  <div>
    <ol>
      <li v-for="(activity, index) in todoList" :key="index">{{ activity }}</li>
    </ol>
    <form @submit.prevent><input type="text" v-model="list" /><button @click="tambahkan">Tambahkan</button></form>
    <p v-if="isMoreFour">{{ isMoreFour }}</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      todoList: [],
      list: "",
    };
  },
  methods: {
    tambahkan() {
      if (this.list.trim() == "") {
        alert("Inputan harus diisi dan tidak boleh kosong ya ");
      } else {
        this.todoList.push(this.list);
        this.list = "";
      }
    },
  },
  computed: {
    isMoreFour() {
      return this.todoList.length >= 4 ? "Hebat" : "";
    },
  },
};
</script>
