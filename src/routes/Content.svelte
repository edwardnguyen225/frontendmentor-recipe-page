<script>
	const preparations = [
		{ name: 'Total', value: 'Approximately 10 minutes' },
		{ name: 'Preparation', value: '5 minutes' },
		{ name: 'Cooking', value: '5 minutes' }
	];

	const ingredients = [
		'2-3 large eggs',
		'Salt, to taste',
		'Pepper, to taste',
		'1 tablespoon of butter or oil',
		'Optional fillings: cheese, diced vegetables, cooked meats, herbs'
	];

	const instructions = [
		{
			stepName: 'Beat the eggs',
			stepDescription:
				'In a bowl, beat the eggs with a pinch of salt and pepper until they are well mixed. You can add a tablespoon of water or milk for a fluffier texture.'
		},
		{
			stepName: 'Heat the pan',
			stepDescription: 'Place a non-stick frying pan over medium heat and add butter or oil'
		},
		{
			stepName: 'Cook the omelette',
			stepDescription:
				'Once the butter is melted and bubbling, pour in the eggs. Tilt the pan to ensure the eggs evenly coat the surface.'
		},
		{
			stepName: 'Add fillings (optional)',
			stepDescription:
				'When the eggs begin to set at the edges but are still slightly runny in the middle, sprinkle your chosen fillings over one half of the omelette.'
		},
		{
			stepName: 'Fold and serve',
			stepDescription:
				'As the omelette continues to cook, carefully lift one edge and fold it over the fillings. Let it cook for another minute, then slide it onto a plate.'
		},
		{
			stepName: 'Enjoy',
			stepDescription: 'Serve hot, with additional salt and pepper if needed.'
		}
	];

	const nutritions = [
		{ name: 'Calories', value: '277kcal' },
		{ name: 'Carbs', value: '0g' },
		{ name: 'Protein', value: '20g' },
		{ name: 'Fat', value: '22g' }
	];
</script>

<div class="content-container">
	<img src="images/image-omelette.jpeg" alt="Omlette" />

	<div class="content">
		<div class="section">
			<h1 class="header heading-large">Simple Omelette Recipe</h1>
			<p>
				An easy and quick dish, perfect for any meal. This classic omelette combines beaten eggs
				cooked to perfection, optionally filled with your choice of cheese, vegetables, or meats.
			</p>
		</div>

		<div class="section section-preparation">
			<h2 class="heading-small">Preparation time</h2>
			<ul>
				{#each preparations as preparation}
					<li>
						<p>
							<span class="bold">{preparation.name}:</span>
							{preparation.value}
						</p>
					</li>
				{/each}
			</ul>
		</div>

		<div class="section">
			<h2 class="heading-medium">Ingredients</h2>
			<ul>
				{#each ingredients as ingredients}
					<li>{ingredients}</li>
				{/each}
			</ul>
		</div>

		<div class="divider"></div>

		<div class="section">
			<h2 class="heading-medium">Instructions</h2>
			<ol>
				{#each instructions as { stepName, stepDescription }, i}
					<li>
						<p>
							<span class="bold">{stepName}:</span>
							{stepDescription}
						</p>
					</li>
				{/each}
			</ol>
		</div>

		<div class="divider"></div>

		<div class="section">
			<h2 class="heading-medium">Nutrition</h2>
			<p>The table below shows nutritional values per serving without the additional fillings.</p>
			<div class="nutrition-list">
				{#each nutritions as { name, value }, i}
					<div class="nutrition-item">
						<div class="nutrition-item--left">{name}</div>
						<div class="nutrition-item--right">
							{value}
						</div>
					</div>
					{#if i !== nutritions.length - 1}
						<div class="divider"></div>
					{/if}
				{/each}
			</div>
		</div>
	</div>
</div>

<style>
	.content-container {
		width: 100%;
		max-width: 736px;
		display: flex;
		flex-direction: column;
		background-color: var(--white);
		transition: all 0.2s ease-in-out;
	}

	img {
		transition: all 0.2s ease-in-out;
	}

	@media only screen and (min-width: 455px) {
		.content-container {
			padding: 40px;
			border-radius: 24px;
		}

		img {
			border-radius: 12px;
		}
	}

	.content {
		padding: 40px 32px;
		display: flex;
		flex-direction: column;
		gap: 32px;
	}

	.section {
		display: flex;
		flex-direction: column;
		gap: 24px;
	}

	.section.section-preparation {
		padding: 24px;
		gap: 16px;
		background-color: var(--rose-white);
		border-radius: 12px;
	}

	.heading-large,
	.heading-medium {
		font-family: 'Young Serif', serif;
		line-height: 100%;
		letter-spacing: 0;
	}

	.heading-large {
		font-size: 2.5rem;
		color: var(--dark-charcoal);
	}

	.heading-medium {
		font-size: 1.75rem;
		color: var(--nutmeg);
	}

	.heading-small {
		font-family: 'Outfit', Arial, Helvetica, sans-serif;
		font-size: 1.25rem;
		font-weight: semibold;
		line-height: 100%;
		letter-spacing: 0;
		color: var(--dark-raspberry);
	}

	.bold {
		font-weight: bold;
	}

	ul,
	ol {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		list-style-position: inside;
	}

	ul > li {
		padding-left: 0.5rem;
		display: flex;
		align-items: center;
		gap: 1rem;
	}

	ul > li::before {
		content: '';
		flex: 0 0 auto;
		width: 4px;
		height: 4px;
		border-radius: 50%;
		background-color: var(--dark-raspberry);
	}

	ol > li {
		padding-left: 0.5rem;
		display: flex;
		gap: 1rem;
	}

	ol > li::before {
		content: counter(list-item) '.';
		counter-increment: list-item;
		font-weight: bold;
		color: var(--nutmeg);
	}

	.divider {
		height: 1px;
		background-color: var(--light-grey);
	}

	.nutrition-list {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.nutrition-item {
		padding: 0 16px;
		display: flex;
		justify-content: space-between;
		gap: 16px;
	}

	.nutrition-item--left,
	.nutrition-item--right {
		flex: 1;
	}

	.nutrition-item--right {
		font-weight: bold;
		color: var(--nutmeg);
	}
</style>
