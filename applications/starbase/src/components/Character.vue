<template>
	<div class="col-md-3" @click="switchCharacter">
		<div class="character-card">
			<div class="card-block">
				<h4 class="card-title">{{character.name}}</h4>
				<div class="card-text">Height {{character.height}} cm</div>
				<div class="card-text">Mass {{character.mass}} kg</div>
				<div class="card-text">Hair color {{character.hair_color}}</div>
				<div class="card-text">Eye color {{character.eye_color}}</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'app',
		props: ['id'],
		data(){
			return {
				character: {}
			}
		},
		methods: {
			fetchCharacter(id){
				fetch(`https://swapi.co/api/people/${id}/`,{
					method:'GET'
				})
				.then(response => response.json())
				.then(json=>this.character = json)
			},
			switchCharacter(){
				let random_id = Math.floor(Math.random()*83)+1
				this.fetchCharacter(random_id)
				console.log(random_id)
			}
		},
		created(){
			this.fetchCharacter(this.id)
		}
	}
</script>