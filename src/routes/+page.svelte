<script>
  import './styles.scss'
  import { onMount } from 'svelte';

  import { book, open_book, arrow, emoji, artist, gear, school, brain, oldsites, cs50, battlebot, automsg, devbench, github, linkedin, instagram, twitter, discord, blog } from '$lib/images/images';
  
  import Metatags from '$lib/components/Metatags.svelte';
  
  let emojiNum = 2;
  let currentEmoji = emoji[emojiNum];
  function changeEmoji() {
    emojiNum++
    if (emojiNum >= 7) {
      emojiNum = 0
    }
    currentEmoji = emoji[emojiNum]
  }
  let interval = null;
  function rollEmoji() {
    let iteration = 0;
    
    clearInterval(interval);
    interval = setInterval(() => {
      changeEmoji()
    }, 150);
  }

  let projectsSection;
  let project1;
  let project2;
  let project3;
  let project4;

  // GSAP
  // GSAP
  import { gsap } from "gsap/dist/gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
  import { ScrollSmoother } from "$lib/gsap/src/ScrollSmoother";
  gsap.registerPlugin(ScrollTrigger, ScrollSmoother);

  let smoother;
  let aboutTimeline = gsap.timeline();
  onMount(() => {
    if (window.innerWidth >= 900) { // Only use scrollSmoother if on a large enough page
      smoother = ScrollSmoother.create({
        smooth: 3,
        effects: true,
      });
    }

    gsap.to("#header .line-1", {
      y: "10vh",
      scrollTrigger: {
        trigger: "#header",
        start: "top top",
        end: "bottom top",
        scrub: 1.5,
        ease: "slow(0.7,0.7,false)",
      }
    })
    gsap.to("#header .line-2", {
      y: "10vh",
      scrollTrigger: {
        trigger: "#header",
        start: "top top",
        end: "bottom top",
        scrub: 1,
        ease: "slow(0.7,0.7,false)",
      }
    })
    if (window.innerWidth > 1250) {
      gsap.to(".navbar", {
        y: "25vh",
        scrollTrigger: {
          trigger: "#header",
          start: "top top",
          end: "top+=750 top",
          scrub: true,
        }
      })
    }
    gsap.to("#arrow", {
      y: "2vh",
      scrollTrigger: {
        trigger: "#header",
        start: "top top",
        end: "bottom top",
        scrub: true,
      }
    })

    aboutTimeline.from("#about .section-1", {
      height: 0,
      duration: 1
    }, "<")
    .from("#about .line-1", {
      opacity: 0,
      y: "0.5em",
      duration: 1
    })
    .from("#about .line-1 .highlight", {
      background: "transparent",
      duration: 1.5
    }, "<")
    .from("#about .line-2", {
      opacity: 0,
      y: "0.5em",
      duration: 1
    })
    .from("#about .line-2 .highlight", {
      background: "transparent",
      duration: 1.5
    }, "<")
    .from("#about .line-3", {
      opacity: 0,
      y: "0.5em",
      duration: 1
    })
    .from("#about .line-3 .highlight", {
      background: "transparent",
      scale: 0,
      duration: 1.5
    }, "<")
    .from("#about .section-2", {
      height: 0,
      duration: 1
    }, "<")
    .from("#about .line-4", {
      opacity: 0,
      y: "0.5em",
      duration: 1
    })
    .from("#about .line-5", {
      opacity: 0,
      y: "0.5em",
      duration: 1
    })
    .from("#about .line-5 .highlight", {
      background: "transparent",
      duration: 1.5
    }, "<")
    .to("#about", {
      duration: 1
    })
    .to("#about", {
      clipPath: "polygon(0 50%, 100% 50%, 100% 50%, 0 50%)",
      duration: 1.5,
    })
    .to("#about", {
      duration: 0.5
    })
    .from("#past-sites .small", {
      opacity: 0,
      y: "0.25em",
      duration: 1,
    })
    .from("#past-sites .big", {
      opacity: 0,
      y: "0.25em",
      duration: 1,
    })
    .from("#past-sites .images", {
      scale: 0,
      opacity: 0,
      duration: 1,
    })
    .to("#past-sites .images", {
      scale: 1.1,
      duration: 2
    })
    .from(".old-site", {
      marginRight: "-35vw",
      duration: 2,
    }, "<")
    .to("#about", {
      duration: 0.5
    })

    if (window.innerHeight >= 900) {
      ScrollTrigger.create({
        trigger: "#about-scroll-section",
        animation: aboutTimeline,
        start: "top top",
        end: "+=4000vh",
        scrub: 0.5,
        pin: true,
      })  
    } else {
      ScrollTrigger.create({
        trigger: "#about-scroll-section",
        animation: aboutTimeline,
        start: "top top",
        end: "+=2000vh",
        scrub: true,
        pin: true,
      })  
    }
  })
