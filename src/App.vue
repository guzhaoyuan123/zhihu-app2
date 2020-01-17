<template>
  <div id="app">
	  <router-view class="main"/>
  </div>
</template>

<style lang="scss">
	*{
		padding: 0;
		margin: 0;
	}
#app {
  @import url('assets/css/basic.css');
  @import url('assets/css/style.css');
}

#app {
  .main{
	  background-color: #f6f6f6;
  }
}
</style>
