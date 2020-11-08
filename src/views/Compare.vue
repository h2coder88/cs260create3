<template>
<div>
  <div v-if='this.$root.$data.compareList.length > 0' class="wrapper">
  </div>
  <div v-else class="emptyCart">
    <h1>No Teams Selected!</h1>
  </div>
  <CompareList :teamList="teams" />
</div>
</template>

<script>
import CompareList from "../components/CompareList.vue"
export default {
  name: 'Compare',
  components: {
    CompareList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    teams() {
      return this.$root.$data.compareList.filter(team => team.name.toLowerCase().search(this.searchText) >= 0);
    }
  },
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}

.emptyCart {
  width: 100%;
  font-size: 150%;
  text-align: center;
  color: orange;
  margin-top: 100px;
}
</style>
