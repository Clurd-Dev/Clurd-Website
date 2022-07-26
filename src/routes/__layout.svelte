<script>
    import { onMount } from 'svelte';
    import 'bootstrap/dist/css/bootstrap.min.css';
    onMount(async() => {
        const module = await import('bootstrap/dist/js/bootstrap.bundle.js');
    });
</script>

<nav class="navbar navbar-expand-lg bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="/">Clurd.NET</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link" href="#">Getting started</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Download</a>
          </li>
          <li class="nav-item">
            <a class="nav-link">Source code</a>
          </li>
        </ul>
    
      </div>
    </div>
  </nav>
  <br/>
  <br/>
<main>
   <slot>

</slot> 
</main>
