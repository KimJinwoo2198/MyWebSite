<script lang="ts">
  export let title = 'Kim Jinwoo';
  export let google_analytics = 'G-JEHCBZEX1R';
  export let description = "Hi! I'm KimJinwoo, and I build and make cool stuffs";
  // export let image = 'https://paulkim.me/card.png';
  
  import { onMount } from 'svelte';
  
  onMount(() => {
    const script = document.createElement('script');
    script.innerHTML = `
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', '${google_analytics}', { 'cookie_flags': 'SameSite=None;Secure' });
    `;
    document.head.appendChild(script);
  });
</script>

<svelte:head>
  <title>{title}</title>
  <meta name="description" content={description}/>
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:site" content="kimjinwoo.me" />
  <meta name="twitter:title" content={title} />
  <meta name="twitter:description" content={description} />
  <!-- <meta name="twitter:image" content={image} /> -->
  <meta property="og:title" content={title} />
  <meta property="og:description" content={description} />
  <!-- <meta property="og:image" content={image} /> -->

  <script async src="https://www.googletagmanager.com/gtag/js?id={google_analytics}&cookieFlags=SameSite=None;Secure"></script>

  <link rel="icon" href="https://kimjinwoo.me/favicon.ico" type="image/x-icon"/>
</svelte:head>