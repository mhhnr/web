<script>
  export let project;

  function handleClick() {
    window.open(project.link, '_blank');
  }
</script>

<div class="project-card" on:click={handleClick}>
  <div class="image-container">
    <img src={project.image} alt={project.title} class="project-image">
  </div>
  <div class="project-info">
    <h2>{project.title}</h2>
    <p>{project.description}</p>
  </div>
</div>

<style>
  .project-card {
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transition: all 0.3s ease;
    border: 1px solid #000;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    height: 100%;
  }

  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
    border-color: #000000;
  }

  .image-container {
    width: 100%;
    height: 200px;
    overflow: hidden;
    position: relative;
  }

  .project-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
  }

  .project-card:hover .project-image {
    transform: scale(1.05);
  }

  .image-container::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.3);
    opacity: 0;
    transition: opacity 0.3s ease;
  }

  .project-card:hover .image-container::after {
    opacity: 1;
  }

  .project-info {
    padding: 20px;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  h2 {
    margin: 0 0 10px;
    font-size: 1.5em;
    color: #000000;
  }

  p {
    margin: 0;
    color: #000000;
  }
</style>