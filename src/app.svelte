<script>
  import { Router, Route } from 'svelte-routing';
  import Bookslot from './routes/bookslot.svelte';
  import Homepage from './routes/homepage.svelte';
   import Slotconfirm from './routes/confirmbook.svelte';

  </script>
  <Router>
    <Route path="/" component={Homepage} /> 
     <Route path="/bookslot" component={Bookslot} /> 
  <Route path="/confirmbook" component={Slotconfirm} />
  </Router>
