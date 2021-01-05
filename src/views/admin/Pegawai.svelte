<script>
  // core components
  import Pegawai from "components/Cards/Pegawai.svelte";
  import ListMesin from "components/Cards/ListMesin.svelte";
  export let location;
</script>

  <div class="w-full xl:w-10/14 mb-14 xl:mb-0 px-6">
    <Pegawai />
  </div>
  <div class="w-full xl:w-10/14 mb-14 xl:mb-0 px-6">
    <ListMesin />
  </div>

