<script>
	import { gsap } from "gsap";
	import { onMount } from "svelte";

	onMount(() => {
		gsap.from(".card", { opacity: 0, y: 100, ease: "power1.out", duration: 1 })
		gsap.from(".card__summary", { opacity: 0, y: -25, ease: "power1.out", stagger: 0.6, duration: 1 })
		gsap.from(".card__illustration-img", { opacity: 0, scale: 0, ease: "power2.out", duration: .5 })
	})
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Red+Hat+Display:wght@500;700;900&display=swap');

	:root {
		--pale-blue: hsl(225, 100%, 94%);
		--bright-blue: rgb(56, 41, 224);
		--very-pale-blue: rgb(245, 247, 255);
		--desaturated-blue: rgb(114, 128, 167);
		--dark-blue: rgb(70, 76, 89);
		--desaturated-pale-blue: rgb(246, 247, 254);
		--vd-blue: rgb(25, 46, 87);
		--desaturated-bright-blue: rgb(117, 106, 241);
	}

	.card {
		background-color: #fff;
		box-shadow: 0 15px 15px rgba(114, 128, 167, .2);
		border-radius: 2rem;
		display: flex;
		flex-direction: column;
		max-width: 400px;
	}
	
	.card__illustration-img {
		width: 100%;
		border-top-left-radius: 2rem;
		border-top-right-radius: 2rem;
	}

	.card__summary {
		padding: 2.5rem;
		text-align: center;
	}

	.card__summary-headline {
		margin-bottom: 2rem;
		color: var(--vd-blue);
		font-size: 1.8rem;
		font-weight: 900;
	}

	.card__summary-subheadline {
		color: var(--desaturated-blue);
		line-height: 2.5rem;
	}

	.card__summary-btns {
		display: flex;
		flex-direction: column;
	}

	.card__pricing {
		display: flex;
		background-color: var(--desaturated-pale-blue);
		justify-content: space-between;
		align-items: center;
		margin: 2.5rem 0;
		padding: 1.5rem;
		border-radius: 1rem;
	}

	.card__pricing-btn {
		border: none;
		background-color: transparent;
		color: var(--bright-blue);
		font-weight: 700;
		text-decoration: underline;
	}

	.card__pricing-btn:hover {
		color: var(--desaturated-bright-blue);
		text-decoration: none;
	}

	.card__pricing-plan {
		display: flex;
		flex-direction: column;
		text-align: left;
	}

	.card__pricing-plan-time {
		font-weight: 900;
		font-size: 1.5rem;
		color: var(--vd-blue);
	}

	.card__pricing-plan-amount {
		color: var(--desaturated-bright-blue);
		font-size: 1.4rem;
	}

	.card__summary-proceed {
		background-color: var(--bright-blue);
		border: none;
		color: #fff;
		padding: 1.5rem;
		border-radius: 1rem;
		box-shadow: 0 15px 15px rgba(56, 41, 224, .2);
		margin-bottom: 2.5rem;
		font-weight: 700;
	}

	.card__summary-proceed:hover {
		background-color: var(--desaturated-bright-blue);
	}

	.card__summary-cancel {
		background-color: transparent;
		border: none;
		color: var(--desaturated-blue);
		font-weight: 900;
	}

	.card__summary-cancel:hover {
		color: var(--dark-blue);
	}
</style>

<main>
	<div class="card">
		<div class="card__illustration">
			<img src="./images/illustration-hero.svg" alt="Person Listening To Song Illustration" class="card__illustration-img">
		</div>
		<div class="card__summary">
			<h1 class="card__summary-headline">Order Summary</h1>
			<p class="card__summary-subheadline">You can now listen to millions of songs, audiobooks, and podcasts on any device anywhere you like!</p>
			<div class="card__pricing">
				<img src="./images/icon-music.svg" alt="Music Note Icon" class="card__pricing-icon">
				<div class="card__pricing-plan">
					<span class="card__pricing-plan-time">Annual Plan</span>
					<span class="card__pricing-plan-amount">$59.99/year</span>
				</div>
				<button class="card__pricing-btn">Change</button>
			</div>
			<div class="card__summary-btns">
				<button class="card__summary-proceed">Proceed To Payment</button>
				<button class="card__summary-cancel">Cancel Order</button>
			</div>
		</div>
	</div>
</main>
