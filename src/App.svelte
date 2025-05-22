<script>
  import { Route } from "tinro";
  import { ModeWatcher } from "mode-watcher";
  import Lazyload from "$lib/components/utils/Lazyload.svelte";
  import ToggleTheme from "$lib/components/utils/toggleTheme.svelte";
</script>

<ModeWatcher />
<ToggleTheme />

<Route path="/">
  <Lazyload props={{ component: import("./routes/Index.svelte") }} />
</Route>
<Route path="/orden/:id" let:params>
  <Lazyload
    props={{ component: import("./routes/ViewOrder.svelte"), params }}
  />
</Route>
