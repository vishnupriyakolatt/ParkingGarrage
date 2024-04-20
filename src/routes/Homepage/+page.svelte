<script>
    import { navigate } from 'svelte-routing';
  </script>
    
    <main class="flex flex-col flex-1 p-4">
    <section id="introPage" class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14">
      <div class="relative shadow-2xl grid place-items-center">
        <img src="https://images.pexels.com/photos/2612855/pexels-photo-2612855.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" alt="Cover Image" />
      </div>
      <div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
        <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
          Hi! I'm <span class="poppin">here</span> to give
          <br />a <span class="poppins">slot for you</span>
        </h2>
        <a href='/Bookslot'  class='button'>Click here to Book your slot</a>
      </div>
    </section>
    </main>
    
    <style>
    .label {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
    }
    .button {
      padding: 10px 5px;
      background-color: #930aee;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 26px;
      font-weight: bold;
      width: 330px;
      font-family: 'Times New Roman', Times, serif;
    }
    
    .input {
      width: 100%;
      padding: 0.5rem;
      border: 1px solid #000;
    }
    
    .btn {
      cursor: pointer;
    }
    </style>