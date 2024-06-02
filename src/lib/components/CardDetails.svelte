<script lang="ts">
  import MarkDownLegend from "$lib/components/MarkDownLegend.svelte";

  import { Github } from "lucide-svelte";
  import { Button } from "$lib/components/ui/button/index.js";
</script>
  
<div>
  <div class="mx-auto -mt-1 flex w-[22rem] justify-between md:mx-0 md:w-full">
    <a
    href="https://github.com/rezajaber"
    target="_blank"
    rel="noopener noreferrer"
    >
      <Button>
        <Github class="mr-1.5 h-5 w-5" />
        GitHub
      </Button>
    </a>

    <MarkDownLegend />
  </div>
</div>
  