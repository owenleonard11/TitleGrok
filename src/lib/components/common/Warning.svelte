<script lang="ts">
	import { slide } from "svelte/transition";

    export let variant: string;
    export let message: string;
</script>

<aside class="alert variant-{variant}" in:slide out:slide>
    <span class="badge-icon variant-filled-warning text-xl">!</span>
    <div class="alert-message">{message}</div>
</aside>