</script>

<Metatags/>

<nav class="navbar">
  <a href="#" id="title">
    <h2><span>김</span><span>진</span><span>우</span> <span>(</span><span>J</span><span>I</span><span>N</span><span>W</span><span>O</span><span>O</span> <span>K</span><span>I</span><span>M</span><span>)</span></h2>
  </a>
  <div id="socials">
    <a href="https://github.com/KimJinwoo2198" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's Github"><img src={github} alt="github logo"/></a>
    <a href="https://instagram.com/kimjinwoo07" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's Instagram"><img src={instagram} alt="instagram logo"/></a>
    <a href="https://discord.com/users/896570484588703744" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's Discord"><img src={discord} alt="discord logo"/></a>
    <a href="https://linkedin.com/in/kimjinwoo07" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's LinkedIn"><img src={linkedin} alt="linkedin logo"/></a>
    <a href="https://blog.kimjinwoo.me/" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's Blog"><img src={blog} alt="blog logo"/></a>
  </div>
</nav>

<header id="header">
  <h1>
    <span class="line line-1">
      <span class="wrapper innovate-wrapper">
        <span id="stories" class="highlight content">
          <span class="text">Innovate</span>
        </span> 
      </span>
      <span class="wrapper implement-wrapper">
        <span id="stories" class="highlight content">
          <span class="text">Implement</span>
        </span> 
      </span>
      <span class="wrapper inspire-wrapper">
        <span id="stories" class="highlight content">
          <span class="text">Inspire</span>
          <!-- <img src={book} alt="book emoji" class="emoji" aria-hidden="true"/>
          <img src={open_book} alt="open book emoji" class="emoji" aria-hidden="true"/>
          <img src={book} alt="book emoji" class="emoji" aria-hidden="true"/> -->
        </span> 
      </span>
      <!-- <span class="wrapper">
        <span class="content">on the web</span>
      </span> -->
    </span>
    <span class="line line-2">
      <span class="wrapper">
        <span class="content">My World of</span>
      </span>
      <span class="wrapper yours-wrapper">
        <span id="yours" class="highlight content" on:mouseenter={rollEmoji} on:mouseleave={clearInterval(interval)}>
          <span class="text">Programming</span>
          <!-- <img src={currentEmoji} class="emoji" alt="emoji" aria-hidden="true"/> -->
        </span>
      </span>
    </span>
  </h1>
  <div id="arrow">
    <img src={arrow} alt="down arrow"/>
    <img src={arrow} alt="down arrow"/>
  </div>
</header>

