<script>
    import { page } from '$app/stores';
</script>

<svelte:head>
    <title>{$page.status} {$page.error.message} | Hangar 84</title>
    <meta content="{$page.status} {$page.error.message} | Hangar 84" property="og:title" />
    {#if $page.status === 404}
        <meta content="You shared a non-existent page. How awkward..." property="og:description" />
    {:else}
        <meta content="You shared a broken page. How very awkward..." property="og:description" />
    {/if}
    <meta content="https://hangar84.org/" property="og:url" />
    <meta content="#ff0000" data-react-helmet="true" name="theme-color" />
</svelte:head>

<div class="text-center py-8">
    <h1 class="text-6xl font-bold">{$page.status} {$page.error.message}</h1>
    <br />
    {#if $page.status === 404}
        <p class="text-2xl">The resource you have tried to access does not exist.</p>
    {/if}
</div>