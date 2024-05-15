<script lang="ts">
  import MarkDownLegend from "$lib/components/MarkDownLegend.svelte";
  import CategoryEdit from "$lib/components/CategoryEdit.svelte";

  import { GalleryVerticalEnd, Layers, CalendarIcon } from "lucide-svelte";

  import { Button } from "$lib/components/ui/button/index.js";
  import { Calendar } from "$lib/components/ui/calendar/index.js";
  import { cn } from "$lib/utils.js";
  import { DateFormatter, getLocalTimeZone } from "@internationalized/date";
  import type { DateValue } from "@internationalized/date";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
  import * as Popover from "$lib/components/ui/popover/index.js";
  
  let priority  = "priority";
  let category = "category";
  let value: DateValue | undefined = undefined;

  const df = new DateFormatter("en-US", {
  dateStyle: "long"
  });
</script>
  
<div>
  <div class="flex justify-between">
    <div class="flex gap-2">
      <!-- PRIORITY -->
      <DropdownMenu.Root>
        <DropdownMenu.Trigger asChild let:builder> 
          <Button builders={[builder]}>
            <GalleryVerticalEnd class="mr-1.5 w-4" />Priority
          </Button>
        </DropdownMenu.Trigger>
        <DropdownMenu.Content class="w-40">
          <DropdownMenu.RadioGroup bind:value={priority}>
            <DropdownMenu.RadioItem value="Critical">Critical</DropdownMenu.RadioItem>
            <DropdownMenu.RadioItem value="High">High</DropdownMenu.RadioItem>
            <DropdownMenu.RadioItem value="Normal">Normal</DropdownMenu.RadioItem>
            <DropdownMenu.RadioItem value="Low">Low</DropdownMenu.RadioItem>
          </DropdownMenu.RadioGroup>
        </DropdownMenu.Content>
      </DropdownMenu.Root>

      <!-- CATEGORY -->
      <DropdownMenu.Root>
        <DropdownMenu.Trigger asChild let:builder>
          <Button builders={[builder]}>
            <Layers class="mr-1.5 w-4" />Category
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

    <div class="flex gap-2">
      <!-- CALENDAR -->
      <Popover.Root>
        <Popover.Trigger asChild let:builder>
          <Button class={cn('w-fit justify-start bg-primary', !$value && 'text-white')} builders={[builder]}>
            <CalendarIcon class="mr-1.5 w-4 text-white" />
            {value ? df.format(value.toDate(getLocalTimeZone())) : "Pick a date"}
          </Button>
        </Popover.Trigger>
        <Popover.Content class="w-auto p-0">
          <Calendar bind:value initialFocus />
        </Popover.Content>
      </Popover.Root>

      <MarkDownLegend />
    </div>
  </div>
</div>
  