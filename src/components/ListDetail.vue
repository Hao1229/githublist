<template>
    <div class="mt-4">
        <table class="table">
            <thead class="thead-light">
                <tr>
                    <th>專案標題</th>
                    <th>專案敘述</th>
                    <th>專案連結</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in nowPage" :key="item.name">
                    <td width="250" class="text-success">{{item.name}}</td>
                    <td>{{item.description}}</td>
                    <td width="130"><a :href="item.html_url" target="_blank">Github 連結</a></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
  data () {
    return {
      list: [],
      nowPage: []
    }
  },
  methods: {
    getData () {
      const vm = this
      const api = `https://api.github.com/users/${process.env.VUE_APP_API_PATH}/repos`
      this.$http.get(api).then((response) => {
        vm.list = response.data
        vm.nowPage = vm.list.filter((item) => {
          return vm.list.indexOf(item) < 4
        })
      })
    },
    scrollShow () {
      const vm = this
      let scrollPos = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
      let InfiniteElm = document.querySelector('.table')
      let clientHeight = InfiniteElm.clientHeight
      if (scrollPos > clientHeight / 4) {
        vm.list.forEach((item, index) => {
          if (index < vm.nowPage.length + 4 && vm.nowPage.indexOf(item) < 0) {
            vm.nowPage.push(item)
          }
        })
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.scrollShow)
  },
  created () {
    this.getData()
  }
}
</script>
