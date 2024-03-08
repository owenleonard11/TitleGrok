<script lang="ts">

	import { Accordion } from "@skeletonlabs/skeleton";

    import ImportAccordianItem from "$lib/components/import/ImportAccordianItem.svelte";
	import FileItem from "$lib/components/import/FileItem.svelte";

    import link_icon   from "$lib/icons/link.png";
    import paste_icon  from "$lib/icons/paste.png"

    const web_item    = { iconSrc: link_icon,   iconAlt: "link icon",   itemSummary: "From the web" }
    const paste_item  = { iconSrc: paste_icon,  iconAlt: "paste icon",  itemSummary: "From pasted text" }
</script>

<Accordion autocollapse>
    <ImportAccordianItem {...web_item}>
        <div class="input-group input-group-divider grid-cols-[auto_1fr_auto]">
            <div class="input-group-shim">https://</div>
            <input class="text-xl" type="text" placeholder="www.example.com" />
        </div>
    </ImportAccordianItem>
    <FileItem />
    <ImportAccordianItem {...paste_item}>
        <textarea class="textarea text-xl" placeholder="Paste full text here"></textarea>
    </ImportAccordianItem>
</Accordion>