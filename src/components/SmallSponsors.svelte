<script>
  import EmblaCarousel from "embla-carousel";
  import AutoScroll from "embla-carousel-auto-scroll";
  import { onMount } from "svelte";

  const sponsors = [
    {
      name: "Creating Coding Careers",
      url: "https://cccareers.org/?utm_source=coolify.io",
      imageUrl: "https://github.com/cccareers.png",
      width: 45,
      height: 45,
    },
    {
      name: "Crypto Jobs List",
      url: "https://cryptojobslist.com/?utm_source=coolify.io",
      imageUrl: "https://github.com/cryptojobslist.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "SerpAPI",
      url: "https://serpapi.com/?utm_source=coolify.io",
      imageUrl: "https://github.com/serpapi.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "typebot",
      url: "https://typebot.io/?utm_source=coolify.io",
      imageUrl:
        "https://cdn.bsky.app/img/avatar/plain/did:plc:gwxcta3pccyim4z5vuultdqx/bafkreig23hci7e2qpdxicsshnuzujbcbcgmydxhbybkewszdezhdodv42m@jpeg",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "360Creators",
      url: "https://360creators.com/?utm_source=coolify.io",
      imageUrl:
        "https://opencollective-production.s3.us-west-1.amazonaws.com/account-avatar/503e0953-bff7-4296-b4cc-5e36d40eecc0/icon-360creators.png",
      width: 45,
      height: 45,
    },
    {
      name: "Cap-go",
      url: "https://capgo.app/?utm_source=coolify.io",
      imageUrl: "https://github.com/cap-go.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Best for Android",
      url: "https://bestforandroid.com/?utm_source=coolify.io",
      imageUrl: "https://github.com/bestforandroid.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Startup Fame",
      url: "https://startupfa.me?utm_source=coolify.io",
      imageUrl: "https://github.com/startupfame.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Cirun",
      url: "https://cirun.io/?utm_source=coolify.io",
      imageUrl: "/images/cirun-logo.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Alfred Nutile",
      url: "https://www.youtube.com/@AlfredNutile?utm_source=coolify.io",
      imageUrl: "https://github.com/alnutile.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Become a sponsor",
      url: "https://github.com/sponsors/coollabsio/sponsorships?tier_id=61570&preview=false",
      imageUrl: "question",
      width: 45,
      height: 45,
      isSpecial: true,
    },
    {
      name: "DartNode",
      url: "https://dartnode.com/?utm_source=coolify.io",
      imageUrl: "https://github.com/dartnode.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Dry Software",
      url: "https://dry.software/?utm_source=coolify.io",
      imageUrl: "https://github.com/dry-software.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "jyc.dev",
      url: "https://bsky.app/profile/jyc.dev",
      imageUrl: "https://github.com/jycouet.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "BitLaunch",
      url: "https://bitlaunch.io/?utm_source=coolify.io",
      imageUrl: "https://github.com/bitlaunchio.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Internet Garden",
      url: "https://internetgarden.co/?utm_source=coolify.io",
      imageUrl: "/images/internetgarden.ico",
      width: 45,
      height: 45,
      customStyle: "rounded",
      isPublicImage: true,
    },
    {
      name: "Jonas Jaeger",
      url: "https://jonasjaeger.com?utm_source=coolify.io",
      imageUrl: "https://github.com/toxin20.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "TheRealJP",
      url: "https://github.com/therealjp?utm_source=coolify.io",
      imageUrl: "https://github.com/therealjp.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Evercam",
      url: "https://evercam.io/?utm_source=coolify.io",
      imageUrl: "https://github.com/evercam.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Formbricks",
      url: "https://formbricks.com/?utm_source=coolify.io",
      imageUrl: "https://github.com/formbricks.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Web3 Jobs",
      url: "https://web3.career/?utm_source=coolify.io",
      imageUrl: "/images/web3jobs.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "LinkDr",
      url: "https://linkdr.com?utm_source=coolify.io",
      imageUrl: "https://github.com/LLM-Inc.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Fider",
      url: "https://fider.io/?utm_source=coolify.io",
      imageUrl: "https://github.com/getfider.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Reshot",
      url: "https://www.reshot.ai/?utm_source=coolify.io",
      imageUrl: "/images/reshotai.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Devhuset",
      url: "https://devhuset.no?utm_source=coolify.io",
      imageUrl: "https://github.com/devhuset.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "RunPod",
      url: "https://www.runpod.io/?utm_source=coolify.io",
      imageUrl: "/images/runpod.svg",
      width: 45,
      height: 45,
      isSpecial: true,
    },
    {
      name: "Gravity Wiz",
      url: "http://gravitywiz.com/?utm_source=coolify.io",
      imageUrl: "https://github.com/gravitywiz.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Flint-company",
      url: "https://www.flint.sh/en/home?utm_source=coolify.io",
      imageUrl: "https://github.com/Flint-company.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Thompson Edolo",
      url: "https://x.com/mrsmith9ja?utm_source=coolify.io",
      imageUrl: "https://github.com/verygreenboi.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "UXWizz",
      url: "https://www.uxwizz.com/?utm_source=coolify.io",
      imageUrl: "https://github.com/UXWizz.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Codext",
      url: "https://codext.link/coolify-io?utm_source=coolify.io",
      imageUrl: "/images/codext.jpg",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Lightspeed.run",
      url: "https://lightspeed.run/?utm_source=coolify.io",
      imageUrl: "https://github.com/lightspeedrun.png",
      width: 45,
      height: 45,
      customStyle: "rounded bg-white",
    },
    {
      name: "Younes Barrad",
      url: "https://barrad.me/?utm_source=coolify.io",
      imageUrl: "https://github.com/Flowko.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Corentin Clichy",
      url: "https://github.com/corentinclichy",
      imageUrl: "https://github.com/corentinclichy.png",
      width: 45,
      height: 45,
    },
    {
      name: "Niklas Lausch",
      url: "https://github.com/Niki2k1",
      imageUrl: "https://github.com/Niki2k1.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Pixel Infinito",
      url: "https://pixel.ao/?utm_source=coolify.io",
      imageUrl: "https://github.com/pixelinfinito.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Tyler Whitesides",
      url: "https://github.com/whitesidest",
      imageUrl: "https://avatars.githubusercontent.com/u/12365916?s=52&v=4",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "NiftyCo",
      url: "https://github.com/aniftyco",
      imageUrl: "https://github.com/aniftyco.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Imre Ujlaki",
      url: "https://github.com/iujlaki",
      imageUrl: "https://github.com/iujlaki.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Ilias Ism",
      url: "https://il.ly/?utm_source=coolify.io",
      imageUrl: "https://github.com/Illyism.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Paweł Pierścionek",
      url: "https://github.com/urtho",
      imageUrl: "https://github.com/urtho.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
    {
      name: "Michael Mazurczak",
      url: "https://github.com/monocursive",
      imageUrl: "https://github.com/monocursive.png",
      width: 45,
      height: 45,
      customStyle: "rounded",
    },
  ];
  function shuffleArray(array) {
    const shuffled = [...array];
    for (let i = shuffled.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
    }
    return shuffled;
  }

  const smallSponsors = shuffleArray(sponsors);
  let emblaSmallNode;

  onMount(() => {
    const smallOptions = {
      loop: true,
      containScroll: "trimSnaps",
      slidesToScroll: 1,
      skipSnaps: false,
      watchDrag: true,
    };

    const smallAutoScrollOptions = {
      speed: 1,
      stopOnInteraction: false,
      stopOnMouseEnter: true,
      playOnInit: false,
    };

    const emblaSmallApi = EmblaCarousel(emblaSmallNode, smallOptions, [
      AutoScroll(smallAutoScrollOptions),
    ]);

    setTimeout(() => {
      emblaSmallApi.plugins().autoScroll.play();
    }, 300);

    return () => {
      emblaSmallApi.destroy();
    };
  });

  function getImagePath(imageUrl) {
    if (imageUrl.startsWith("http")) {
      return imageUrl;
    }
    return imageUrl;
  }
</script>

<div class="py-4">
  <div class="flex flex-col items-center gap-2">
    <div bind:this={emblaSmallNode} class="embla-small">
      <div class="embla-small__container">
        {#each smallSponsors as sponsor}
          <div class="embla-small__slide">
            {#if sponsor.isSpecial && sponsor.imageUrl === "question"}
              <a
                class="w-12 h-12 border border-warning font-bold border-dashed hover:bg-warning hover:text-black flex justify-center text-center items-center text-3xl text-white animate-pulse plausible-event-name=small-sponsor-clicks"
                href={sponsor.url}
              >
                ?!
              </a>
            {:else if sponsor.isSpecial && sponsor.imageUrl === "runpod-svg"}
              <a
                href={sponsor.url}
                class="plausible-event-name=small-sponsor-clicks"
              >
                <svg
                  class="w-11 h-11 fill-[#824edc] bg-white rounded"
                  xmlns="http://www.w3.org/2000/svg"
                  version="1.0"
                  viewBox="0 0 200 200"
                >
                  <g>
                    <path
                      d="M74.5 51.1c-25.4 14.9-27 16-29.6 20.2-1.8 3-1.9 5.3-1.9 32.3 0 21.7.3 29.4 1.3 30.6 1.9 2.5 46.7 27.9 48.5 27.6 1.5-.3 1.7-3.1 2-27.7.2-21.9 0-27.8-1.1-29.5-.8-1.2-9.9-6.8-20.2-12.6-10.3-5.8-19.4-11.5-20.2-12.7-1.8-2.6-.9-5.9 1.8-7.4 1.6-.8 6.3 0 21.8 4C87.8 78.7 98 81 99.6 81c4.4 0 49.9-25.9 49.9-28.4 0-1.6-3.4-2.8-24-8.2-13.2-3.5-25.1-6.3-26.5-6.3-1.4.1-12.4 5.9-24.5 13z"
                    />
                    <path
                      d="m137.2 68.1-3.3 2.1 6.3 3.7c3.5 2 6.3 4.3 6.3 5.1 0 .9-8 6.1-19.4 12.6-10.6 6-20 11.9-20.7 12.9-1.2 1.6-1.4 7.2-1.2 29.4.3 24.8.5 27.6 2 27.9 1.8.3 46.6-25.1 48.6-27.6.9-1.2 1.2-8.8 1.2-30.2s-.3-29-1.2-30.2c-1.6-1.9-12.1-7.8-13.9-7.8-.8 0-2.9 1-4.7 2.1z"
                    />
                  </g>
                </svg>
              </a>
            {:else if sponsor.isPublicImage}
              <a
                href={sponsor.url}
                class="plausible-event-name=small-sponsor-clicks"
              >
                <img
                  class={sponsor.customStyle || ""}
                  src={sponsor.imageUrl}
                  width={sponsor.width || 45}
                  height={sponsor.height || 45}
                  loading="eager"
                  alt={sponsor.name}
                />
              </a>
            {:else}
              <a
                href={sponsor.url}
                class="plausible-event-name=small-sponsor-clicks"
              >
                <img
                  class={sponsor.customStyle || ""}
                  src={getImagePath(sponsor.imageUrl)}
                  width={sponsor.width || 45}
                  height={sponsor.height || 45}
                  loading="eager"
                  alt={sponsor.name}
                />
              </a>
            {/if}
          </div>
        {/each}
      </div>
    </div>
  </div>
  <div class="text-center pt-4">
    <a
      class="text-warning underline text-xs hover:text-white"
      href="https://github.com/sponsors/coollabsio"
    >
      ...and many more...
    </a>
  </div>
</div>

<style>
  .embla-small {
    overflow: hidden;
    max-width: 100%;
    margin: 0 auto;
    position: relative;
  }

  .embla-small__container {
    display: flex;
    backface-visibility: hidden;
    will-change: transform;
    touch-action: pan-y;
  }

  .embla-small__slide {
    flex: 0 0 auto;
    min-width: 0;
    position: relative;
    padding: 0 0.4rem;
    display: flex;
    align-items: center;
    justify-content: center;
    user-select: none;
    -webkit-touch-callout: none;
    -webkit-tap-highlight-color: transparent;
  }

  .rainbow-border {
    position: relative;
    border-radius: 200px;
    padding: 0rem;
  }

  .rainbow-border::before {
    content: "";
    position: absolute;
    top: 6px;
    left: 6px;
    right: 6px;
    bottom: 6px;
    background: conic-gradient(
      #ff2400,
      #e81d1d,
      #e8b71d,
      #e3e81d,
      #1de840,
      #1ddde8,
      #2b1de8,
      #dd00f3,
      #ff2400
    );
    border-radius: 200px;
    z-index: -1;
    animation: rotate 1s linear infinite;
  }

  @keyframes rotate {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }
</style>
