<script lang="ts">
	import Card from '$lib/Card.svelte';
	import Cards from '$lib/Cards.svelte';
	import Logo from '$lib/Logo.svelte';
	import Section from '$lib/Section.svelte';
</script>

<div class="flex min-h-screen w-screen flex-col bg-black text-white">
	<header class="flex items-center justify-between px-4 py-4 lg:px-64">
		<Logo class="h-8 w-auto text-white" />
		<div class="flex gap-2 text-4xl">
			<a href="https://github.com/unikorn-cloud" aria-label="unikorn github">
				<iconify-icon icon="mdi:github"></iconify-icon>
			</a>
		</div>
	</header>
	<main>
		<section
			id="hero"
			class="flex flex-col gap-4 bg-cover bg-center px-4 py-32 lg:px-64 lg:py-64"
			style="background-image: linear-gradient(rgba(24,63,63,0.8), rgba(0,0,0,0.6)), url(/hero.jpg)"
		>
			<h1 class="text-3xl font-bold lg:text-6xl">Open Source Infrastructure as a Service</h1>
			<h2 class="text-2xl italic text-[rgb(172,204,204)] lg:text-5xl">Simplified</h2>

			<aside class="pt-8 font-serif italic lg:text-2xl">
				Empower your users to spend more time creating and less time managing.
			</aside>
		</section>

		<Section title="What is Unikorn?">
			{#snippet headline()}
				Unikorn is an <em class="text-[rgb(172,204,204)]">opinionated</em> suite of services that manage
				the provisioning and life-cycle of compute infrastructure. The goal is to abstract away all the
				tedious day-to-day tasks associated with running compute infrastructure.
			{/snippet}

			<p>
				We've built a system to be truly proud of, leveraging best-in-breed Open Source components,
				and combining this with enterprise standard security best practices. The end result is easy
				to use, and secure by default.
			</p>

			<Cards>
				<Card
					icon="mdi:lock-outline"
					title="Flexible Security"
					link="https://github.com/unikorn-cloud/identity"
				>
					{#snippet content()}
						<p>Security is at the heart of everything in Unikorn.</p>
						<p>
							We don't ever collect or manage user passwords or credentials. This functionality is
							delegated to Google, Microsoft (covering most enterprise users), and GitHub for
							others. You can even bring your own OIDC compliant identity provider if your
							organization isn't covered by the supported options.
						</p>
						<p>
							On top of authentication, Unikorn support flexible role based access control (RBAC)
							where users are granted fine-grain access control to individual API endpoints. Most
							services act on behalf of a user reducing the permissions a user requires to actually
							provision infrastructure.
						</p>
					{/snippet}
				</Card>
				<Card
					icon="mdi:globe"
					title="Multi Region Cloud Providers"
					link="https://github.com/unikorn-cloud/region"
				>
					{#snippet content()}
						<p>
							Unikorn is architected in a way where it's only concerned with servers, networks,
							security group rules, etc. These are abstractions of the underlying cloud provider
							implementation, so everything appears and behaves the same. A network, for example,
							will be ready to run any kind of workload, handling the HPC requirements of AI
							workloads for example.
						</p>

						<p>
							Regions are defined as instances of a cloud provider e.g. an OpenStack deployment.
						</p>
					{/snippet}
				</Card>
				<Card
					icon="mdi:kubernetes"
					title="Simple Cluster Provisioning and Life-cycle Management"
					link="https://github.com/unikorn-cloud/kubernetes"
				>
					{#snippet content()}
						<p>
							Unikorn natively supports baremetal and Kubernetes cluster provisioning. The focus is
							on simplicity. You're only presented with limited options: cluster geometry and core
							software versions. This means less time procrastinating and more time doing what you
							actually need to do.
						</p>
						<p>
							For Kubernetes clusters in particular, Unikorn provisions clusters with a known
							working set of applications (powered by Helm). These are bundled together into tested
							and stable releases, and automatically upgraded to provide security guarantees around
							CVE mitigation.
						</p>
					{/snippet}
				</Card>
			</Cards>
		</Section>

		<div class="bg-[linear-gradient(rgb(63,128,128),rgb(40,80,80))] text-white">
			<Section title="Designed for AI/ML" image="/gpu.webp" image_alt="A GPU" image_class="h-48 w-auto">
				{#snippet headline()}
					Although Unikorn can be used for general purpose compute, its core focus will always be on
					AI. GPUs are <em>first-class</em> citizens, and the intention is always to provide higher level
					machine learning and generative AI services.
				{/snippet}

				<p>
					With that aim, Unikorn has been designed to support rapid 3rd party service integration
					with your AI/ML applications. All the authentication, authorization and monitoring
					capabilities are available with little effort through reusable libraries that integrate
					with Unikorn services.
				</p>
			</Section>
		</div>

		<Section title="Easy to Use" image="/ui.webp" image_alt="unikorn ui" image_class="max-h-64 w-auto" image_position="start">
			{#snippet headline()}
				We've been inspired by the best designs in the world.
			{/snippet}

			<p>
				No one wants to read reams of documentation to understand how something works.
				We get you, and our mission is to provide simple and intuitive interfaces that anyone can use.
				We've reduced the input you need to provide to get up and running quickly to the bare minimum.
				Fewer distractions, more productivity.
			</p>

			<p>
				We want Unikorn to be <em>the</em> tool we &ndash; as engineers &ndash; want to use.
				But where that's not sufficient, Unikorn provides a rich REST API to enable your creativity and provide automation.
			</p>
		</Section>
	</main>
	<footer class="flex flex-col items-center px-4 py-4 lg:px-64 text-gray-500">
		&copy; The Unikorn Authors 2025
	</footer>
</div>
