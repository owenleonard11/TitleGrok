<script lang="ts">

	import { Accordion, FileDropzone } from "@skeletonlabs/skeleton";
	import ImportAccordianItem from "./ImportAccordianItem.svelte";

    import link_icon from "$lib/icons/link.png";
    import upload_icon from "$lib/icons/upload.png"
    import paste_icon from "$lib/icons/paste.png"

    const ACCEPTED_EXTS = ['pdf', 'docx', 'txt']

    const web_item = { iconSrc: link_icon, iconAlt: "link icon", itemSummary: "From the web" }
    const upload_item = { iconSrc: upload_icon, iconAlt: "upload icon", itemSummary: "From a local file" }
    const paste_item = { iconSrc: paste_icon, iconAlt: "paste icon", itemSummary: "From pasted text" }

    let files: FileList;
    let showFileWarning: boolean = false;
    let showFileCard: boolean = true;
    let fileWarningMessage: string;
    let fileName: string;
    const handleFileUpload = () => {
        console.log(files[0].name)
        const fileExt: string | undefined = files[0].name.split('.').at(-1);
        if (!fileExt) { 
            showFileWarning = true;
            fileWarningMessage = "Unrecognized filetype. Please upload a different file.";
        } else if (!ACCEPTED_EXTS.includes(fileExt.toLowerCase())) {
            showFileWarning = true;
            fileWarningMessage = `Unsupported extension: ${fileExt}. Please upload a different file.`
        } else {
            showFileWarning = false;
        }
    }
</script>

<Accordion autocollapse>
    <ImportAccordianItem {...web_item}>
        <div class="input-group input-group-divider grid-cols-[auto_1fr_auto]">
            <div class="input-group-shim">https://</div>
            <input class="text-xl" type="text" placeholder="www.example.com" />
        </div>
    </ImportAccordianItem>
    <ImportAccordianItem {...upload_item}>
        <FileDropzone name="files" bind:files on:change={handleFileUpload}>
            <svelte:fragment slot="message"><strong>Upload a file</strong> or drag and drop</svelte:fragment>
            <svelte:fragment slot="meta">.txt, .pdf, and .docx currently supported</svelte:fragment>
        </FileDropzone>
        {#if showFileWarning}
            <aside class="alert variant-ghost-warning">
                <span class="badge-icon variant-filled-warning text-xl">!</span>
                <div class="alert-message">{fileWarningMessage}</div>
            </aside>
        {/if}
    </ImportAccordianItem>
    <ImportAccordianItem {...paste_item}>
        <textarea class="textarea text-xl" placeholder="Paste full text here"></textarea>
    </ImportAccordianItem>
</Accordion>