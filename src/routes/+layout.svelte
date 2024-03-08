<script lang="ts">
	import '../app.postcss'
	import { TabGroup, Tab, TabAnchor, LightSwitch } from '@skeletonlabs/skeleton'
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
<div class="card text-xl p-4 mx-8">
	<code class="code">v0.1</code>
	| <a href="https://github.com/owenleonard11/titlegrok/" class="anchor">GitHub</a>
	| <a href="https://titlegrok.readthedocs.io/" class="anchor">ReadTheDocs</a>
	| Icons by <a href="https://icons8.com" class="anchor">Icons8</a>
</div>

