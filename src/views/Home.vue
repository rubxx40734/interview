<template>
  <div class="container">
    <Navbar></Navbar>
    <h1 class="text-center text-primary mt-3">山葵組面試題目</h1>
    <div class="row">
      <div class="col-4">
        <h4>computed功能:</h4>
        <ul v-for="(item, index) in product" :key="index">
          <li>
            {{ item.productname }} / {{ item.price }}
            <button
              type="button"
              class="btn btn-sm btn-success"
              @click="addcart(item)"
            >
              加入購物車
            </button>
          </li>
        </ul>
        <h4>購物車品項:</h4>
        <ul v-for="(item, index) in carts" :key="index">
          <li class="mb-0 mt-0">
            {{ item.productname }}
            <button
              type="button"
              class="btn btn-sm btn-danger"
              @click="deletecart(item, index)"
            >
              刪除
            </button>
          </li>
        </ul>
        <p>總金總金額 total: {{ total }}</p>
      </div>
      <div class="col-4">
        <p>
          搜尋功能:
          <input
            type="text"
            class="mb-3"
            placeholder="搜尋飲品"
            v-model="search"
          />
        </p>
        <ul v-for="(item, index) in filterproduct" :key="index">
          <li>{{ item.productname }} / {{ item.price }}</li>
        </ul>
      </div>
      <div class="col-4">
        <h5>製作 輸入類型 text, radio, select 、同一component切換prop來改變對應的輸入類型，並可套用v-model:</h5>
        <label>請輸入類型(text, radio, select)</label>
        <input type="text" v-model="type" class="mb-5"><br>
        <Changeinput :tempchange="type"></Changeinput>
      </div>
    </div>
  </div>
  <p>備註: Firebase Hosting 我不太會用 所以用gh-pages回覆給貴公司<br>
  設定Global參數、讓頁面的顏色、主題會隨著更換 : 這個技能我還在研究中QQ </p>
</template>

<script>
import Changeinput from '../components/Changeinput.vue'
import Navbar from '../components/Navbar.vue'
export default {
  data () {
    return {
      product: [
        {
          productname: '珍珠奶茶',
          price: 50
        },
        {
          productname: '鐵觀音抹茶',
          price: 60
        },
        {
          productname: '快可立泡沫紅茶',
          price: 30
        },
        {
          productname: '黑糖撞奶',
          price: 65
        }
      ],
      search: '',
      carts: [],
      type: ''
    }
  },
  methods: {
    addcart (item) {
      this.carts.push(item)
    },
    deletecart (item, index) {
      this.carts.splice(index, 1)
      console.log(item, index)
    }
  },
  computed: {
    total () {
      let sum = 0
      this.carts.forEach((item) => {
        sum += item.price
      })
      return sum
    },
    filterproduct () {
      return this.product.filter((item) => {
        // console.log(item)
        return item.productname.match(this.search)
      })
    }
  },
  components: { Navbar, Changeinput }
}
</script>
