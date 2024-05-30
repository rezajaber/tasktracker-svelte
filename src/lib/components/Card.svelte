<script lang="ts">
  import { Circle, CalendarClock, Ellipsis, ListChecks, Trash2, Pencil } from 'lucide-svelte';
  import { Button } from "$lib/components/ui/button/index.js";
  import { Separator } from "$lib/components/ui/separator/index.js";
  import { Input } from "$lib/components/ui/input";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";

  import CategoryEdit from "$lib/components/CategoryEdit.svelte";

  export let priorityColor: string = 'text-red-500'; // Set a default color
  export let cardCategory: string = '';
  export let cardTitle: string = '';
  export let cardContent: string = '';
  export let cardDate: string = '';

  let category = "category";

  const colors = ['text-green-500', 'text-yellow-500', 'text-orange-500', 'text-red-500'];
  let currentColorIndex = colors.indexOf(priorityColor);

  function changeColor() {
    currentColorIndex = (currentColorIndex + 1) % colors.length;
    priorityColor = colors[currentColorIndex];
  }
</script>
  
<!-- FULL CARD -->
<div class="card-container grid-rows-layout grid gap-3.5 rounded-lg p-5">
  <!-- HEADER OF CARD -->
  <div class="flex justify-between items-center">
    <div class="flex items-center gap-2">
      <Button on:click={changeColor} size="xs" variant="ghost" class="p-0 hover:bg-transparent"><Circle class={`h-3 w-3 ${priorityColor} fill-current`} /></Button>
      <span class="font-medium">{cardCategory}</span>
    </div>
  
    <!-- CATEGORY -->
    <DropdownMenu.Root>
      <DropdownMenu.Trigger asChild let:builder>
        <Button size="xs" builders={[builder]}>
          <Pencil class="w-4" />
        </Button>
      </DropdownMenu.Trigger>
      <DropdownMenu.Content class="w-52">
        <DropdownMenu.RadioGroup bind:value={category}>
          <DropdownMenu.RadioItem value="Critical">No Categories found</DropdownMenu.RadioItem>
          <CategoryEdit />
        </DropdownMenu.RadioGroup>
      </DropdownMenu.Content>
    </DropdownMenu.Root>
  </div>

  <!-- BODY OF CARD -->
  <div class="-mt-1 flex flex-col gap-1">
    <Input  
      type="text"
      placeholder="Taskname" 
      bind:value={cardTitle}
      class="line-clamp-1 text-lg font-semibold h-7 resize-none truncate border-0 px-0 focus-visible:ring-0 focus-visible:ring-offset-0">{cardTitle}</Input>
    <textarea class="line-clamp-3 h-[52px] resize-none text-sm outline-0">{cardContent}</textarea>
  </div>

  <Separator class="w-full bg-gray-500" />

  <!-- FOOTER OF CARD -->
  <div class="flex items-center justify-between">
    <div class="flex items-center gap-2">
      <CalendarClock class="h-5 w-5" />
      <span class="text-sm">{cardDate}</span>
    </div>

    <DropdownMenu.Root>
      <DropdownMenu.Trigger asChild let:builder>
          <Button builders={[builder]} variant="ghost" class="hover:bg-transparent px-0">
            <Ellipsis class="h-6 w-6 cursor-pointer duration-300 ease-in-out hover:rotate-90"/>
          </Button>
      </DropdownMenu.Trigger>
    
      <DropdownMenu.Content class="grid w-40">
        <div class="flex cursor-pointer items-center gap-2 rounded-lg px-3 py-0.5 duration-300 ease-in-out hover:bg-accent">
          <ListChecks class="w-5 text-green-600"/>
          <span class="text-sm">Task Done</span>
        </div>
        <div class="flex cursor-pointer items-center gap-2 rounded-lg px-3 py-0.5 duration-300 ease-in-out hover:bg-accent">
          <Trash2 class="w-5 text-red-600"/>
          <span class="text-sm">Delete Task</span>
        </div>
      </DropdownMenu.Content>
    </DropdownMenu.Root>
  </div>
</div>
  
<style scoped>
  .card-container {
    width: 340px;
    height: 220px;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  }
  .grid-rows-layout {
    grid-template-rows: auto 1fr auto auto;
  }
</style>
