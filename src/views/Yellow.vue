<template>
  <div>
  	<div class='lights'>
  		<div class='red-dim'>
  		</div>
  		<div v-bind:class='actualColor'>
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
  name: 'Yellow',
  data:  () => ({
  	time: 3,
  	actualColor: 'yellow'
  }),
  mounted() {
  	setInterval(() => {
  		this.time = Math.round(this.time - 1) 
  	}, 1000)
  	if(sessionStorage.getItem('nextColor') == null) {
  		sessionStorage.setItem('nextColor', 'red')
  	}

  	setInterval(() => {
  		if(this.time <= 3) {
  			if(this.actualColor === 'yellow') {
  				this.actualColor = 'yellow-dim'
  			} else {
  				this.actualColor = 'yellow'
  			}
  		} else {
  			this.actualColor = 'yellow'
  		}
  	}, 500)

  	setTimeout(() => {
  			window.location.assign(`http://localhost:8080/${sessionStorage.getItem('nextColor')}`)
  	}, 3000)
  }
}
</script>