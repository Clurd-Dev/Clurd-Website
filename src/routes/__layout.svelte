<script>
    import { onMount } from 'svelte';
    import 'bootstrap/dist/css/bootstrap.min.css';
    // Import the functions you need from the SDKs you need
    import { initializeApp } from "firebase/app";
    import { getAnalytics } from "firebase/analytics";
    // TODO: Add SDKs for Firebase products that you want to use
    // https://firebase.google.com/docs/web/setup#available-libraries

    // Your web app's Firebase configuration
    // For Firebase JS SDK v7.20.0 and later, measurementId is optional
    const firebaseConfig = {
      apiKey: "AIzaSyCxQqoX554qP5TwLEoG5P680_mpXnapvHE",
      authDomain: "clurd-c8af6.firebaseapp.com",
      projectId: "clurd-c8af6",
      storageBucket: "clurd-c8af6.appspot.com",
      messagingSenderId: "962202455723",
      appId: "1:962202455723:web:31732c666d33b827c531ee",
      measurementId: "G-BCD297KC1S"
    };

    // Initialize Firebase
    const app = initializeApp(firebaseConfig);
    const analytics = getAnalytics(app);
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
            <a class="nav-link" href="/getting">Getting started</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/download">Download</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="" on:click={() => window.open("https://github.com/Clurd-Dev")}>Source code</a>
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
<br/>
<br/>
<footer class="bg-light text-center text-lg-start">
  <!-- Copyright -->
  <div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2);">
    © 2022 Copyright:
    <a class="text-dark" href="/">Clurd</a>
    <p>Source code available <a href="https://github.com/Clurd-Dev">here</a></p>
  </div>
  <!-- Copyright -->
</footer>
