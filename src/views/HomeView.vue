<template>
	<main class="main">
		<section class="hero">
			<section class="hero__illustration">
				<picture>
					<source media="(min-width: 655px)" srcset="@/assets/images/image-intro-desktop.jpg">
					<img src="@/assets/images/image-intro-mobile.jpg" alt="a picture of a family holding hands while walking on the pavement">
				</picture>
			</section>
			<section class="hero__content">
				<section class="hero__content--inner">
					<h1 class="heading heading--hero">
						<span>Humanizing</span> <span>your insurance.</span>
					</h1>
					<p class="text text--hero">
						Get your life insurance coverage easier and faster. We blend our
						expertise and technology to help you find the plan that’s right for
						you. Ensure you and your loved ones are protected.
					</p>
					<router-link :to="{ name: '' }" class="cta">View plans</router-link>
				</section>
			</section>
		</section>
		<section class="about grid">
			<section class="about--inner">
				<h1 class="heading heading--about">We’re different</h1>
				<section class="card__container">
					<section class="card">
						<img
							src="@/assets/images/icon-snappy-process.svg"
							alt="Snappy process icon"
						/>
						<h1 class="heading">Snappy Process</h1>
						<p class="text">
							Our application process can be completed in minutes, not hours.
							Don’t get stuck filling in tedious forms.
						</p>
					</section>
					<section class="card">
						<img
							src="@/assets/images/icon-affordable-prices.svg"
							alt="Affordable Prices icon"
						/>
						<h1 class="heading">Affordable Prices</h1>
						<p class="text">
							We don’t want you worrying about high monthly costs. Our prices
							may be low, but we still offer the best coverage possible.
						</p>
					</section>
					<section class="card">
						<img src="@/assets/images/icon-people-first.svg" alt="People first icon" />
						<h1 class="heading">People First</h1>
						<p class="text">
							Our plans aren’t full of conditions and clauses to prevent
							payouts. We make sure you’re covered when you need it.
						</p>
					</section>
				</section>
				<section class="moreInfo">
					<h1 class="heading">Find out more <span>about how we work</span></h1>
					<router-link :to="{name: ''}" class="cta">How we work</router-link>
				</section>
			</section>
		</section>
	</main>
	<app-footer />
</template>

<script>
import AppFooter from '../components/AppFooter.vue';
export default {
  name: "HomeView",
  components: {
    AppFooter
  }
}
</script>
