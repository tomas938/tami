<template>
	<div>
		<Navigation></Navigation>
		<Hero></Hero>
		<section class="news">
			<img
				v-if="width > 800"
				class="milk-bg"
				src="../assets/News/milk.png"
				alt="milk-background"
			/>
			<SectionDescription>
				<template v-slot:title>
					Sledujte naše
				</template>
				<template v-slot:BigTitle>
					Tami aktuality
				</template>
			</SectionDescription>
			<div class="container">
				<BigCards :data="actualityContent"></BigCards>
			</div>
			<div class="actuality">
				<ExpandButton>Všetky recepty</ExpandButton>
			</div>
		</section>
		<section class="offers">
			<SectionDescription>
				<template v-slot:title>
					školské mlieko
				</template>
				<template v-slot:BigTitle>
					Tatranskej mliekarne
				</template>
				<template v-slot:description>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex, iste
					odit! Nam consequuntur eveniet fugiat incidunt facere ea expedita
					mollitia ad laudantium magni vero porro iure perferendis ratione eum
					recusandae aliquam facilis ipsum, delectus consectetur in autem alias.
					Ab iste doloremque ullam illo voluptatibus dolorum rem sequi
					temporibus ex provident!
				</template>
			</SectionDescription>
			<div class="container">
				<OfferItems></OfferItems>
			</div>
		</section>
		<section class="catalog">
			<div class="catalog__content">
				<span>prelistujte si </span>
				<h2>Katalóg produktov</h2>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex, iste
					odit! Nam consequuntur eveniet fugiat incidunt facere ea expedita
					mollitia ad laudantium magni vero porro iure perferendis ratione eum
					recusandae aliquam facilis ipsum, delectus consectetur in autem alias.
				</p>
			</div>
			<div class="catalog__button">
				<img src="../assets/catalog-icon.png" alt="catalog-icon" />
				<p>otvoriť Katalóg</p>
				<img class="catalog-bg" src="../assets/catalog-bg2.png" alt="catalog" />
				<img class="catalog-bg2" src="../assets/catalog-bg.png" alt="catalog" />
			</div>
		</section>
		<section class="small-carousel">
			<vueper-slides
				class="no-shadow"
				:visible-slides="3"
				:slide-ratio="1 / 4"
				:gap="3"
				:fade="true"
			>
				<vueper-slide v-for="i in 9" :key="i" :title="i.toString()" />
			</vueper-slides>
			<!-- <vueper-slides
				class="no-shadow"
				:visible-slides="6"
				:arrows="false"
				:slide-ratio="1 / 4"
				:gap="3"
				:dragging-distance="70"
			>
				<vueper-slide v-for="i in 9" :key="i" :title="i.toString()" />
			</vueper-slides> -->
		</section>
		<section class="about">
			<div class="container">
				<AboutItems :aboutConent="aboutConent"></AboutItems>
			</div>
		</section>
		<section class="recipes">
			<img
				v-if="width > 800"
				class="milk-bg"
				src="../assets/News/milk.png"
				alt="milk-background"
			/>
			<SectionDescription>
				<template v-slot:title>
					vyskúšajte
				</template>
				<template v-slot:BigTitle>
					Recepty z našej kuchyne
				</template>
				<template v-slot:description>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex, iste
					odit! Nam consequuntur eveniet fugiat incidunt facere ea expedita
					mollitia ad laudantium magni vero porro iure perferendis ratione eum
					recusandae aliquam facilis ipsum, delectus consectetur in autem alias.
					Ab iste doloremque ullam illo voluptatibus dolorum rem sequi
					temporibus ex provident!
				</template>
			</SectionDescription>
			<div class="container">
				<BigCards :data="recipesContent"></BigCards>
			</div>
		</section>
		<Footer></Footer>
	</div>
</template>

