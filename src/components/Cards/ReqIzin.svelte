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

  export let pengajuanizin
  $: fetch(`http://192.168.0.25:3000/api/izin`)
		.then(r => r.json())
		.then(data => {
			pengajuanizin = data
		});

  // can be one of light or dark
  export let color = "light";
</script>

{#if pengajuanizin}
<div
  class="relative flex flex-col min-w-0 break-words w-full mb-6 shadow-lg rounded {color === 'light' ? 'bg-white' : 'bg-red-800 text-white'}"
>
  <div class="rounded-t mb-0 px-4 py-3 border-0">
    <div class="flex flex-wrap items-center">
      <div class="relative w-full px-4 max-w-full flex-grow flex-1">
        <h3
          class="font-semibold text-lg {color === 'light' ? 'text-gray-800' : 'text-white'}"
        >
          Request Izin
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
            Nama
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Tanggal Izin
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Tanggal Selesai
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Kategori Izin
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          >
            Kantor
          </th>
          <th
            class="px-6 align-middle border border-solid py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left {color === 'light' ? 'bg-gray-100 text-gray-600 border-gray-200' : 'bg-red-700 text-red-200 border-red-600'}"
          ></th>
        </tr>
      </thead>
      <tbody>
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
              {pengajuanizin[0].nama}

            </span>
          </th>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
               {pengajuanizin[0].tgl_mulai}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[0].tgl_selesai}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[0].kategori_izin}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[0].nama_cabang}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-right"
          >
            <TableDropdown />
          </td>
        </tr>
        <tr>
          <th
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-left flex items-center"
          >
            <img
              src="{vue}"
              class="h-12 w-12 bg-white rounded-full border"
              alt="..."
            />
            <span
              class="ml-3 font-bold {color === 'light' ? 'btext-gray-700' : 'text-whit'}"
            >
              {pengajuanizin[1].nama}

            </span>
          </th>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
               {pengajuanizin[1].tgl_mulai}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[1].tgl_selesai}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[1].kategori_izin}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[1].nama_cabang}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-right"
          >
            <TableDropdown />
          </td>
        </tr>
        <tr>
          <th
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-left flex items-center"
          >
            <img
              src="{sketch}"
              class="h-12 w-12 bg-white rounded-full border"
              alt="..."
            />
            <span
              class="ml-3 font-bold {color === 'light' ? 'btext-gray-700' : 'text-whit'}"
            >
              {pengajuanizin[2].nama}

            </span>
          </th>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
               {pengajuanizin[2].tgl_mulai}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[2].tgl_selesai}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[2].kategori_izin}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[2].nama_cabang}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-right"
          >
            <TableDropdown />
          </td>
        </tr>
        <tr>
          <th
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-left flex items-center"
          >
            <img
              src="{react}"
              class="h-12 w-12 bg-white rounded-full border"
              alt="..."
            />
            <span
              class="ml-3 font-bold {color === 'light' ? 'btext-gray-700' : 'text-whit'}"
            >
              {pengajuanizin[3].nama}

            </span>
          </th>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
               {pengajuanizin[3].tgl_mulai}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[3].tgl_selesai}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[3].kategori_izin}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[3].nama_cabang}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-right"
          >
            <TableDropdown />
          </td>
        </tr>
        <tr>
          <th
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-left flex items-center"
          >
            <img
              src="{angular}"
              class="h-12 w-12 bg-white rounded-full border"
              alt="..."
            />
            <span
              class="ml-3 font-bold {color === 'light' ? 'btext-gray-700' : 'text-whit'}"
            >
              {pengajuanizin[4].nama}

            </span>
          </th>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
               {pengajuanizin[4].tgl_mulai}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
            <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[4].tgl_selesai}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[4].kategori_izin}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          <i class="fas fa-circle text-orange-500 mr-2"></i> {pengajuanizin[4].nama_cabang}
          </td>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-right"
          >
            <TableDropdown />
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
{/if}
