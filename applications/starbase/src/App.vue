<template>
<div id="app">
	<h3>{{title}}</h3>
	<div class="col-md-12">
		<Character 
		v-for="(id,index) in initial_ids"
		:id="id"
		:key="index"
		>	
		</Character>
	</div>
</div>
</template>

<script>
import Character from './components/Character.vue'
export default {
	name: 'app',
	data(){
		return {
			title: 'Generate your team',
			initial_ids: ['2','5','8']
		}
	},
	components: {
		Character
	}
}
</script>