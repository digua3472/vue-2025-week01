<script setup>
import { ref } from 'vue';

const datas = ref([
  {
    id: 1,
    name: '珍珠奶茶',
    discription: '香濃奶茶搭配QQ珍珠',
    price: 50,
    stock: 20
  },
  {
    id: 2,
    name: '冬瓜檸檬',
    discription: '清新冬瓜配上新鮮檸檬',
    price: 45,
    stock: 18
  },
  {
    id: 3,
    name: '翡翠檸檬',
    discription: '綠茶與檸檬的完美結合',
    price: 55,
    stock: 34
  },
  {
    id: 4,
    name: '四季春茶',
    discription: '香醇四季春茶，回甘無比',
    price: 45,
    stock: 10
  },
  {
    id: 5,
    name: '阿薩姆奶茶',
    discription: '阿薩姆紅茶搭配香醇鮮奶',
    price: 50,
    stock: 25
  },
  {
    id: 6,
    name: '檸檬冰茶',
    discription: '檸檬與冰茶的清新組合',
    price: 45,
    stock: 20
  },
  {
    id: 7,
    name: '芒果綠茶',
    discription: '芒果與綠茶的獨特風味',
    price: 55,
    stock: 18
  },
  {
    id: 8,
    name: '抹茶拿鐵',
    discription: '抹茶與鮮奶的絕配',
    price: 60,
    stock: 20
  }
]);

function decrease(item) {
  if(item.stock > 0) {
    item.stock --;
  }
}

function increase(item) {
  item.stock ++;
}

</script>

<template>
  <thead>
    <tr>
      <th scope="col">品項</th>
      <th scope="col">描述</th>
      <th scope="col">價格</th>
      <th scope="col">庫存</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item in datas" :key="item.id">
      <td>{{ item.name }}</td>
      <td><small>{{ item.discription }}</small></td>
      <td>{{ item.price }}</td>
      <td>
        <button type="button" v-on:click="decrease(item)">-</button>
        {{ item.stock }}
        <button type="button" v-on:click="increase(item)">+</button></td>
    </tr>
    
  </tbody>
</template>

<style scoped></style>
