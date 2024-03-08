<script lang="ts">

	import { Accordion, FileDropzone } from "@skeletonlabs/skeleton";
	import ImportAccordianItem from "./ImportAccordianItem.svelte";

    import link_icon from "$lib/icons/link.png";
    import upload_icon from "$lib/icons/upload.png"
    import paste_icon from "$lib/icons/paste.png"

    const web_item = { 
        icon_src: link_icon, icon_alt: "link icon", item_summary: "From the web" }
    const upload_item = {
        icon_src: upload_icon, icon_alt: "upload icon", item_summary: "From a local file" }
    const paste_item = {
        icon_src: paste_icon, icon_alt: "paste icon", item_summary: "From pasted Text" }

</script>

<Accordion autocollapse>
    <ImportAccordianItem {...web_item}>
        <div class="input-group input-group-divider grid-cols-[auto_1fr_auto]">
            <div class="input-group-shim">https://</div>
            <input class="text-xl" type="text" placeholder="www.example.com" />
        </div>
    </ImportAccordianItem>
    <ImportAccordianItem {...upload_item}>
        <FileDropzone name="files">
            <svelte:fragment slot="message"><strong>Upload a file</strong> or drag and drop</svelte:fragment>
            <svelte:fragment slot="meta">.txt, .pdf, and .docx currently supported</svelte:fragment>
        </FileDropzone>
    </ImportAccordianItem>
    <ImportAccordianItem {...paste_item}>
        <textarea class="textarea text-xl" placeholder="Paste full text here"></textarea>
    </ImportAccordianItem>
</Accordion>