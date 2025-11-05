<!--

@component CenteredTextOnlyHero

This component displays a centered text hero with call to action buttons.
Takes up the full viewport height and centers content vertically.
-->

<script lang="ts">
	// Components
	import AnimateText from "$lib/components/animation/AnimateText.svelte";
	import Button from "$lib/components/ui/Button.svelte";

	// Constants
	import { cta } from "$lib/navigation";

	// Types
	type Props = {
		title: string;
		subtitle: string;
		imageSrc: string;
		callsToAction?: Array<{
			href: string;
			label: string;
		}>; // A maximum of two calls to action, with the first one being primary and the second one being secondary
	};

	let {
		title,
		subtitle,
		callsToAction = [cta],
		imageSrc = "https://www.unc.mn/image-placeholder.svg",
		...rest
	}: Props = $props();
</script>

<div class="relative grid min-h-[calc(100vh-var(--nav-height))] grid-rows-[1fr_auto] overflow-hidden" {...rest}>
	<!-- Gradient background -->
	<div class="bg-background absolute inset-0 -z-20"></div>
	<div 
		class="absolute inset-0 -z-10 opacity-30"
		style="background: radial-gradient(circle at 20% 50%, var(--color-primary-600) 0%, transparent 50%), radial-gradient(circle at 80% 50%, var(--color-secondary-500) 0%, transparent 50%);"
	></div>

	<div class="relative isolate flex items-center justify-center">
		<header
			class="section-px section-py z-50 container mx-auto grid place-items-center text-center text-balance"
			data-enter-container
		>
			<div class="grid max-w-prose place-items-center justify-center gap-8 lg:max-w-[90ch] lg:gap-12">
				<h1 class="w-full text-balance text-[2.5rem] font-medium leading-[1.05] tracking-tight lg:text-[5rem] xl:text-[6rem]" data-enter>
					<span class="block bg-gradient-to-br from-foreground via-foreground to-primary bg-clip-text text-transparent">
						<AnimateText text={title} />
					</span>
				</h1>

				<p
					data-enter
					class="text-title2 block max-w-[50ch] text-pretty opacity-70 transition duration-500 ease-out lg:text-title1"
				>
					{subtitle}
				</p>
			</div>

			{#if callsToAction.length > 0}
				<div class="mt-12 flex gap-4 lg:mt-16" data-enter>
					{#each callsToAction as cta, index}
						<Button href={cta.href} size="lg" variant={index === 0 ? "primary" : "secondary"} class="max-lg:hidden"
							>{cta.label}</Button
						>
						<Button
							href={cta.href}
							size="md"
							variant={index === 0 ? "primary" : "secondary"}
							class="lg:hidden">{cta.label}</Button
						>
					{/each}
				</div>
			{/if}
		</header>
	</div>
</div>
