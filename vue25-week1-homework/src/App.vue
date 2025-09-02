<script setup>
import { ref } from 'vue'
const drinks = ref([
  { id: 1, name: '珍珠奶茶', des: '香濃奶茶搭配QQ珍珠', price: 50, count: 20 },
  {
    id: 2,
    name: '冬瓜檸檬',
    des: '清新冬瓜配上新鮮檸檬',
    price: 45,
    count: 18,
  },
  {
    id: 3,
    name: '翡翠檸檬',
    des: '綠茶與檸檬的完美結合',
    price: 55,
    count: 34,
  },
  {
    id: 4,
    name: '四季春茶',
    des: '香醇四季春茶，回甘無比',
    price: 45,
    count: 10,
  },
  {
    id: 5,
    name: '阿薩姆奶茶',
    des: '阿薩姆紅茶搭配香醇鮮奶',
    price: 50,
    count: 25,
  },
  {
    id: 6,
    name: '檸檬冰茶',
    des: '檸檬與冰茶的清新組合',
    price: 45,
    count: 20,
  },
  {
    id: 7,
    name: '芒果綠茶',
    des: '芒果與綠茶的獨特風味',
    price: 55,
    count: 18,
  },
  { id: 8, name: '抹茶拿鐵', des: '抹茶與鮮奶的絕配', price: 60, count: 20 },
])

function addCount(item) {
  item.count += 1
}
function reduceCount(item) {
  if (item.count > 0) {
    item.count -= 1
  }
}
</script>

<template>
  <div class="app">
    <table>
      <thead>
        <tr>
          <th scope="col">品項</th>
          <th scope="col">描述</th>
          <th scope="col">價格</th>
          <th scope="col">庫存</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in drinks" :key="item.id">
          <td>{{ item.name }}</td>
          <td>
            <small>{{ item.des }}</small>
          </td>
          <td>{{ item.price }}</td>
          <td class="count">
            <button v-on:click="reduceCount(item)">-</button>
            <span>{{ item.count }}</span>
            <button v-on:click="addCount(item)">+</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.count span {
  display: inline-block;
  width: 30px;
  text-align: center;
}
</style>
