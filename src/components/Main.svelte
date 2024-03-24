<script>
    import Step from "./Step.svelte";
    import { onMount } from 'svelte'; 

    let steps = [
        {
            name: "EdTech Website",
            icon: "fa-solid fa-cart-shopping",
            description:
                "EdTech Website is a SaaS tool to build your own website using Next.js, Supabase and Tailwind. The backend is handled by Supabase and for payment we have integrated Stripe",
        },
        {
            name: "Feeding Paws",
            icon: "fa-solid fa-list-check",
            description:
                "Founder of an animal welfare start-up. We conduct feeding drives for 200+ street animals in India and help them by fostering and adoption drives.",
        },
        {
            name: "World Happiness Predictor",
            icon: "fa-solid fa-diagram-project",
            description:
                "Made for my Python in Business Class.",
        },
    ];

    let benefits = [
        {
            metric: "10x",
            name: "Education",
            description:
                " I have a Bachelors in Computer Science and Engineering from Vellore Institute of Technology and am currently pursuing my Masters in Management from ESSEC Business School. I have deep interest in Data Science, Finance and Business and keep exploring different roles for the same.",
        },
        {
            name: "3+ Years of Experience",
            description:
                "I have worked across different sectors and industries. Currently I am working as a Strategy Project Manager in Amadeus, Nice. Earlier, I have interned at companies such as - Alvarez and Marsal, Tata Consultancy Services and Oracle.",
        },
        {
            name: "Entrepreneurial Spirit",
            description:
                "I have over 2 years of experience in running my own Start-up: Feeding Paws, and am inivoled with multiple small incubators at ESSEC Business School",
        },
    ];
    let darkMode = false;

// Function to toggle dark mode
function toggleDarkMode() {
    darkMode = !darkMode;
    // Save the user's preference in localStorage
    localStorage.setItem('darkMode', darkMode);
}

// Load user's preference for dark mode on component mount
onMount(() => {
    const savedMode = localStorage.getItem('darkMode');
    if (savedMode !== null) {
        darkMode = savedMode === 'true';
    }
});

</script>

