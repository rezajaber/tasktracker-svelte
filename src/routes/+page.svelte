<script lang="ts">
  import SearchBar from "$lib/components/SearchBar.svelte";
  import CardDetails from "$lib/components/CardDetails.svelte";
  import Card from "$lib/components/Card.svelte";
  
  const cards = [
    { priorityColor: "text-red-500", cardCategory: "Cyber Security", cardTitle: "Hack The Box", cardContent: "Explore the latest trends in cybersecurity and learn how to protect your systems effectively.", cardDate: "22. September 2024" },
    { priorityColor: "text-blue-500", cardCategory: "Data Analysis", cardTitle: "Do not miss the Data", cardContent:"Deep dive into data analysis techniques that can transform your business insights.", cardDate: "30. October 2024" },
    { priorityColor: "text-green-500", cardCategory: "Renewable Energy", cardTitle: "Tesla or Xiaomi", cardContent: "Renewable energy solutions are becoming more affordable and accessible, driving sustainability.", cardDate: "15. November 2024" },
    { priorityColor: "text-yellow-500", cardCategory: "Digital Marketing", cardTitle: "Zahlungswerk to the Top", cardContent: "Understanding the digital marketing landscape is crucial for any modern business strategy.", cardDate: "05. December 2024" },
    { priorityColor: "text-purple-500", cardCategory: "AI Development", cardTitle: "ChatGPT - Dangerous?", cardContent: "Artificial intelligence continues to evolve, offering new possibilities in various sectors. Artificial intelligence continues to evolve, offering new possibilities in various sectors", cardDate: "10. January 2025" },
    { priorityColor: "text-red-500", cardCategory: "Cyber Security", cardTitle: "Hack The Box", cardContent: "Explore the latest trends in cybersecurity and learn how to protect your systems effectively.", cardDate: "22. September 2024" },
    { priorityColor: "text-blue-500", cardCategory: "Data Analysis", cardTitle: "Do not miss the Data", cardContent:"Deep dive into data analysis techniques that can transform your business insights.", cardDate: "30. October 2024" },
    { priorityColor: "text-green-500", cardCategory: "Renewable Energy", cardTitle: "Tesla or Xiaomi", cardContent: "Renewable energy solutions are becoming more affordable and accessible, driving sustainability.", cardDate: "15. November 2024" },
    { priorityColor: "text-yellow-500", cardCategory: "Digital Marketing", cardTitle: "Zahlungswerk to the Top", cardContent: "Understanding the digital marketing landscape is crucial for any modern business strategy.", cardDate: "05. December 2024" },
  ];
</script>
  
<div class="grid h-screen place-content-center place-items-center">
  <div class="mb-6 flex w-full flex-col gap-2">
    <SearchBar />
    <CardDetails />
  </div>

  <div class="overlay relative h-[560px] overflow-hidden rounded-lg">
    <div class="no-scrollbar grid h-full grid-cols-3 gap-5 overflow-y-scroll p-2">
      {#each cards as card}
        <Card  
          priorityColor={card.priorityColor} 
          cardCategory={card.cardCategory} 
          cardTitle={card.cardTitle} 
          cardContent={card.cardContent} 
          cardDate={card.cardDate}  />
      {/each}
    </div>

    <div class="lg:grid-cols-4 grid sm:grid-cols-3 grid-cols-2"></div>
    <div class="hover:opacity-75 opacity-50 hover:scale-150 scale-125"></div>
  </div>
</div>
  
<style>
  .overlay::before {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 40px;
    background: linear-gradient(to bottom, rgba(255, 255, 255, 0), rgba(255, 255, 255, 1));
    pointer-events: none;
  }
</style>
  