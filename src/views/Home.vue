<template>
	<div>
		<Navigation></Navigation>
		<Hero></Hero>
		<section class="news">
			<img
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
				<BigCards></BigCards>
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
		<section class="small-carousel"></section>
		<section class="about"></section>
		<section class="recipes">
			<img
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
				<BigCards></BigCards>
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
	},
};
</script>
<style lang="scss">
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
</style>
