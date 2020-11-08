<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <h1>NCAA Football Top 10</h1>
      </router-link>
    </div>
    <div id="side">
      <router-link to="/compare">
        <div class="menu-item browse">
          <p>Compare ({{compareSize}} Teams Selected)</p>
        </div>
      </router-link>
      <router-link to="/details">
        <div class="menu-item">
          <p>View Details (Selected: {{detailsName}})</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>

<script>
export default {
name: 'App',
computed: {
    compareSize() {
      return this.$root.$data.compareList.length;
    },
    detailsName() {
    return this.$root.$data.selected.name;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  display: flex;
  justify-content: center;
  font-size: 200%;
}

#side {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.menu-item {
  display: flex;
  width: 400px;
  background: #5e748a;
  height: 50px;
  text-align: center;
  font-size: 150%;

}

.menu-item p {
  margin: auto;
  color: black;
  font-family: impact, fantasy;
}

.browse {
  margin-right: 50px;
}

h1 {
  text-align: center;
  color: black;
  font-family: impact, fantasy;
}

@media only screen and (max-width: 800px) {
  #brand {
    font-size: 100%;
  }

  .menu-item {
    width: 100%;
    margin: 10px;
    background: black;
    height: 50px;
  }
}
</style>
