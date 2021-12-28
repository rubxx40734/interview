<template>
  <div class="container">
    <Navbar></Navbar>
    <h1 class="text-center mb-3">串接一組列表資料api</h1>
    <div class="content text-center">
      <button class="btn btn-primary text-center" @click="getdata">
        按我測試
      </button>
    </div>
    <Datamodal ref="datamodal" :data="fakedata"></Datamodal>
  </div>
</template>

<script>
import Datamodal from '../components/Datamodal.vue'
import Navbar from '../components/Navbar.vue'
export default {
  data () {
    return {
      fakedata: [],
      modal: {}
    }
  },
  components: { Navbar, Datamodal },
  methods: {
    getdata () {
      this.axios
        .get('https://mocki.io/v1/d4867d8b-b5d5-4a48-a4ab-79131b5809b8')
        .then((res) => {
          console.log(res)
          this.fakedata = res.data
          this.$refs.datamodal.showmodal()
        })
        .catch((err) => {
          console.log(err)
        })
    }
  },
  mounted () {
  },
  created () {
    // this.getdata()
  }
}
</script>
