<template>
<div class="wrapper">
  <div class="teams">
    <div class="team" v-for="team in teams" :key="team.rank">
      <div class="image">
        <img :src="'/images/teams/'+team.image">
      </div>
      <div class="info">
        <h1>{{team.name}}</h1>
      </div>
      <div class="price">
        <button @click="addToCompare(team)" class="auto">Compare</button>
        <router-link to="/">
          <button @click="addToDetails(team)" class="auto">Select</button>
        </router-link>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TeamList',
  props: {
    teams: Array
  },
  methods: {
    addToCompare(team) {
        this.$root.$data.compareList.push(team);
    },
    addToDetails(team) {
      this.$root.$data.selected = team;
    }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.teams {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.team {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.team img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.team .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #5e748a;
  color: #000;
  padding: 10px 30px;
  height: 40px;
}

.info h1 {
  font-size: 20px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
  background: #5e748a;
  padding: 10px;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin: auto;
}
</style>
