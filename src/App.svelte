<script>
    import cat from "./lib/assets/cat.jpg"

    const expresiones = [
        "No me hagas eso, por favor.",
        "¿Qué estás haciendo? Mejor para ya.",
        "Vas a terminar enfadándome, eh.",
        "¿En serio tienes que hacer eso?",
        "¿por qué sigues así?",
        "No jodas, deja de hacerlo.",
        "Eso no está cool, para un poco.",
        "No te pases, en serio.",
        "Me estás sacando de quicio",
        "Para con eso, ¿vale?"
        ];

    let text = ""

    let noBttn;
    let perdon = false;

    function MoveBttn() {
        noBttn.style.position = "absolute";
        noBttn.style.top = Math.floor(Math.random()*window.innerHeight*0.9)+"px";
        noBttn.style.left = Math.floor(Math.random()*window.window.innerWidth*0.9)+"px";
        text = expresiones[Math.floor(Math.random() * expresiones.length)].toLowerCase();
    }

</script>

<div class="w-screen h-screen">
    {#if !perdon}
    <div class="py-4 h-full w-full bg-[#4EF5F2] flex flex-col gap-3 items-center">
        <h1 class="text-7xl font-bold text-white">Lo siento Ani, me perdonas? 😭</h1>
        <h1 class="text-4xl text-white">{text}</h1>
        <div class="flex flex-row items-center gap-2 justify-center">
            <button on:click={() => perdon = true} class="text-white bg-black w-24 text-xl rounded-lg">Si</button>
            <button bind:this={noBttn} on:mouseenter={MoveBttn} class="text-black text-xl bg-red-500 w-24 rounded-lg">No</button>
        </div>
    </div>
    {:else}
    <div class="py-4 h-full w-full bg-purple-400 flex flex-col items-center">
        <h1 class="text-7xl font-bold text-white">GRACIAS TE AMO</h1>
        <img alt="" src={cat} class="h-[90%]"/>
    </div>
    {/if}
</div>