<main class="flex flex-col flex-1 p-4" class:dark-mode={darkMode}>
    <!-- Toggle Button for Dark Mode -->
    <button 
        class="absolute top-4 right-4 rounded-full w-12 h-12 bg-gray-200 flex items-center justify-center text-gray-900 dark:bg-gray-800 dark:text-white" 
        on:click={toggleDarkMode}
    >
        {#if darkMode}
            Light
        {:else}
            Dark
        {/if}
    </button>


    <section
        id="introPage"
        class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14"
    >
        <div
            class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
        >
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi! I'm <span class="poppins text-violet-400">Siddhant Vinayak</span> Chanda
                <br />
                <span class="poppins text-violet-400"></span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                I am M2 student at   <span class="text-violet-400">ESSEC Business School</span> and have 
                deep interest in Strategy, Finance and Data Science. Would love to have a coffee chat about how different things work in the world!
            </p>
            <button
                class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950"
            >
                <div
                    class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
                />
                <h4 class="relative z-9">Get in touch &rarr;</h4>
            </button>
        </div>
        <div class="relative shadow-2xl grid place-items-center">
            <img
                src={"images/profile.png"}
                alt="Zetane Engine"
                class="object-cover z-[2] max-h-[70vh]"
            />
        </div>
        <!-- <div  class="flex p-0.5 relative max-w-[700px] w-full mx-auto">
            <div
                class="absolute inset-0 overflow-hidden rounded-md flex items-center justify-center"
            >
                <div
                    class="bg-gradient-to-r absolute inset-[-20px]  from-violet-800 to-indigo-800 specialSpin"
                />
            </div>

            <img
                src={"images/zetane-engine.jpeg"}
                alt="Zetane Engine"
                class="w-full h-full object-cover z-[2]"
            />
        </div> -->
    </section>
    <section class="py-20 lg:py-32 flex flex-col gap-24" id="projects">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-large sm:text-xl md:text-2xl">
                A few of my projects
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                Curious to <span class="poppins text-violet-400">see</span> my profile?
            </h3>
        </div>
        <a
            href="https://www.linkedin.com/in/svchanda"
            target="_blank"
            class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
        >
            <i class="fa-regular fa-circle-play" />
            <p>Check this out</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            <Step step={steps[0]}>
                <p>
                    EdTech Website is a SaaS tool to build your own website using Next.js, Supabase and Tailwind. The backend is handled by Supabase and for payment we have integrated Stripe. <strong
                        class="text-violet-400"
                        >I build the project for my Website Creation Class</strong
                    > and in the future will work on it to make it fully functional.
                </p>
            </Step>
            <Step step={steps[1]}>
                <p>
                    Founder of an animal welfare start-up. We conduct feeding drives for <strong
                        class="text-violet-400"><form action=""></form></strong
                    > 
                    <strong class="text-violet-400"> 200+ street animals</strong
                    >
                    <strong class="text-violet-400">in India</strong> and help them get adopted by awarness campaigns and fostering sessions.
                </p>
            </Step>
            <Step step={steps[2]}>
                <p>
                    World happiness predictor is a Machine Learning <strong class="text-violet-400"
                        >Python model</strong
                    > I build as a project for my 
                    <strong class="text-violet-400">Python for Business Class</strong> at ESSEC Business School. It analyses past 
                    <strong class="text-violet-400">15 year data</strong>
                    to make certain predictions using Linear Regression.
                </p>
            </Step>
        </div>
    </section>
    <section
        id="about"
        class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
    >
        <!-- <div class="z-[-1] bg-violet-950 w-screen left-1/2 -translate-x-1/2 top-0 h-full absolute"> </div> -->
        <div
            class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
        >
            <h6 class="text-large sm:text-xl md:text-2xl">
                Want to know more?
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                A bit <span class="poppins text-violet-400">about</span> me.
            </h3>
        </div>
        <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
            I am . . .
        </p>
        <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
            {#each benefits as benefit, index}
                <!-- <div class="flex flex-col gap-2 mx-auto">
                    <div class="flex items-end gap-4">
                        <p
                            class="poppins text-6xl sm:text-7xl md:text-8xl text-slate-500 font-medium"
                        >
                            {benefit.metric}
                        </p>
                        <p
                            class="text-xl sm:text-2xl md:text-3xl capitalize pb-2"
                        >
                            {benefit.name}
                        </p>
                    </div>
                    <p class="text-center italic">- {benefit.description}</p>
                </div> -->
                <div class="flex gap-6 sm:gap-8">
                    <p
                        class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold"
                    >
                        0{index + 1}
                    </p>
                    <div class="flex flex-col gap-6 sm:gap-8">
                        <h3 class="text-2xl sm:text-3xl md:text-5xl">
                            {benefit.name}
                        </h3>
                        <p>{benefit.description}</p>
                    </div>
                </div>
            {/each}
        </div>
        <h5 class={" text-2xl sm:text-3xl font-semibold text-center poppins "}>
            Siddhant <span class="text-violet-400">vs </span> Others
        </h5>
        <div
            class="flex flex-col overflow-x-scroll gap-10 max-w-[800px] mx-auto w-full"
        >
            <table class="bg-white text-slate-700 rounded text-center">
                <thead class={"border-b border-solid border-slate-200  "}>
                    <tr class="">
                        <th />
                        <th class="whitespace-nowrap p-2 px-4">Candidate #1</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate #2</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate #3</th>
                        <th
                            class="bg-violet-700 text-white whitespace-nowrap p-4 px-8"
                            >Siddhant</th
                        >
                    </tr>
                </thead>
                <tbody>
                    <tr class="border-b border-solid border-slate-200">
                        <td
                            class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                            >Education</td
                        >
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr class="border-b border-solid border-slate-200">
                        <td
                            class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                            >Experience</td
                        >
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr>
                        <td
                            class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                            >Interpersonal Skills</td
                        >
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr class="border-t border-solid border-slate-200">
                        <td
                            class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                            >Critical Thinking</td
                        >
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div class="mx-auto -mt-12 italic sm:hidden opacity-50">
            <p>Scroll to see more &rarr;</p>
        </div>
        <p class="mx-auto">Connect to get in touch to talk about future opportunities!</p>
    </section>
</main>
