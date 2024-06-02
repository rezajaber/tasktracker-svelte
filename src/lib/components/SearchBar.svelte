<script lang="ts">
  import { Search, CirclePlus, SlidersHorizontal } from "lucide-svelte";

  import { Button } from "$lib/components/ui/button/index.js";
  import Input from "./ui/input/input.svelte";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";

  let showDone: boolean = false;
  let overdue: boolean = false;
  let critical: boolean = false;
  let high: boolean = false;
  let normal: boolean = false;
  let low: boolean = false;
</script>
  
<div class="mx-auto grid gap-2 md:mx-0 md:flex md:justify-between">
  <div class="flex gap-2">
    <div class="relative w-[22rem] max-w-md items-center md:w-96">
      <Input
        id="search"
        type="text"
        placeholder="Create or Search for a Task..."
        class="pl-10"
      />
      <span
        class="absolute inset-y-0 start-0 flex items-center justify-center px-3"
      >
        <Search class="w-5 text-muted-foreground" />
      </span>
    </div>

    <Button class="hidden md:flex" type="submit">
      <CirclePlus class="mr-1.5 w-4" />Create Task
    </Button>
  </div>

  <div class="flex justify-between">
    <Button class="md:hidden" type="submit"
      ><CirclePlus class="mr-1.5 w-4" />Create Task
    </Button>

  <DropdownMenu.Root>
    <DropdownMenu.Trigger asChild let:builder>
      <Button builders={[builder]}><SlidersHorizontal class="mr-1.5 w-4" />Filter</Button>
    </DropdownMenu.Trigger>
    <DropdownMenu.Content class="w-56">
      <DropdownMenu.Label>Status</DropdownMenu.Label>
      <DropdownMenu.Separator />
      <DropdownMenu.Group>
        <DropdownMenu.CheckboxItem bind:checked={showDone}>
          Show Done
        </DropdownMenu.CheckboxItem>
        <DropdownMenu.CheckboxItem bind:checked={overdue}>
          Overdue
        </DropdownMenu.CheckboxItem>
        <DropdownMenu.Separator />
      </DropdownMenu.Group>
      <DropdownMenu.Label>Priorities</DropdownMenu.Label>
      <DropdownMenu.Separator />
      <DropdownMenu.Group>
        <DropdownMenu.CheckboxItem bind:checked={critical}>
          Critical
        </DropdownMenu.CheckboxItem>
        <DropdownMenu.CheckboxItem bind:checked={high}>
          High
        </DropdownMenu.CheckboxItem>
        <DropdownMenu.CheckboxItem bind:checked={normal}>
          Normal
        </DropdownMenu.CheckboxItem>
        <DropdownMenu.CheckboxItem bind:checked={low}>
          Low
        </DropdownMenu.CheckboxItem>
      </DropdownMenu.Group>
    </DropdownMenu.Content>
  </DropdownMenu.Root>
  </div>
</div>
  