<template>
  <div id="app">
    <div>
      <p v-if="showMessage">This is SIT120 task 2.1C Number 1</p>
      <p v-else>This message is shown when v-if condition is not met</p>

      <p v-show="showMessage">Darren Marchiano Sunandar</p>
    </div>

    <ul>
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>

    <div>
      <p v-for="person in people" :key="person.id">
        <template v-if="person.age >= 18">{{ person.name }} is an adult</template>
        <template v-else>{{ person.name }} is a teen</template>
      </p>
    </div>

    <div>
      <input type="text" v-model="inputText">
      <p>You typed: {{ inputText }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showMessage: true,
      items: ['Tea', 'Coffee', 'Milk'],
      people: [
        { id: 1, name: 'Michelle', age: 25 },
        { id: 2, name: 'Darren', age: 17 },
        { id: 3, name: 'Joel', age: 20 }
      ],
      inputText: ''
    };
  }
};
</script>
