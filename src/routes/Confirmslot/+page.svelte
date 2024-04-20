<script>
    import axios from 'axios';


    let slotNumber = '';
    let carNumber = '';
    let date = '';
    let startTime = '';
    let endTime = '';
    let message = '';

    const handleSubmit = async () => {
        try {
            const response = await axios.post('http://localhost:9000/api/Parking/newslot', {
                carno: carNumber,
                slotno: slotNumber,
                stime: startTime,
                etime: endTime
            });

            console.log(response);
            const data = response.data;

            message = data.msg;
        } catch (error) {
            console.error('Error submitting form:', error);
            message = 'An error occurred while submitting the form.';
        }
    };
 
</script>

<section class="py-20 lg:py-22 flex flex-col gap-24" id="projects">
    <div class="flex flex-col gap-2 text-center">
        <h6 class="text-large sm:text-xl md:text-2xl">No need to wait! Click to confirm your space</h6>
        <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
            Your parking slot is ready
        </h3>
        <div class="flex justify-center mt-16">
            <div class="w-full lg:max-w-lg">
                <form on:submit|preventDefault={handleSubmit} class="bg-white shadow-md rounded-lg px-8 pt-6 pb-8 flex flex-col items-center">

                    <h1 class="text-3xl text-center text-gray-900 font-bold mb-4">Confirm your parking area</h1>
                    <div class="flex flex-col gap-4 items-center">
                        <label class="label">
                            <input bind:value={slotNumber} class="input border-black rounded-md text-black" type="text" placeholder="Enter your slot number." />
                        </label>
                    
                        <label class="label">
                            <input bind:value={carNumber} class="input border-black rounded-md text-black" type="text" placeholder="Enter your car number" />
                        </label>
                        <div class="flex flex-row gap-4 items-center">
                            <label class="label flex flex-col items-start">
                                <span class="text-black">Start time (In hour)</span>
                                <input bind:value={startTime} class="input border-black rounded-md mt-1  text-black" type="number" />
                            </label>
                            <label class="label flex flex-col items-start">
                                <span class="text-black">End time (In hour)</span>
                                <input bind:value={endTime} class="input border-black rounded-md mt-1  text-black" type="number" />
                            </label>
                        </div>
                    
                        <button type="submit" class="btn border-black rounded-md px-6 py-3 bg-gray-900 text-white font-bold text-lg">Proceed to pay</button>

                    </div>
                    
                </form>
                {#if message}
                    <p class="text-center text-xl mt-4">{message}</p>
                {/if}
            </div>
        </div>
    </div>
</section>

