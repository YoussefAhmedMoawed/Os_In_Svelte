<script lang="ts">
import {
    onMount
} from 'svelte';
import "../app.css";

onMount(() => {

    function update_clock() {
        const d = new Date();
        const hrs = d.getHours().toString().padStart(2, "0");
        const min = d.getMinutes().toString().padStart(2, "0");
        const sec = d.getSeconds().toString().padStart(2, "0");

        const clockElement = document.getElementById("date_and_time");
        if (clockElement) {
            clockElement.textContent = `${hrs}:${min}:${sec}`;
        }
    }
    update_clock();
    const interval = setInterval(update_clock, 1000);

    return () => clearInterval(interval);

})
</script>

<svelte:head>
    <title>Reactor Os</title>
</svelte:head>

<body class="h-full w-full">
        <!-- -------------------------Footer---------------------------- -->
        <footer id="Taskbar" class=" flex items-center md:h-16 absolute bottom-0 w-full bg-neutral-800">

            <div id="Main_btns">
                <button id="ReactorBtn" aria-label="ReactorBtn" class="absolute left-[5px] cursor-pointer">
                    <svg width="30" height="30" viewBox="0 0 310 316"  xmlns="http://www.w3.org/2000/svg">
                        <path d="M238.503 7C244.579 7 249.817 11.2031 251.17 17.0742L251.289 17.6475L302.08 293.647C303.55 301.635 297.417 309 289.295 309H20.168C12.0727 309 5.94626 301.681 7.37109 293.712L56.7256 17.7119L56.8418 17.1357C58.1717 11.2355 63.4222 7 69.5225 7H238.503Z" fill="gray" stroke="white" stroke-width="14"/>
                    </svg>
                </button>
                <button id="FileManger" class="">
                    <svg width="800px" height="800px" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M0 1H6L9 4H16V14H0V1Z" fill="#000000"/>
                    </svg>
                </button>
	          </div>

            <h1 id="date_and_time" class=" absolute right-[5px] text-2xl text-white">date</h1>

	      </footer>
</body>
