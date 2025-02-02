<script lang="ts">
	import * as Avatar from '$lib/components/ui/avatar/index.js';
	import Button from '$lib/components/ui/button/button.svelte';

	import * as Card from '$lib/components/ui/card/index.js';
	import * as Carousel from '$lib/components/ui/carousel/index.js';
	import { Sun, Moon } from 'radix-icons-svelte';
	import { toggleMode } from 'mode-watcher';
</script>

<div class="mx-10 my-10 flex justify-between">
	<div class="flex space-x-2">
		<Avatar.Root>
			<Avatar.Image src="" alt="@shadcn" />
			<Avatar.Fallback>OS</Avatar.Fallback>
		</Avatar.Root>
		<Button variant="ghost" size="icon" onclick={toggleMode} class="rounded-full">
			<Sun class="absolute scale-100 dark:scale-0 " />
			<Moon class="scale-0 dark:scale-100" />
		</Button>
	</div>
	<div>
		<Button variant="ghost">Home</Button>
		<Button variant="ghost">Bestellen</Button>
		<Button variant="ghost">Produkte</Button>
		<Button variant="ghost">Anmelden</Button>
	</div>
</div>

<div class="flex h-80 justify-evenly">
	<div>
		<h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">
			WILLKOMMEN BEI<br />OFFICE SNAXs<br />
		</h1>
		<h2 class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0">
			GUTEN HUNGER
		</h2>
	</div>
	<img src="/food-placeholder.png" alt="food-placeholder" class="mr-10 w-[500px]" />
</div>

<div class="mx-20 mt-20">
	<Carousel.Root opts={{ align: 'start' }} class=" w-full">
		<Carousel.Content class="p-6">
			{#each Array(5) as _, i (i)}
				<Carousel.Item class="basis-1/4">
					<Card.Root>
						<Card.Content>
							<img src="/food-placeholder.png" alt="food-img" class="" />
						</Card.Content>
					</Card.Root>
				</Carousel.Item>
			{/each}
		</Carousel.Content>
		<Carousel.Previous />
		<Carousel.Next />
	</Carousel.Root>
</div>
