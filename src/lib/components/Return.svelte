<script lang="ts">
    export let deep: string = "";
</script>

<div class="w-full flex justify-center gap-10">
    {#if deep}
        <a href="/" class="btn-link">
            &lt;&lt; Home
        </a>
    {/if}

    <a href={`/${deep}`} class="btn-link">
        &lt; Retour
    </a>
</div>