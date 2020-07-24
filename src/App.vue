<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
.lights {
	width: 100px;
	height: 300px;
	border: 1px solid #000;
	div {
		width: 90px;
		height: 90px;
		border-radius: 50%;
		margin: 8px 5px;
	}
	.red-dim {
		background-color: #470505;
	}
	.green-dim {
		background-color: #0c2604;
	}
	.yellow-dim {
		background-color: #2b2905;
	}
	.red {
		background-color: #b01212;
	}
	.yellow {
		background-color: #cfad27;
	}
	.green {
		background-color: #3dba16;
	}
}
.timer {
	width: 100px;
	text-align: center;
	font-size: 20px;
}
</style>
