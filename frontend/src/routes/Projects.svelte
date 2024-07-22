<script>
    import { onMount } from 'svelte';
    import ProjectCard from '../components/ProjectCard.svelte';
  
    let projects = [
      {
        title: "ARC Prize 2024",
        description: "Create an AI capable of solving reasoning tasks it has never seen before",
        image: "/projects/arcprice.png",
        link: "https://www.kaggle.com/competitions/arc-prize-2024"
      },
      {
        title: "ISIC 2024 - Skin Cancer Detection",
        description: "Identify cancers among skin lesions cropped from 3D total body photographs",
        image: "/projects/skincancer.png",
        link: "https://www.kaggle.com/competitions/isic-2024-challenge"
      },
      {
        title: "Anguliyam HireHelper.AI",
        description: "AI-powered hiring assistant",
        image: "/projects/hirehelper.png",
        link: "https://medium.com/@hariharanithin/hire-helper-ai-f78495819c3b"
      }
    ];
  
    onMount(() => {
      document.body.style.backgroundColor = '#f0f0f0';
    });
  </script>
  
  <main>
    <div class="container">
      <h1>Projects</h1>
      <div class="projects">
        {#each projects as project}
          <ProjectCard {project} />
        {/each}
      </div>
    </div>
  </main>
  
  <style>

    
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }
  
    h1 {
      text-align: center;
      font-size: 3em;
      margin-bottom: 40px;
      color: #333;
      text-transform: uppercase;
      letter-spacing: 2px;
      animation: fadeIn 1.5s ease-in-out;
    }
  
    .projects {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
    }
  
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>