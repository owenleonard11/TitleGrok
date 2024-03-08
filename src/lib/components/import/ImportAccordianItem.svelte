<script lang="ts">

	import { AccordionItem } from "@skeletonlabs/skeleton";
    import none_icon from "$lib/icons/none.png";

    export let iconSrc: string = "";
    export let iconAlt: string;
    export let itemSummary: string;
    
</script>

<AccordionItem>
    <svelte:fragment slot="iconOpen"><img src={none_icon} alt="blank icon"></svelte:fragment>
    <svelte:fragment slot="iconClosed"><img src={none_icon} alt="blank icon"></svelte:fragment>
    <svelte:fragment slot="lead"><img src={iconSrc} alt={iconAlt}/></svelte:fragment>
    <svelte:fragment slot="summary"><span class="text-2xl ml-2"><strong>{itemSummary}</strong></span></svelte:fragment>
    <svelte:fragment slot="content">
        <slot />
    </svelte:fragment>
</AccordionItem>