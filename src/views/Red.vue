<template>
  <div>
  	<div class='lights'>
  		<div v-bind:class='actualColor'>
  		</div>
  		<div class='yellow-dim'>
  		</div>
  		<div class="green-dim">
  		</div>
  	</div>
  	<div class='timer'>
  		{{time}}
  	</div>
  </div>
</template>

<script>

export default {
  name: 'Red',
  data:  () => ({
  	time: 10,
  	actualColor: 'red'
  }),
  mounted() {
  	sessionStorage.setItem('nextColor', 'green')
  	setInterval(() => {
  		this.time = Math.round(this.time - 1) 
  	}, 1000)

  	setInterval(() => {
  		if(this.time <= 3) {
  			if(this.actualColor === 'red') {
  				this.actualColor = 'red-dim'
  			} else {
  				this.actualColor = 'red'
  			}
  		} else {
  			this.actualColor = 'red'
  		}
  	}, 400)

  	setTimeout(() => {
  		window.location.assign(`http://localhost:8080/yellow`)
  	}, 10000)
  }
}
</script>