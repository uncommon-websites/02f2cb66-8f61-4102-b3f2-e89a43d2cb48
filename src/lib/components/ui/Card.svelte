<script lang="ts">
	import type { Component } from "svelte";

	interface Props {
		title?: string;
		description?: string;
		icon?: Component;
		iconClass?: string;
		imageSrc?: string;
		imageAspect?: "16/9" | "9/16";
		class?: string;
	}

	let {
		title = "",
		description = "",
		icon,
		iconClass = "size-5 text-primary",
		imageSrc,
		imageAspect = "16/9",
		class: customClass = ""
	}: Props = $props();
</script>

<article
	class="group relative flex flex-col overflow-hidden rounded-(--radius-lg) border border-border/50 bg-card/40 p-6 text-pretty backdrop-blur-sm transition-all duration-500 ease-out hover:border-primary/30 hover:bg-card/60 lg:p-8 {customClass}"
>
	{#if icon || imageSrc}
		<div class="mb-6 lg:mb-8">
			{#if icon && imageSrc}
				{@const Icon = icon}
				<div class="relative">
					<img
						src={imageSrc}
						alt={title}
						class="w-full object-cover {imageAspect === '9/16' ? 'aspect-[9/16]' : 'aspect-[16/9]'}"
						style="border-radius: max(2px, calc(var(--radius) - 1rem));"
					/>
					<div
						class="absolute top-3 left-3 bg-primary/10 p-2 backdrop-blur-md"
						style="border-radius: max(2px, calc(var(--radius) - 1.25rem));"
					>
						<Icon class="size-5 text-primary" />
					</div>
				</div>
			{:else if icon}
				{@const Icon = icon}
				<div class="inline-flex rounded-(--radius) bg-primary/10 p-3 backdrop-blur-sm">
					<Icon class="size-6 text-primary transition-transform duration-300 group-hover:scale-110" />
				</div>
			{:else if imageSrc}
				<img
					src={imageSrc}
					alt={title}
					class="w-full object-cover {imageAspect === '9/16' ? 'aspect-[9/16]' : 'aspect-[16/9]'}"
					style="border-radius: max(2px, calc(var(--radius) - 1rem));"
				/>
			{/if}
		</div>
	{/if}

	<div class:mt-auto={icon || imageSrc}>
		<h3 class="text-title3 mb-3 transition-colors duration-300 group-hover:text-primary">
			{title}
		</h3>
		<p class="text-callout max-w-prose opacity-70">{description}</p>
	</div>
</article>
