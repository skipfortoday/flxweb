<script>
  export let pegawai
  $: fetch(`http://192.168.0.25:3000/api/user`)
		.then(r => r.json())
		.then(user => {
			pegawai = user
		}); 
</script>


<div
  class="relative flex flex-col min-w-0 break-words w-full mb-6 shadow-lg rounded-lg bg-gray-200 border-0"
>
  <div class="rounded-t bg-white mb-0 px-6 py-6">
    <div class="text-center flex justify-between">
      <h6 class="text-gray-800 text-xl font-bold">Tambah Akun</h6>
      <button
        class="bg-red-500 text-white active:bg-red-600 font-bold uppercase text-xs px-4 py-2 rounded shadow hover:shadow-md outline-none focus:outline-none mr-1 ease-linear transition-all duration-150"
        type="button"
      >
        +
      </button>
    </div>
  </div>
  <div class="flex-auto px-4 lg:px-10 py-10 pt-0">
    <form>
      <h6 class="text-gray-500 text-sm mt-3 mb-6 font-bold uppercase">
        Pilih Nama Karyawan, Masukkan Username & Password
      </h6>
      <div class="flex flex-wrap">
        <div class="w-full lg:w-4/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-username"
            >
              Nama Karyawan
            </label>
            <input
              id="grid-username"
              type="text"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="Rizqi Pratama"
            />
          </div>
        </div>
        <div class="w-full lg:w-4/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              Username
            </label>
            <input
              id="grid-email"
              type="email"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="rizqipratamar"
            />
          </div>
        </div>
        <div class="w-full lg:w-4/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              Password
            </label>
            <input
              id="grid-email"
              type="email"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="rizqipratamar"
            />
          </div>
        </div>
      </div>
    </form>
  </div>  
</div>
{#if pegawai}
<div
  class="relative flex flex-col min-w-0 break-words bg-white w-full mb-6 shadow-lg rounded"
>
  <div class="rounded-t mb-0 px-4 py-3 border-0">
    <div class="flex flex-wrap items-center">
      <div class="relative w-full px-4 max-w-full flex-grow flex-1">
        <h3 class="font-semibold text-base text-gray-800">
          List Pegawai
        </h3>
      </div>
      <div class="relative w-full px-4 max-w-full flex-grow flex-1 text-right">
        <button
          class="bg-indigo-500 text-white active:bg-indigo-600 text-xs font-bold uppercase px-3 py-1 rounded outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150"
          type="button"
        >
          See all
        </button>
      </div>
    </div>
  </div>
  <div class="block w-full overflow-x-auto">
    <!-- Projects table -->
    <table class="items-center w-full bg-transparent border-collapse">
      <thead>
        <tr>
          <th
          class="px-6 bg-gray-100 text-gray-600 align-middle border border-solid border-gray-200 py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left"
          >
          No
          </th>
          <th
            class="px-6 bg-gray-100 text-gray-600 align-middle border border-solid border-gray-200 py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left"
          >
            Nama
          </th>
          <th
            class="px-6 bg-gray-100 text-gray-600 align-middle border border-solid border-gray-200 py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left"
          >
          </th>
        </tr>
      </thead>
      <tbody>
        {#each pegawai as pegawai, i}
        <tr>
          <th
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4 text-left"
          >
           {[i+1]}
          </th>
          <td
            class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
          >
              {pegawai.Nama}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
          </td>
        </tr>
        {/each}
      </tbody>
    </table>
  </div>
  <div class="py-2">
    <nav class="block">
      <ul class="flex pl-0 rounded list-none flex-wrap">
        <li>
          <a href="#pablo" class="first:ml-0 text-xs font-semibold flex w-8 h-8 mx-1 p-0 rounded-full items-center justify-center leading-tight relative border border-solid border-orange-500 bg-white text-orange-500">
            <i class="fas fa-chevron-left -ml-px"></i>
          </a>
        </li>
        <li>
          <a href="#pablo" class="first:ml-0 text-xs font-semibold flex w-8 h-8 mx-1 p-0 rounded-full items-center justify-center leading-tight relative border border-solid border-orange-500 text-white bg-orange-500">
            1
          </a>
        </li>
        <li>
          <a href="#pablo" class="first:ml-0 text-xs font-semibold flex w-8 h-8 mx-1 p-0 rounded-full items-center justify-center leading-tight relative border border-solid border-orange-500 bg-white text-orange-500">
            2
          </a>
        </li>
        <li>
          <a href="#pablo" class="first:ml-0 text-xs font-semibold flex w-8 h-8 mx-1 p-0 rounded-full items-center justify-center leading-tight relative border border-solid border-orange-500 bg-white text-orange-500">
            3
          </a>
        </li>
        <li>
          <a href="#pablo" class="first:ml-0 text-xs font-semibold flex w-8 h-8 mx-1 p-0 rounded-full items-center justify-center leading-tight relative border border-solid border-orange-500 bg-white text-orange-500">
            4
          </a>
        </li>
        <li>
          <a href="#pablo" class="first:ml-0 text-xs font-semibold flex w-8 h-8 mx-1 p-0 rounded-full items-center justify-center leading-tight relative border border-solid border-orange-500 bg-white text-orange-500">
            5
          </a>
        </li>
        <li>
          <a href="#pablo" class="first:ml-0 text-xs font-semibold flex w-8 h-8 mx-1 p-0 rounded-full items-center justify-center leading-tight relative border border-solid border-orange-500 bg-white text-orange-500">
            <i class="fas fa-chevron-right -mr-px"></i>
          </a>
        </li>
      </ul>
    </nav>
  </div>
</div>
{/if}
