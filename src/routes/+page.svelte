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

<body class="  h-full w-full">
    <!-- -------------------------Footer---------------------------- -->
    <footer id="Taskbar" class=" flex items-center h-10 fixed bottom-0 w-full bg-gray-300 dark:bg-gray-900">
        <div id="Main_btns">
            <button id="ReactorBtn" aria-label="ReactorBtn" class="relative left-[5px] cursor-pointer pr-1 b h-full border-r-2">
                <svg width="30px" height="30px" viewBox="0 0 310 316"  xmlns="http://www.w3.org/2000/svg">
                    <path d="M238.503 7C244.579 7 249.817 11.2031 251.17 17.0742L251.289 17.6475L302.08 293.647C303.55 301.635 297.417 309 289.295 309H20.168C12.0727 309 5.94626 301.681 7.37109 293.712L56.7256 17.7119L56.8418 17.1357C58.1717 11.2355 63.4222 7 69.5225 7H238.503Z" class="fill-white dark:fill-gray-800 stroke-black dark:stroke-white"  stroke-width="16"/>
                </svg>
            </button>
            <button id="FileManger" aria-label="FileManger" class="relative top-[6px]  cursor-pointer">
                <svg width="40px" height="40px" viewBox="0 0 24 24" class="fill-white dark:fill-gray-800  stroke-black dark:stroke-white"  xmlns="http://www.w3.org/2000/svg">
                    <path d="M3 8.2C3 7.07989 3 6.51984 3.21799 6.09202C3.40973 5.71569 3.71569 5.40973 4.09202 5.21799C4.51984 5 5.0799 5 6.2 5H9.67452C10.1637 5 10.4083 5 10.6385 5.05526C10.8425 5.10425 11.0376 5.18506 11.2166 5.29472C11.4184 5.4184 11.5914 5.59135 11.9373 5.93726L12.0627 6.06274C12.4086 6.40865 12.5816 6.5816 12.7834 6.70528C12.9624 6.81494 13.1575 6.89575 13.3615 6.94474C13.5917 7 13.8363 7 14.3255 7H17.8C18.9201 7 19.4802 7 19.908 7.21799C20.2843 7.40973 20.5903 7.71569 20.782 8.09202C21 8.51984 21 9.0799 21 10.2V15.8C21 16.9201 21 17.4802 20.782 17.908C20.5903 18.2843 20.2843 18.5903 19.908 18.782C19.4802 19 18.9201 19 17.8 19H6.2C5.07989 19 4.51984 19 4.09202 18.782C3.71569 18.5903 3.40973 18.2843 3.21799 17.908C3 17.4802 3 16.9201 3 15.8V8.2Z"  stroke-width="1" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </button>
        </div>
        <h1 id="date_and_time" class=" absolute right-[5px] text-2xl text-black dark:text-white">date</h1>
    </footer>
</body>
