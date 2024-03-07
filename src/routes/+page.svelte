<script lang="ts">
    import { Accordion, AccordionItem } from '@skeletonlabs/skeleton';
</script>

<Accordion class="px-8 pt-8 text-xl">
    <AccordionItem open>
        <svelte:fragment slot="summary"><h2 class="h2">Step 1: Import</h2></svelte:fragment>
        <svelte:fragment slot="content">
            Content Here!
        </svelte:fragment>
    </AccordionItem>
    <AccordionItem open>
        <svelte:fragment slot="summary"><h2 class="h2">Step 2: Clean</h2></svelte:fragment>
        <svelte:fragment slot="content">
            Content Here!
        </svelte:fragment>
    </AccordionItem>
    <AccordionItem open>
        <svelte:fragment slot="summary"><h2 class="h2">Step 3: Export</h2></svelte:fragment>
        <svelte:fragment slot="content">
            Content Here!
        </svelte:fragment>
    </AccordionItem>
</Accordion>