<template>
<div class="wrapper">
  <div class="teamInfo">
    <div class="teamName">
      <div class="name">
        <h1>{{this.$root.$data.selected.name}}</h1>
      </div>
      <div class="location">
        <p>{{this.$root.$data.selected.location}}</p>
      </div>
      <div class="teamLogo">
        <img :src="'/images/teams/'+this.$root.$data.selected.image">
      </div>
    </div>
    <div class="additionalInfo">
      <div class="rank">
        <p>Rank:</p>
        <h1>{{this.$root.$data.selected.rank}}</h1>
      </div>
      <div class="record">
        <p>Record:</p>
        <h1>{{this.$root.$data.selected.record}}</h1>
      </div>
    </div>
  </div>
</div>
</template>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.name {
  width: 100%;
  font-size: 200%;
  text-align: center;
  margin-bottom: 0;
}

.location {
  width: 100%;
  margin: 0;
  padding: 0;
  text-align: center;
}

.teamInfo {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.teamLogo {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  margin: 10px;
  margin-top: 100px;
  width: 250px;
}

.teamLogo img {
  height: 400px;
  width: 400px;
  object-fit: cover;
}

.teamName {
  display: flex;
  flex-direction: column;
  width: 400px;
  align-items: center;
}

.additionalInfo {
  display: flex;
  flex-align: space-between;
  width: 100%;
  padding: 10px;
  align-items: center;
  text-align: center;
}

.rank {
  height: 200px;
  width: 200px;
  border: 2px solid;
  margin: 10px;
  font-size: 150%;
  background: #5e748a;
  margin-top: 20px;
}

.record {
  height: 200px;
  width: 200px;
  border: 2px solid;
  margin: 10px;
  font-size: 150%;
  background: #5e748a;
  margin-top: 20px;
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