<main>
  <div id="about-scroll-section">
    <section id="about">
      <div class="inner">
        <h2>So... who am I?</h2>
        <h3 class="section-1">
          <span class="line line-1">
            I'm a 
            <span class="highlight" style="color: #FDD641;">
              <span class="highlight-content">
                <img src={artist} alt="artist emoji" aria-hidden="true"/>
                Software Engineer
              </span>
            </span>
            ,
          </span>
          <span class="line line-2">
            <span class="highlight" style="color: #CDC4D6;">
              <span class="highlight-content">
                <img src={gear} alt="gear emoji" aria-hidden="true"/>
                Web Developer
              </span>
            </span>
            , and
          </span>
          <span class="line line-3">
            <span class="highlight" style="color: #FFCE7C;">
              <span class="highlight-content">
                <img src={school} alt="school emoji" aria-hidden="true"/>
                Ai Developer
              </span>
            </span>
          </span>
        </h3>
        <h3 class="section-2">
          <span class="line line-4">
            But mostly, I'm a
          </span>
          <span class="line line-5">
            <span class="highlight" style="color: #FF6DC6;">
              <span class="highlight-content">
                <img src={brain} alt="brain emoji" aria-hidden="true"/>
                Problem Solver
              </span>
            </span>
            ...
          </span>
        </h3>
      </div>
    </section>
    <section id="past-sites">
      <h2>
        <span class="small">...and I'm always</span>
        <span class="big">learning</span>
      </h2>
      <div class="images">
        {#each oldsites as site (site.number)}
          <img src={site.image} id={`site${site.number}`} alt={`old site ${site.number}`} class="old-site"/>
        {/each}
      </div>
    </section>
  </div>
  
  <section id="projects" bind:this={projectsSection}>
    <h2>Projects</h2>
    <span aria-hidden="true">Projects</span>
    <div id="scroller">
      <article class="project" bind:this={project2}>
        <a href="https://devbench.kr/" target="_blank" rel="noreferrer" aria-label="go to featured website">
          <img src={devbench} alt="DevBench, A Community for Korean Youth Developers - website screenshot"/>
        </a>
        <a href="https://devbench.kr/" target="_blank" rel="noreferrer" class="project-title">
          <h3>DevBench: A Community for Korean Youth Developers</h3>
        </a>
      </article>
      <article class="project" bind:this={project3}>
        <a href="https://battlebot.kr/" target="_blank" rel="noreferrer" aria-label="go to featured website">
          <img src={battlebot} alt="BattleBot: Manage your Discord Conveniently - website screenshot"/>
        </a>
        <a href="https://battlebot.kr/" target="_blank" rel="noreferrer" class="project-title">
          <h3>BattleBot: Manage your Discord Conveniently</h3>
        </a>
      </article>
      <article class="project" bind:this={project4}>
        <a href="https://automsg.xyz/" target="_blank" rel="noreferrer" aria-label="go to featured website">
          <img src={automsg} alt="Project: Empower at Fulton Science Academy - website screenshot"/>
        </a>
        <a href="https://automsg.xyz/" target="_blank" rel="noreferrer" class="project-title">
          <h3>AutoMSG: Easily Streamlining Marketing Efforts</h3>
        </a>
      </article>
      <!-- <article class="project" bind:this={project1}>
        <a href="https://cs50.paulkim.me/hello_world" target="_blank" rel="noreferrer" aria-label="go to featured website">
          <img src={cs50} alt="CS50 at Fulton Science Academy - website screenshot"/>
        </a>
        <a href="https://cs50.paulkim.me/hello_world" target="_blank" rel="noreferrer" class="project-title">
          <h3>CS50 at Fulton Science Academy</h3>
        </a>
      </article> -->
    </div>
  </section>
  <section id="contact">
    <div id="contact-wrapper">
      <h2>I'd love to work with you</h2>
      <div id="contact-content">
        <div id="contact-info">
          <p>Do you have a wonderful idea and want to make it into reality? <br/> Reach out with a contact form - I'd love to hear from you. </p>
          <div>
            <div class="contact-info-line">
              <h3>Social Media</h3>
              <div class="contact-social-media">
                <a href="https://github.com/kimjinwoo2198" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's Github"><img src={github} alt="github logo"/></a>
                <a href="https://instagram.com/kimjinwoo07" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's Instagram"><img src={instagram} alt="instagram logo"/></a>
                <a href="https://discord.com/users/896570484588703744" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's Discord"><img src={discord} alt="discord logo"/></a>
                <a href="https://www.linkedin.com/in/kimjinwoo07" target="_blank" rel="noreferrer" aria-label="Go to Jinwoo's LinkedIn"><img src={linkedin} alt="linkedin logo"/></a>
              </div>
            </div>
            <div class="contact-info-line">
              <h3>Email</h3>
              <a href="mailto:kimjw2198@gmail.com">hello at kimjinwoo.me</a>
            </div>
            <!-- <div class="contact-info-line">
              <h3>Resume</h3>
              <a href="https://resume.paulkim.me" target="_blank" rel="noreferrer">Not much, but it's honest work.</a>
            </div> -->
            <div class="contact-info-line">
              <h3>Blog</h3>
              <a href="https://blog.kimjinwoo.me/" target="_blank" rel="noreferrer">I write my life!</a>
            </div>
          </div>
        </div>
        <form name="contact-form" acceptCharset="utf-8" action="https://formsubmit.co/kimjw2198@gmail.com" method="POST">
          <fieldset>
            <input type="text" name="name" id="your-name" placeholder="Your Name" required/>
            <input type="email" name="email" id="your-email" placeholder="Your@Email.com" required/>
          </fieldset>
          <textarea name="message" id="message" placeholder="Message" required/>
          <input type="submit" value="Submit"/>
          <input type="hidden" name="_next" value="https://kimjinwoo.me">
        </form>
      </div>
    </div>
  </section>
</main>