<script>
import Navigation from "../components/Navigation.vue";
import Hero from "../components/Hero.vue";
import BigCards from "../components/BigCards.vue";
import ExpandButton from "../components/ExpandButton.vue";
import SectionDescription from "../components/SectionDescription.vue";
import OfferItems from "../components/OfferItems.vue";
import Footer from "../components/Footer.vue";
import AboutItems from "../components/AboutItems.vue";
// Carousel library //
import { VueperSlides, VueperSlide } from "vueperslides";
import "vueperslides/dist/vueperslides.css";
export default {
	name: "Home",
	components: {
		Hero,
		Navigation,
		BigCards,
		ExpandButton,
		SectionDescription,
		OfferItems,
		Footer,
		AboutItems,
		VueperSlides,
		VueperSlide,
	},
	data() {
		return {
			width: null,
			aboutConent: [
				{
					img: "leaf",
					characteristic: "kvalitné",
					textColor: "green",
					title: "Bio výrobky",
					description:
						"Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur quis ea accusantium laborum tempore, nulla nostrum reiciendis qui nam perspiciatis unde culpa dolore temporibus facere maiores. Nisi necessitatibus inventore vel consectetur magnam veniam incidunt non.Pariatur nemo quidem, rerum ut mollitia quas quia eligendi, quaerat molestias temporibus voluptatem, unde illo.",
				},
				{
					img: "cow",
					characteristic: "kvalitné",
					textColor: "blue",
					title: "Zariadenie",
					description:
						"Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur quis ea accusantium laborum tempore, nulla nostrum reiciendis qui nam perspiciatis unde culpa dolore temporibus facere maiores. Nisi necessitatibus inventore vel consectetur magnam veniam incidunt non.Pariatur nemo quidem, rerum ut mollitia quas quia eligendi, quaerat molestias temporibus voluptatem, unde illo.",
				},
				{
					img: "certificate",
					characteristic: "kvalitné",
					textColor: "red",
					title: "Certifikáty",
					description:
						"Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur quis ea accusantium laborum tempore, nulla nostrum reiciendis qui nam perspiciatis unde culpa dolore temporibus facere maiores. Nisi necessitatibus inventore vel consectetur magnam veniam incidunt non.Pariatur nemo quidem, rerum ut mollitia quas quia eligendi, quaerat molestias temporibus voluptatem, unde illo.",
				},
			],
			actualityContent: [
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
			recipesContent: [
				{
					img: "img-1",
					heading: "zemiakové pečivo s plesňovým syrom",
					description:
						"Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore cupiditate veniam rem ducimus obcaecati nostrum accusamus ad soluta repellendus illo!",
				},
				{
					img: "img-1",
					heading: "kuracie rezne s plesňovým syrom",
					description:
						"Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore cupiditate veniam rem ducimus obcaecati nostrum accusamus ad soluta repellendus illo!",
				},
				{
					img: "img-1",
					heading: "tortičky s plesňového syra encíán",
					description:
						"Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore cupiditate veniam rem ducimus obcaecati nostrum accusamus ad soluta repellendus illo!",
				},
			],
			// slides: [
			// 	{
			// 		title: "Slide #1",
			// 		content: "Slide content.",
			// 	},
			// 	{
			// 		title: "Slide 2",
			// 		content: "Slide content.",
			// 	},
			// ],
		};
	},
	methods: {},
	mounted() {
		this.width = window.innerWidth;
		console.log(this.width);
	},
};
</script>
<style lang="scss">
.vueperslide {
	background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
}

// documentation link.

.news {
	background-color: var(--news-bg);
	text-align: center;
	padding-bottom: 7rem;
	position: relative;
	.milk-bg {
		max-width: 250rem;
		position: absolute;
		width: 100%;
		top: 27%;
		left: 50%;
		transform: translateX(-50%);
		z-index: 1;
	}
	.actuality {
		display: flex;
		justify-content: center;
	}
}
.offers {
	text-align: center;
}

.catalog {
	display: flex;
	align-items: center;
	justify-content: center;
	gap: 17rem;
	position: relative;
	z-index: 0;
	/* ff 3.6+ */
	padding-top: 6rem;
	padding-bottom: 7rem;

	&__content {
		max-width: 80rem;
	}
	&__button {
		position: relative;
		cursor: pointer;
		width: 26rem;
		padding: 2rem 3rem;
		letter-spacing: 0.15rem;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 2rem;
		background-color: var(--danger);
		font-family: var(--myriad-pro);
		text-transform: uppercase;
		img {
			width: 2rem;
			height: 1.4rem;
		}
	}
	.catalog-bg,
	.catalog-bg2 {
		pointer-events: n;
		height: 38rem;
		width: 36rem;
		position: absolute;
		z-index: -1;
	}

	h2,
	p {
		color: white;
		max-width: 72rem;
	}
	h2 {
		padding-top: 2rem;
		padding-bottom: 3rem;
		font-size: 4.8rem;
	}

	span {
		font-weight: 800;
		color: var(--catalog-span);
		text-transform: uppercase;
	}
}
.recipes {
	position: relative;
	text-align: center;
	h2 {
		color: #fff;
	}

	p,
	.intro {
		color: var(--recipes-text-color);
	}
	.milk-bg {
		max-width: 250rem;
		position: absolute;
		width: 100%;
		left: 50%;
		transform: translateX(-50%);
		top: 33%;
		z-index: 1;
	}
}
.catalog,
.recipes {
	background: -moz-radial-gradient(
		circle at 50% 50%,
		rgb(80, 134, 255) 0%,
		rgb(14, 37, 91) 100%
	);
	/* safari 5.1+,chrome 10+ */
	background: -webkit-radial-gradient(
		circle at 50% 50%,
		rgb(80, 134, 255) 0%,
		rgb(14, 37, 91) 100%
	);
	/* opera 11.10+ */
	background: -o-radial-gradient(
		circle at 50% 50%,
		rgb(80, 134, 255) 0%,
		rgb(14, 37, 91) 100%
	);
	/* ie 10+ */
	background: -ms-radial-gradient(
		circle at 50% 50%,
		rgb(80, 134, 255) 0%,
		rgb(14, 37, 91) 100%
	);
	/* global 92%+ browsers support */
	background: radial-gradient(
		circle at 50% 50%,
		rgb(80, 134, 255) 0%,
		rgb(14, 37, 91) 100%
	);
}
.about {
	background-color: var(--news-bg);
}
</style>
