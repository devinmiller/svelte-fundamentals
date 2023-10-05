<script lang="ts">
    import { get_twemoli_url } from "./utils";

    export let found: string[];
</script>

<div class="found">
    {#each found as emoji (emoji)}
        <img alt={emoji} src={get_twemoli_url(emoji)} />
    {/each}
</div>

<style>
    .found {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 0.5em;
    }

    img {
        width: 5em;
        height: 5em;
    }
</style>