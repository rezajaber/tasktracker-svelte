<script lang="ts">
    import { Info } from 'lucide-svelte';

    import { Button } from "$lib/components/ui/button/index.js";
    import * as Dialog from "$lib/components/ui/dialog/index.js";
</script>
  
<Dialog.Root>
  <Dialog.Trigger>
    <Button><Info class="w-5" /></Button>
  </Dialog.Trigger>
  <Dialog.Content class="max-h-[90vh] max-w-xs grid-rows-[auto_minmax(0,1fr)_auto] rounded-md p-0 sm:max-w-[425px]">
    <Dialog.Header class="p-6 pb-0">
      <Dialog.Title>Information - TaskTracker</Dialog.Title>
      <Dialog.Description>
        Below you can see what everything does and how it is supposed to work!
      </Dialog.Description>
    </Dialog.Header>
    <div class="grid gap-4 overflow-y-auto px-6">
      <div class="flex flex-col justify-between">
        <div class="grid gap-6">
          <div
            class="grid grid-cols-2 gap-2 text-center text-sm text-white sm:text-base"
          >
            <p class="rounded-md bg-primary px-2.5 py-1">
              -- converts to —
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              ... converts to …
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              &lt;- converts to ←
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              -&gt; converts to →
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              (c) converts to ©
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              (r) converts to ®
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              (tm) converts to ™
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              (sm) converts to ℠
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              1/2 converts to ½
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              1/4 converts to ¼
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              3/4 converts to ¾
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              +/- converts to ±
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              != converts to ≠
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              &lt;&lt; converts to «
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              &gt;&gt; converts to »
            </p>
            <p class="rounded-md bg-primary px-2.5 py-1">
              2*3 converts to 2×3
            </p>
            <p class="bg-primary px-2.5 py-1">^2 converts to ²</p>
            <p class="bg-primary px-2.5 py-1">^3 converts to ³</p>
          </div>

          <div class="grid gap-2 text-sm sm:text-base">
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              # to ####### convert to h1 to h6
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              == your word == convert to
              <span class="rounded-md bg-yellow-400 px-2 py-0.5 text-black"
                >highlighted</span
              >
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              * , - or + converts to a bullet list
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              &gt; converts to BlockQuote
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              ``` or ~~~~ converts to CodeBlock
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              --- or ___ converts to a Horizontal Line
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              ***word*** or ___word___ = <b>word</b>
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              *word* or _word_ = <i>word</i>
            </p>
            <p
              class="rounded-md bg-primary px-2.5 py-1 text-center text-white"
            >
              ~~word~~ = <s>word</s>
            </p>
          </div>
        </div>
      </div>
    </div>
  </Dialog.Content>
</Dialog.Root>