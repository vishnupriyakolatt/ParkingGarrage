<script>
    import { onMount } from "svelte";
    import axios from 'axios';
import {goto} from '$app/navigation'

    let email = '';
    let carNumber = '';
    let message = '';

    const handleSubmit = async () => {
        try {
            const response = await axios.post('http://localhost:9000/api/Parking/addslot', {
                email: email,
                carno: carNumber
            }, {
                headers: {
                    'Content-Type': 'application/json'
                }
            });

            console.log(response);
            const data = response.data;
            console.log(data);

            message = data.msg;

          
            goto('/Confirmslot');
        } catch (error) {
            console.error('Error submitting form:', error);
            message = 'An error occurred while submitting the form.';
        }
    };

    // onMount(() => {
    //     handleSubmit()
    // });
</script>
  
<section class="py-20 lg:py-32 flex flex-col gap-24" id="projects">
    <div class="flex flex-col gap-2 text-center">
      <h6 class="text-large sm:text-xl md:text-2xl">Don't waste your time anymore.</h6>
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
        To find a parking slot!
      </h3>
      <div class="flex justify-center mt-16">
        <div class="w-full lg:max-w-lg">
          <form on:submit|preventDefault="{handleSubmit}" class="bg-white shadow-md rounded-lg px-8 pt-6 pb-8 flex flex-col items-center">
            <h1 class="text-3xl text-center text-gray-900 font-bold mb-4">Book Your Parking Area</h1>

            <div class="flex flex-col gap-4">
              <label class="label">
                <input bind:value={email} class="input border-black rounded-md text-black" type="email"  placeholder="Enter your email" />
              </label>

              <label class="label">
                <input bind:value={carNumber} class="input border-black rounded-md text-black" type="text" placeholder="Enter your car number" />
              </label>
              <button type="submit" class="btn border-black rounded-md px-6 py-3 bg-gray-900 text-white font-bold text-lg">Submit</button>
            </div>
          </form>
          {#if message}
            <p class="text-center text-xl mt-4">{message}</p>
          {/if}
        </div>
      </div>
    </div>
  </section>