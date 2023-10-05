<script lang="ts">
  import { get_twemoli_url } from "./utils";

    export let emoji: string;
    export let selected: boolean;
    export let found: boolean;
</script>

<div class="square" class:flipped={selected || found}>
    <button on:click />

    <div class="background" />

    {#if !found}
        <img alt={emoji} src={get_twemoli_url(emoji)} />
    {/if}
    
</div>

<style>
    .square {
        display: flex;
        justify-content: center;
        align-items: center;
        transform-style: preserve-3d;
        transition: transform 0.4s;
    }

    img {
        width: 5em;
        height: 5em;
        transform: rotateY(180deg);
        backface-visibility: hidden;
    }

    .flipped {
        transform: rotateY(180deg);
    }

    .background {
        position: absolute;
        background-color: white;
        border: .5em solid #eee;
        transform: rotateY(180deg);
        backface-visibility: hidden;
        width: 100%;
        height: 100%;
        border-radius: 1em;
    }

    button {
        cursor: pointer;
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
        background: #eee;
        border: 0;
        border-radius: 1em;
        font-size: inherit;
    }
</style>
