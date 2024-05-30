<script lang="ts">
    import { Info } from 'lucide-svelte';
    import { Button } from "$lib/components/ui/button/index.js";
    import * as Dialog from "$lib/components/ui/dialog/index.js";

    import Card from "$lib/components/Card.svelte";

    const cards = [
    { priorityColor: "text-red-500", cardCategory: "Cyber Security", cardTitle: "Hack The Box", cardContent: "Explore the latest trends in cybersecurity and learn how to protect your systems effectively.", cardDate: "22. September 2024" },];
</script>
  
<div class="">
  <Dialog.Root>
    <Dialog.Trigger>
      <Button><Info class="w-5" /></Button>
    </Dialog.Trigger>
    <Dialog.Content class="max-h-[90vh] max-w-xs grid-rows-[auto_minmax(0,1fr)_auto] rounded-md p-0 sm:max-w-[425px] place-items-center">
      <Dialog.Header class="p-6 pb-0">
        <Dialog.Title>Information - TaskTracker</Dialog.Title>
        <Dialog.Description>
          Below you can see what everything does and how it is supposed to work!
        </Dialog.Description>
      </Dialog.Header>

      {#each cards as card}
        <Card  
          priorityColor={card.priorityColor} 
          cardCategory={card.cardCategory} 
          cardTitle={card.cardTitle} 
          cardContent={card.cardContent} 
          cardDate={card.cardDate}  />
      {/each}
      
      <div class="mt-1 grid w-full gap-2 px-6 pb-6 text-sm sm:text-base">
        <p
          class="rounded-md bg-primary px-2.5 py-1 text-center text-sm text-white"
        >
          Click the circle to change the priority of the task.
        </p>

        <p
          class="rounded-md bg-primary px-2.5 py-1 text-center text-sm text-white"
        >
          Click the edit button to add or delete categories.
        </p>

        <p
          class="rounded-md bg-primary px-2.5 py-1 text-center text-sm text-white"
        >
          Click the title to edit it.
        </p>

        <p
          class="rounded-md bg-primary px-2.5 py-1 text-center text-sm text-white"
        >
          Click on the description to edit it.
        </p>

        <p
          class="rounded-md bg-primary px-2.5 py-1 text-center text-sm text-white"
        >
          Click the date icon to change the date.
        </p>

        <p
          class="rounded-md bg-primary px-2.5 py-1 text-center text-sm text-white"
        >
          Click the three dots to delete or mark a task as done.
        </p>
      </div>
    </Dialog.Content>
  </Dialog.Root>
</div>