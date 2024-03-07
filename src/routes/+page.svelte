<script lang="ts">
    import { Accordion, AccordionItem } from '@skeletonlabs/skeleton';
    import { FileDropzone } from '@skeletonlabs/skeleton';

    import link_icon from "$lib/icons/link.png"
    import paste_icon from "$lib/icons/paste.png"
    import upload_icon from "$lib/icons/upload.png"
</script>

<Accordion class="px-8 pb-4 text-xl">
    <AccordionItem open>
        <svelte:fragment slot="summary"><h2 class="h2">Step 1: Import</h2></svelte:fragment>
        <svelte:fragment slot="content">
            <Accordion autocollapse>
                <AccordionItem>
                    <svelte:fragment slot="iconClosed"></svelte:fragment>
	                <svelte:fragment slot="iconOpen"></svelte:fragment>
                    <svelte:fragment slot="lead"><img src={link_icon} alt="link icon"/></svelte:fragment>
                    <svelte:fragment slot="summary"><span class="text-2xl ml-2"><strong>From the web</strong></span></svelte:fragment>
                    <svelte:fragment slot="content">
                        <div class="input-group input-group-divider grid-cols-[auto_1fr_auto]">
                            <div class="input-group-shim">https://</div>
                            <input class="text-xl" type="text" placeholder="www.example.com" />
                        </div>
                    </svelte:fragment>
                </AccordionItem>
                <AccordionItem>
                    <svelte:fragment slot="lead"><img src={upload_icon} alt="upload icon" class="object-scale-down"/></svelte:fragment>
                    <svelte:fragment slot="summary"><span class="text-2xl ml-2"><strong>From a local file</strong></span></svelte:fragment>
                    <svelte:fragment slot="content">
                        <FileDropzone name="files">
                            <svelte:fragment slot="message"><strong>Upload a file</strong> or drag and drop</svelte:fragment>
                            <svelte:fragment slot="meta">.txt, .pdf, and .docx currently supported</svelte:fragment>
                        </FileDropzone>
                    </svelte:fragment>
                </AccordionItem>
                <AccordionItem>
                    <svelte:fragment slot="lead"><img src={paste_icon} alt="paste icon" class="object-scale-down"/></svelte:fragment>
                    <svelte:fragment slot="summary"><span class="text-2xl ml-2"><strong>From pasted text</strong></span></svelte:fragment>
                    <svelte:fragment slot="content">
                        <textarea class="textarea text-xl" placeholder="Paste full text here"></textarea>
                    </svelte:fragment>
                </AccordionItem>
            </Accordion>
        </svelte:fragment>
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