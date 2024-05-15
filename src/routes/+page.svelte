<script lang="ts">
    import SearchBar from "$lib/components/SearchBar.svelte";
    import CardDetails from "$lib/components/CardDetails.svelte";
    import Card from "$lib/components/Card.svelte";
  
    const cards = [
  {
    priorityColor: "text-red-500",
    cardCategory: "Cyber Security",
    cardTitle: "Hack The Box",
    cardContent:
      "Explore the latest trends in cybersecurity and learn how to protect your systems effectively.",
    cardDate: "22. September 2024",
  },
  {
    priorityColor: "text-blue-500",
    cardCategory: "Data Analysis",
    cardTitle: "Do not miss the Data",
    cardContent:
      "Deep dive into data analysis techniques that can transform your business insights.",
    cardDate: "30. October 2024",
  },
  {
    priorityColor: "text-green-500",
    cardCategory: "Renewable Energy",
    cardTitle: "Tesla or Xiaomi",
    cardContent:
      "Renewable energy solutions are becoming more affordable and accessible, driving sustainability.",
    cardDate: "15. November 2024",
  },
  {
    priorityColor: "text-yellow-500",
    cardCategory: "Digital Marketing",
    cardTitle: "Zahlungswerk to the Top",
    cardContent:
      "Understanding the digital marketing landscape is crucial for any modern business strategy.",
    cardDate: "05. December 2024",
  },
  {
    priorityColor: "text-purple-500",
    cardCategory: "AI Development",
    cardTitle: "ChatGPT - Dangerous?",
    cardContent:
      "Artificial intelligence continues to evolve, offering new possibilities in various sectors.",
    cardDate: "10. January 2025",
  },

  {
    priorityColor: "text-orange-500",
    cardCategory: "Healthcare Innovation",
    cardTitle: "AI-Doctors rule the world",
    cardContent:
      "Innovative healthcare technologies are revolutionizing patient care worldwide.",
    cardDate: "25. February 2025",
  },
  {
    priorityColor: "text-pink-500",
    cardCategory: "Education Technology",
    cardTitle: "New IPad-OS helps student",
    cardContent:
      "The impact of technology on education is profound, shaping the future of learning.",
    cardDate: "20. March 2025",
  },
  {
    priorityColor: "text-gray-500",
    cardCategory: "Industry 4.0",
    cardTitle: "Xiaomi Robots",
    cardContent:
      "The fourth industrial revolution brings smart technology to manufacturing and production.",
    cardDate: "15. April 2025",
  },
  {
    priorityColor: "text-indigo-500",
    cardCategory: "Blockchain",
    cardTitle: "Bitcoin over Etherum Bitcoin over EtherumBitcoin over Etherum",
    cardContent:
      "Blockchain technology promises enhanced security and transparency in digital transactions. Blockchain technology promises enhanced security and transparency in digital transactions.",
    cardDate: "05. May 2025",
  },
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
    </div>
  </div>
  
  <style>
    .overlay::before {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      height: 50px;
      background: linear-gradient(to bottom, rgba(255, 255, 255, 0), rgba(255, 255, 255, 1));
      pointer-events: none;
    }
  </style>
  