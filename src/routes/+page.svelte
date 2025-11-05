<script lang="ts">
	// Components
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CenteredTextOnlyHero from "$lib/components/layout/hero-sections/CenteredTextOnlyHero.svelte";

	// Icons
	import IconRadar from "~icons/lucide/radar";
	import IconTrendingUp from "~icons/lucide/trending-up";
	import IconHeart from "~icons/lucide/heart";
	import IconBell from "~icons/lucide/bell";
	import IconNetwork from "~icons/lucide/network";
	import IconGauge from "~icons/lucide/gauge";
</script>

<CenteredTextOnlyHero
	title="The system of work for venture capital"
	subtitle="Tend to your portfolio like a gardener tends their garden. Monitor companies continuously, surface follow-on opportunities, and ensure no exceptional founder goes without the attention they need to thrive."
	imageSrc="/generated/image-a-mid-career-venture-capital-partner-in-.webp"
/>
<LogoScroller 
	label="Trusted by leading venture firms"
	logoUrls={[
		'https://cdn.brandfetch.io/sequoiacap.com/w/400/h/400/logo',
		'https://cdn.brandfetch.io/a16z.com/w/400/h/400/logo',
		'https://cdn.brandfetch.io/firstround.com/w/400/h/400/logo',
		'https://cdn.brandfetch.io/accel.com/w/400/h/400/logo'
	]}
/>

<Summary
	title="What we do"
	text="TendAI works as the connective tissue between your investment team and portfolio founders, monitoring companies continuously to surface follow-on opportunities before they're missed. We prevent exceptional companies from dying of neglect by ensuring every promising investment gets the attention and resources needed to thrive."
/>

<Testimonials
	testimonials={[
		{
			name: "Mei-Lin Chen",
			position: "General Partner",
			company: "Seedling Ventures",
			quote:
				"TendAI helped us identify three follow-on opportunities we would have missed in the noise of managing 42 portfolio companies. The automated monitoring saved our team 15 hours per week and caught early warning signs that let us step in before a promising company hit a funding crisis.",
			image: "/generated/image-an-asian-woman-gp-partner-in-her-early-4.webp"
		},
		{
			name: "Marcus Thompson",
			position: "Managing Partner",
			company: "Catalyst Capital",
			quote:
				"We nearly lost our best portfolio company because we didn't see the traction signals until their Series A was oversubscribed by competitors. TendAI now surfaces these moments automatically, giving us first-mover advantage on follow-on rounds and saving us from $2M in missed opportunities last quarter alone.",
			image: "/generated/image-a-black-male-venture-capitalist-in-his-l.webp"
		},
		{
			name: "Sofia Ramirez",
			position: "Partner",
			company: "Growth Stage Partners",
			quote:
				"The system paid for itself in the first month by flagging a founder who needed critical introductions we could make. What used to take quarterly reviews and manual Slack searches now happens continuously. Our portfolio companies feel more supported, and we're investing in winners instead of scrambling to salvage neglected investments.",
			image: "/generated/image-a-hispanic-woman-investor-in-her-late-30.webp"
		}
	]}
/>

<Features
	title="How TendAI helps you cultivate exceptional companies"
	subtitle="AI-powered portfolio intelligence that ensures no promising investment withers from neglect"
	features={[
		{
			title: "Continuous portfolio monitoring",
			description:
				"Our AI works 24/7 analyzing your portfolio companies, tracking progress signals you'd otherwise miss. Never lose sight of what's happening across your investments while you focus on new deals.",
			icon: IconRadar
		},
		{
			title: "Follow-on signal detection",
			description:
				"Identify promising follow-on opportunities before other investors do. TendAI surfaces traction signals and growth inflection points that indicate it's time to double down.",
			icon: IconTrendingUp
		},
		{
			title: "Founder needs surfacing",
			description:
				"Know when founders need your help before they have to ask. Our AI detects hiring challenges, product pivots, and growth bottlenecks so you can provide timely support that actually matters.",
			icon: IconHeart
		},
		{
			title: "Real-time traction alerts",
			description:
				"Get notified the moment something meaningful happens in your portfolio. From revenue milestones to key hires, stay connected to the wins that signal momentum.",
			icon: IconBell
		},
		{
			title: "Relationship intelligence",
			description:
				"Surface the full context of every founder relationship instantly. Access conversation history, past support provided, and connection strength to engage more meaningfully.",
			icon: IconNetwork
		},
		{
			title: "Portfolio health dashboard",
			description:
				"See your entire portfolio's health at a glance with AI-generated insights. Quickly identify which companies need attention and which are thriving without micromanagement.",
			icon: IconGauge
		}
	]}
/>
<AboutTeaser />
<CallToAction 
	title="Stop letting exceptional companies wither from neglect"
	subtitle="Join the waitlist today"
	description="Every day without TendAI is another day your portfolio grows harder to manage and critical signals slip through the cracks. Join leading VC firms who are already cultivating their portfolios more effectively with AI-powered monitoring that works 24/7."
	imageSrc="/generated/image-a-confident-venture-capital-partner-in-t.webp"
	callsToAction={[
		{
			href: "/",
			label: "Join waitlist",
			variant: "primary"
		},
		{
			href: "mailto:kenneth@alleycorp.com",
			label: "Get in touch",
			variant: "secondary"
		}
	]}
/>
