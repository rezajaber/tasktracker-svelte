<script lang="ts">
import {
    Button,
   
  } from "$lib/components/ui/button/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import * as Dialog from "$lib/components/ui/dialog/index.js";
  import { CirclePlus } from 'lucide-svelte';
  import { Trash2 } from "lucide-svelte";
</script>

<div class="w-full grid">
  <Dialog.Root>
    <Dialog.Trigger>
      <Button class="my-1 w-full">
        <CirclePlus class="mr-1.5 w-4" />
        Edit Categories
      </Button>
    </Dialog.Trigger>

    <Dialog.Content class="sm:max-w-[425px]">
      <Dialog.Header>
        <Dialog.Title>Edit Categories</Dialog.Title>
        <Dialog.Description>
          Here you can add or delete categories!
        </Dialog.Description>
      </Dialog.Header>

      <div class="grid gap-5">
        <div class="grid gap-2">
          <div class="flex gap-2">
            <Input
              disabled
              class="border border-primary bg-primary text-white"
            />
            <Button><Trash2 class="w-5"/></Button>
          </div>
        </div>

        <div class="flex flex-col gap-2">
          <Input
            placeholder="Create a new Task..."
            class="border border-primary focus-visible:ring-0"
          />
          <Button type="submit">Create</Button>
        </div>
      </div>
    </Dialog.Content>
  </Dialog.Root>
</div>
