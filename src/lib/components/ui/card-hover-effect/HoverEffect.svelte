<script lang="ts">
  import { cn } from "$lib/utils";
  import { Motion, AnimateSharedLayout, AnimatePresence } from "svelte-motion";
  import Card from "./Card.svelte";
  import CardTitle from "./CardTitle.svelte";
  import CardDescription from "./CardDescription.svelte";

  // Type for items prop
  type Item = {
    title: string;
    description: string;
    link: string;
  };
  export let items: Item[] = [];
  let _class = "";
  export { _class as class };

  let hoveredIndex: number | null = null;
</script>

<div
  class={cn("grid grid-cols-1 md:grid-cols-2  lg:grid-cols-3  py-10", _class)}
>
  <AnimateSharedLayout>
    {#each items as item, idx (item.title)} 
      <a
        class="relative group block p-2 h-full w-full"
        on:mouseenter={() => (hoveredIndex = idx)}
        on:mouseleave={() => (hoveredIndex = null)}
        href={item.link}
        target="_blank" rel="noopener noreferrer"
      >
        <AnimatePresence show={hoveredIndex === idx}>
          {#if hoveredIndex === idx}
            <Motion
              layoutId="hoverBackground"
              initial={{ opacity: 0 }}
              animate={{
                opacity: 1,
                transition: { duration: 0.15 },
              }}
              exit={{
                opacity: 0,
                transition: { duration: 0.15, delay: 0.2 },
              }}
              let:motion
            >
              <span
                use:motion
                class="absolute inset-0 h-full w-full bg-neutral-200 dark:bg-slate-800/[0.8] block rounded-3xl"
              >
              </span>
            </Motion>
          {/if}
        </AnimatePresence>
        <Card>
          <CardTitle>{item.title}</CardTitle>
          <CardDescription>{item.description}</CardDescription>
        </Card>
      </a>
    {/each}
  </AnimateSharedLayout>
</div>
