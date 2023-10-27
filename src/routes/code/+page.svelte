<script lang="ts">
    let enteredCode: number[] = [];

    function pressButton(number: number) {
        if (enteredCode.length >= 5) {
            return;
        }

        enteredCode.push(number);
    }
</script>

<div class="w-screen h-screen flex flex-col justify-center items-center gap-6">
    <div>
        <p class="font-semibold text-xl text-primary-600">Enter your order code</p>

        <div class="flex gap-2 justify-center items-center mt-3">
            {#each Array(5) as _, index}
                <div class="relative text-primary w-6">
                    <p class="text-2xl {enteredCode[index] === undefined ? 'invisible' : ''}">{enteredCode[index] !== undefined ? enteredCode[index] : "0"}</p>

                    {#if enteredCode[index] === undefined}
                        <div class="absolute bottom-0 w-full h-[2px] bg-[rgb(227,227,227)]" />
                    {/if}
                </div>
            {/each}
        </div>
    </div>

    <div class="w-full full flex flex-col items-center justify-center gap-2 children:flex children:gap-2">
        {#each Array(2) as _, row}
            <div class="w-full flex gap-2 justify-center items-center">
                {#each Array(5) as _, number}
                    <button
                        on:click={() => {
                            pressButton(row == 1 ? number + 5 : number);
                        }}
                        class="h-full rounded-lg bg-brand-600 text-black py-1 px-1 aspect-square w-auto text-3xl">{row == 1 ? number + 5 : number}</button
                    >
                {/each}
            </div>
        {/each}
    </div>
</div>
