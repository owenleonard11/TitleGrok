<script lang="ts">
	import '../app.postcss'
	import { TabGroup, TabAnchor } from '@skeletonlabs/skeleton'
	import { LightSwitch } from '@skeletonlabs/skeleton'
	import { page } from '$app/stores';
</script>

<TabGroup class="text-2xl px-8 pt-8">
	<TabAnchor selected = {$page.url.pathname === "/"} href="/">
		<svelte:fragment slot="lead">TitleGrok</svelte:fragment>
	</TabAnchor>
	<TabAnchor selected = {$page.url.pathname === "/usage"} href="/usage">Usage</TabAnchor>
	<TabAnchor selected = {$page.url.pathname === "/about"} href="/about">About</TabAnchor>
</TabGroup>

<slot />


