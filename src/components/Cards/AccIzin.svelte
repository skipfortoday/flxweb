<script>
  // core components
  import TableDropdown from "components/Dropdowns/TableDropdown.svelte";

  const bootstrap = "../assets/img/bootstrap.jpg";
  const angular = "../assets/img/angular.jpg";
  const sketch = "../assets/img/sketch.jpg";
  const react = "../assets/img/react.jpg";
  const vue = "../assets/img/react.jpg";

  const team1 = "../assets/img/team-1-800x800.jpg";
  const team2 = "../assets/img/team-2-800x800.jpg";
  const team3 = "../assets/img/team-3-800x800.jpg";
  const team4 = "../assets/img/team-4-470x470.png";

  export let fullizin
  $: fetch(`http://192.168.1.100:3000/api/fullizin`)
		.then(r => r.json())
		.then(data => {
			fullizin = data
		});

  // can be one of light or dark
  export let color = "light";
</script>

{#if fullizin}
<div
  class="relative flex flex-col min-w-0 break-words w-full mb-6 shadow-lg rounded {color === 'light' ? 'bg-white' : 'bg-red-800 text-white'}"
>
  <div class="rounded-t mb-0 px-4 py-3 border-0">
    <div class="flex flex-wrap items-center">
      <div class="relative w-full px-4 max-w-full flex-grow flex-1">
        <h3
          class="font-semibold text-lg {color === 'light' ? 'text-gray-800' : 'text-white'}"
        >
          Izin Diterima
        </h3>
      </div>
    </div>
  </div>
  <div class="block w-full overflow-x-auto">
    <!-- Projects table -->
    <table class="items-center w-full bg-transparent border-collapse">
      <thead>
        <tr>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            No
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Tanggal Izin
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Nama
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Kategori Izin
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Keterangan
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          ></th>
        </tr>
      </thead>
      <tbody>
        {#each fullizin as fullizin, i}
        <tr>
          <th
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-left flex items-center"
          >
            <img
              src="{bootstrap}"
              class="h-12 w-12 bg-white rounded-full border"
              alt="..."
            />
            <span
              class="ml-3 font-bold {color === 'light' ? 'btext-gray-700' : 'text-whit'}"
            >
                {[i+1]}
            </span>
          </th>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
               {fullizin.Tanggal}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <i class="fas fa-circle text-orange-500 mr-2"></i> {fullizin.Nama}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <div class="flex">
              <img
                src="{team1}"
                alt="..."
                class="w-10 h-10 rounded-full border-2 border-gray-100 shadow"
              />
              <img
                src="{team2}"
                alt="..."
                class="w-10 h-10 rounded-full border-2 border-gray-100 shadow -ml-4"
              />
              <img
                src="{team3}"
                alt="..."
                class="w-10 h-10 rounded-full border-2 border-gray-100 shadow -ml-4"
              />
              <img
                src="{team4}"
                alt="..."
                class="w-10 h-10 rounded-full border-2 border-gray-100 shadow -ml-4"
              />
            </div>
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <div class="flex items-center">
              <span class="mr-2">60%</span>
              <div class="relative w-full">
                <div
                  class="overflow-hidden h-2 text-xs flex rounded bg-red-200"
                >
                  <div
                    style="width: 60%;"
                    class="shadow-none flex flex-col text-center whitespace-nowrap text-white justify-center bg-red-500"
                  ></div>
                </div>
              </div>
            </div>
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-right"
          >
            <TableDropdown />
          </td>
        </tr>
        {/each}
      </tbody>
    </table>
  </div>
</div>
{/if}
