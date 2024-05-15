<script lang="ts">
  import Input from "./ui/input/input.svelte";
  import { Button } from "$lib/components/ui/button/index.js";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
  import { Search, CirclePlus, SlidersHorizontal } from "lucide-svelte";

  let showDone = false;
  let overdue = false;
  let critical = false;
  let high = false;
  let normal = false;
  let low = false;
</script>
  
  <div class="flex justify-between">
    <div class="flex gap-2">
      <div class="relative w-96 max-w-md items-center">
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
  
      <Button type="submit">
        <CirclePlus class="mr-1.5 w-4" />Create Task
      </Button>
    </div>
  
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
  