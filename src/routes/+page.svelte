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

<body class="h-full w-full">
    <!-- -------------------------Footer---------------------------- -->
    <footer id="Taskbar" class=" flex items-center md:h-16 absolute bottom-0 w-full bg-gray-900">



        <h1 id="date_and_time" class=" absolute right-[5px] text-2xl text-white">date</h1>
    </footer>
</body>
