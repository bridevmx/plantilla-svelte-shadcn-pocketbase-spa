<script>
    export let props;
    const { component, params } = props;    
</script>

{#await component.then ? component : component()}
    <!-- un componente que mustre que se esta cargando el contenido  -->
    <div class="flex justify-center items-center h-screen">
        <div class="loader"></div>
    </div>
{:then child}
    <svelte:component this={child.default} {params}  />
{/await}
