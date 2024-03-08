<script lang="ts">

	import { AccordionItem } from "@skeletonlabs/skeleton";
    import none_icon from "$lib/icons/none.png";

    export let icon_src: string = "";
    export let icon_alt: string;
    export let item_summary: string;
    
</script>

<AccordionItem>
    <svelte:fragment slot="iconOpen"><img src={none_icon} alt="blank icon"></svelte:fragment>
    <svelte:fragment slot="iconClosed"><img src={none_icon} alt="blank icon"></svelte:fragment>
    <svelte:fragment slot="lead"><img src={icon_src} alt={icon_alt}/></svelte:fragment>
    <svelte:fragment slot="summary"><span class="text-2xl ml-2"><strong>{item_summary}</strong></span></svelte:fragment>
    <svelte:fragment slot="content">
        <slot />
    </svelte:fragment>
</AccordionItem>