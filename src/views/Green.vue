<template>
  <div>
  	<div class='lights'>
  		<div class='red-dim'>
  		</div>
  		<div class='yellow-dim'>
  		</div>
  		<div v-bind:class="actualColor">
  		</div>
  	</div>
  	<div class='timer'>
  		{{time}}
  	</div>
  </div>
</template>

<script>

export default {
  name: 'Green',
  data:  () => ({
  	time: 15,
  	actualColor: 'green'
  }),
  mounted() {
  	sessionStorage.setItem('nextColor', 'red')
  	setInterval(() => {
  		this.time = Math.round(this.time - 1)
  	}, 1000)

  	setInterval(() => {
  		if(this.time <= 3) {
  			if(this.actualColor === 'green') {
  				this.actualColor = 'green-dim'
  			} else {
  				this.actualColor = 'green'
  			}
  		} else {
  			this.actualColor = 'green'
  		}
  	}, 500)

  	setTimeout(() => {
  		window.location.assign(`http://localhost:8080/yellow`)
  	}, 15000)
  }
}
</script>