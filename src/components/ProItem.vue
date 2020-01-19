<template>
	<div>
		<hr class="mb-5" color="#BDBDBD">
		<v-card
			class="d-flex my-2"
			max-height="300"
			outlined
		>
				<v-img
					max-width="200"
					height="200"
					width="200"
					src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
					>
				</v-img>
				<v-card-text>
						<p class="display-1">{{pro.title}}</p>
						<h3>{{pro.content}}</h3>
				</v-card-text>
		</v-card>
	</div>
</template>

<script>
export default {
    name : "ProItem",
    props:{
        pro : Object,
    }

}
</script>

<style>

</style>