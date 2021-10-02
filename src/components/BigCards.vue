<template>
	<div class="cards">
		<BigCard
			v-for="(card, index) in cards"
			:key="index"
			:heading="card.heading"
			:description="card.description"
			:img="card.img"
		>
			{{ card }}
		</BigCard>
	</div>
</template>

<script>
import BigCard from "./BigCard.vue";
export default {
	components: {
		BigCard,
	},
	data() {
		return {
			cards: [
				{
					img: "img-1",
					heading: "Intolerancia nie je prekážkou",
					description:
						"Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore cupiditate veniam rem ducimus obcaecati nostrum accusamus ad soluta repellendus illo!",
				},
				{
					img: "img-2",
					heading: "Intolerancia nie je prekážkou",
					description:
						"Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore cupiditate veniam rem ducimus obcaecati nostrum accusamus ad soluta repellendus illo!",
				},
				{
					img: "img-3",
					heading: "Intolerancia nie je prekážkou",
					description:
						"Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore cupiditate veniam rem ducimus obcaecati nostrum accusamus ad soluta repellendus illo!",
				},
			],
		};
	},
};
</script>

<style lang="scss" scoped>
.cards {
	margin-top: 6rem;
	position: relative;
	z-index: 2;
	margin-bottom: 7rem;
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	@media only screen and (max-width: 800px) {
		grid-template-columns: 1fr;
		grid-gap: 4rem;
	}
	grid-gap: 2rem;
}
</style>
