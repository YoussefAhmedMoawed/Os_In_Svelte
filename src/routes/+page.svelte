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
        <footer id="Taskbar" class="  flex items-center h-10 absolute bottom-0 w-full bg-gray-300 dark:bg-gray-900">

            <div id="Main_btns">
                <button id="ReactorBtn" class="relative left-[5px] top-[3px] cursor-pointer">
                    <img src="ReactorIcon.svg" alt="reactor" class="w-[30px] h-[30px]">
                </button>   
                <button id="FileManger" class="relative left-[5px] top-[5px] cursor-pointer">
                    <img src="/FileManger.svg" alt="FileManger" class="w-[30px] h-[30px]">
                </button>
            </div>

            <h1 id="date_and_time" class=" absolute right-[5px] text-2xl text-black dark:text-white">date</h1>

        </footer>
</body>
