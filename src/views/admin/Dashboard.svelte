<script>
  // core components
  import RecentScanAbsen from "components/Cards/RecentScanAbsen.svelte";
  import RecentIzin from "components/Cards/RecentIzin.svelte";
  export let location;
</script>




    <div class="w-full xl:w-10/14 mb-14 xl:mb-0 px-6">
      <RecentScanAbsen />
    </div>
    <div class="xl:w-10/14 mb-14 xl:mb-0 px-6">
      <RecentIzin />
    </div>


