<script lang="ts">
    import { Accordion, AccordionItem } from '@skeletonlabs/skeleton';

    import ImportAccordian from '$lib/components/import/ImportAccordian.svelte';
</script>

<Accordion autocollapse class="px-8 pb-4 text-xl">
    <AccordionItem open>
        <svelte:fragment slot="summary"><h2 class="h2">Step 1: Import</h2></svelte:fragment>
        <svelte:fragment slot="content"><ImportAccordian /></svelte:fragment>
    </AccordionItem>
    <AccordionItem>
        <svelte:fragment slot="summary"><h2 class="h2">Step 2: Configure</h2></svelte:fragment>
        <svelte:fragment slot="content">
            Content Here!
        </svelte:fragment>
    </AccordionItem>
    <AccordionItem>
        <svelte:fragment slot="summary"><h2 class="h2">Step 3: Process</h2></svelte:fragment>
        <svelte:fragment slot="content">
            Content Here!
        </svelte:fragment>
    </AccordionItem>
    <AccordionItem>
        <svelte:fragment slot="summary"><h2 class="h2">Step 4: Export</h2></svelte:fragment>
        <svelte:fragment slot="content">
            Content Here!
        </svelte:fragment>
    </AccordionItem>
</Accordion>