<script>
  // core components
  import Pegawai from "components/Cards/Pegawai.svelte";
  import ListMesin from "components/Cards/ListMesin.svelte";
  export let location;
</script>

  <div class="w-full lg:w-8/12 px-4">
    <Pegawai />
  </div>
  <div class="w-full lg:w-8/12 px-4">
    <ListMesin />
  </div>

