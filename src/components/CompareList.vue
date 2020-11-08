<template>
<div class="wrapper">
  <div class="compareList">
    <div class="compareTeam" v-for="(team, index) in teamList" :key="team.rank">
    <div class="itemLeft">
      <div class="image">
        <img :src="'/images/teams/'+team.image">
      </div>
      <div class="info">
        <h1>Team: {{team.name}}</h1>
        <p>{{team.location}}</p>
      </div>
    </div>
    <div class="itemRight">
      <div class="price">
        <h2>Rank:</h2>
        <h2>{{team.rank}}</h2>
        <h2>Season Record:</h2>
        <h2>{{team.record}}</h2>
      </div>
      <button @click="removeFromCompareList(index)" class="auto">Remove From List</button>
    </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CompareList',
  props: {
    teamList: Array
  },
  methods: {
    removeFromCompareList(index) {
      console.log(index);
        this.$root.$data.compareList.splice(index, 1);
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

.compareList {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  justify-content: space-around;
}

.compareTeam {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  margin: 10px;
  margin-top: 100px;
  width: 250px;
}

.itemLeft {
  display: flex;
  flex-direction: column;
  width: 200px;
}

.itemRight {
  display: flex;
  flex-direction: column;
  flex-align: space-between;
  width: 200px;
  height: 400px;
  padding: 10px;
  align-items: center;
  text-align: center;
}

.compareTeam img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.compareTeam .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #5e748a;
  color: #000;
  padding: 10px 50px;
  height: 100px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
  text-align: center;
}


.price {
  display: flex;
  flex-direction: column;
  padding-top: 10px;
  font-size: 125%;
  height: 200px;
}

.price h2 {
  padding: 0;
  margin: 0;
}

button {
  height: 50px;
  width: 150px;
  background: #000;
  color: white;
  border: none;
  margin-top: 80px;
  margin-bottom: 10px;
}

.auto {
  margin-left: auto;
}
</style>
