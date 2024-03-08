<script lang="ts">
	import { FileDropzone } from "@skeletonlabs/skeleton";
    import { slide } from "svelte/transition"

    import ImportAccordianItem from "./ImportAccordianItem.svelte";
    import Warning from "$lib/components/common/Warning.svelte";
    import upload_icon from "$lib/icons/upload.png"

    const ACCEPTED_EXTS = ['PDF', 'DOCX', 'TXT']
    const upload_item = { iconSrc: upload_icon, iconAlt: "upload icon", itemSummary: "From a local file" }
    
    let files: FileList;

    let showFileWarning   : boolean = false;
    let fileWarningMessage: string;
    let showFileCard      : boolean = false;
    let fileExt           : string | undefined;
    let fileName          : string;

    const handleFileUpload = () => {
        console.log(files[0].name)
        fileName = files[0].name;
        fileExt = fileName.split('.').at(-1)?.toUpperCase();
        if (!fileExt) { 
            showFileWarning = true;
            showFileCard = false;
            fileWarningMessage = "Unrecognized filetype. Please upload a different file.";
        } else if (!ACCEPTED_EXTS.includes(fileExt)) {
            showFileWarning = true;
            showFileCard = false;
            fileWarningMessage = `Unsupported extension: ${fileExt}. Please upload a different file.`;
        } else {
            showFileWarning = false;
            showFileCard = true;
        }
    }
</script>

<ImportAccordianItem {...upload_item}>
    <FileDropzone name="files" bind:files on:change={handleFileUpload}>
        <svelte:fragment slot="message"><strong>Upload a file</strong> or drag and drop</svelte:fragment>
        <svelte:fragment slot="meta">.txt, .pdf, and .docx currently supported</svelte:fragment>
    </FileDropzone>
    {#if showFileWarning}
        <Warning variant="ghost-warning" message={fileWarningMessage}></Warning>
    {/if}
    {#if showFileCard}
        <aside class="alert variant-ghost-success" in:slide out:slide>
            <span class="badge">{fileExt}</span>
            <div class="alert-message">{fileName}</div>
            <div class="alert-actions">
                <button class="btn-icon variant-ghost text-3xl" on:click={() => showFileCard=false}>×</button>
            </div>
        </aside>
    {/if}
</ImportAccordianItem>