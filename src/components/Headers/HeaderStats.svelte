<script>
  // core components
  import CardStats from "components/Cards/CardStats.svelte";
  export let recordsm
  $: fetch(`http://192.168.0.25:3000/api/recordsm`)
		.then(r => r.json())
		.then(data => {
			recordsm = data
		});
</script>

<!-- Header -->
<div class="relative bg-orange-500 md:pt-32 pb-32 pt-12">
  <div class="px-4 md:px-10 mx-auto w-full">
    <div>
      <!-- Card stats -->
      <div class="flex flex-wrap">
        <div class="w-full lg:w-6/12 xl:w-3/12 px-4">
          <CardStats
            statSubtitle="Record"
            statTitle="350,897"
            statArrow="up"
            statPercent="3.48"
            statPercentColor="text-green-500"
            statDescripiron="Since Last Month"
            statIconName="far fa-chart-bar"
            statIconColor="bg-red-500"
          />
        </div>
        <div class="w-full lg:w-6/12 xl:w-3/12 px-4">
          <CardStats
            statSubtitle="Kantor"
            statTitle="8"
            statArrow="up"
            statPercent="3.48"
            statPercentColor="text-red-500"
            statDescripiron="Since Last Month"
            statIconName="fas fa-chart-pie"
            statIconColor="bg-orange-500"
          />
        </div>
        <div class="w-full lg:w-6/12 xl:w-3/12 px-4">
          <CardStats
            statSubtitle="Karyawan"
            statTitle="120"
            statArrow="uo"
            statPercent="1.10"
            statPercentColor="text-orange-500"
            statDescripiron="Since Last Month"
            statIconName="fas fa-users"
            statIconColor="bg-pink-500"
          />
        </div>
        <div class="w-full lg:w-6/12 xl:w-3/12 px-4">
          <CardStats
            statSubtitle="PERFORMANCE"
            statTitle="49,65%"
            statArrow="up"
            statPercent="12"
            statPercentColor="text-green-500"
            statDescripiron="Since Last Month"
            statIconName="fas fa-percent"
            statIconColor="bg-green-500"
          />
        </div>
      </div>
    </div>
  </div>
</div>
