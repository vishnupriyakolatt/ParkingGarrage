<script>
  import "../app.css";
  import Header from '../components/Header.svelte';

  // import Booking from "./bookslot.svelte";



</script>

<div class='relative flex flex-col max-w-[1400px] mx-auto w-full text-sm sm:text-base min-h-screen'>
  <Header />
<slot />
 <!-- <Booking/>  -->
</div>



