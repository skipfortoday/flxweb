<script>
  export let pegawai
  $: fetch(`http://192.168.1.100:3000/api/user`)
		.then(r => r.json())
		.then(user => {
			pegawai = user
    }); 

    import print from 'print-js'

  let UserID = '';
  let Nama = '';
  let Pass = '';
  let TglMasuk = '';
  let RoleUser = '';
  let IdGroups = '';
  let KodeCabang = '';
	let i = 0;

    async function doPost () {
		const res = await fetch('http://192.168.1.16:3000/api/user', {
			method: 'POST',
			body: JSON.stringify({UserID,Nama,Pass,RoleUser,IdGroups,KodeCabang
			})
		})
		
		const json = await res.json()
		result = JSON.stringify(json)
  }
  
  
</script>


<div
  class="relative flex flex-col min-w-0 break-words w-full mb-6 shadow-lg rounded-lg bg-gray-200 border-0"
>
  <div class="rounded-t bg-white mb-0 px-6 py-6">
    <div class="text-center flex justify-between">
      <h6 class="text-gray-800 text-xl font-bold">Daftarkan Pegawai</h6>
  
    </div>
  </div>
  <div class="flex-auto px-4 lg:px-10 py-10 pt-0">
    <form id="printJS-form">
      <h6 class="text-gray-500 text-sm mt-3 mb-6 font-bold">
        Isikan Data Karyawan 
      </h6>
      <div class="flex flex-wrap">
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              UserID
            </label>
            <input
              bind:value={UserID}
              type="email"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="SB1ACC001"
            />
          </div>
        </div>
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-username"
            >
              Nama Karyawan
            </label>
            <input
              bind:value={Nama}
              type="text"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="Rizqi Pratama"
            />
          </div>
        </div>
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              Password
            </label>
            <input
              bind:value={Pass}
              type="password"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="123"
            />
          </div>
        </div>
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              Tanggal Masuk
            </label>
            <input
               bind:value={TglMasuk}
              type="date"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="SB1ACC001"
            />
          </div>
        </div>
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              Role
            </label>
            <input
               bind:value={RoleUser}
              type="email"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="1 - Directur , 2 - Manager , 3 - SPV, 4 - Staff"
            />
          </div>
        </div>
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              IdGroups
            </label>
            <input
               bind:value={IdGroups}
              type="email"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="DIR -- ADM"
            />
          </div>
        </div>
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              KodeCabang
            </label>
            <input
              bind:value={KodeCabang}
              type="email"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="SB1 -- SB2 -- JK1"
            />
          </div>
        </div>
        <div class="w-full lg:w-3/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
            <span class="text-xs font-semibold inline-block py-1 px-6 uppercase rounded text-orange-600 bg-orange-500 uppercase last:mr-0 mr-1">
              
            </span>            
            </label>
            <button class="bg-orange-500 text-white active:bg-orange-600 font-bold uppercase text-sm px-6 py-3 rounded shadow hover:shadow-lg outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150" type="button" onclick="printJS('printJS-form', 'html')">
              <i class="fas fa-user-plus"></i> Daftarkan Pegawai
            </button>
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
        <div class="relative flex w-full flex-wrap items-stretch mb-3">
          <input type="text" placeholder="Search" class="px-3 py-3 placeholder-gray-400 text-gray-700 relative bg-white bg-white rounded text-sm border border-gray-400 outline-none focus:outline-none focus:shadow-outline w-full pr-10"/>
          <span class="z-10 h-full leading-snug font-normal absolute text-center text-gray-400 absolute bg-transparent rounded text-base items-center justify-center w-8 right-0 pr-3 py-3">
            <i class="fas fa-user"></i>
          </span>
        </div>
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
            UserID
          </th>
          <th
            class="px-6 bg-gray-100 text-gray-600 align-middle border border-solid border-gray-200 py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left"
          >
            Nama
          </th>
          <th
            class="px-6 bg-gray-100 text-gray-600 align-middle border border-solid border-gray-200 py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left"
          >
            Jabatan
          </th>
          <th
            class="px-6 bg-gray-100 text-gray-600 align-middle border border-solid border-gray-200 py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left"
          >
            Cabang
          </th>
          <th
          class="px-6 bg-gray-100 text-gray-600 align-middle border border-solid border-gray-200 py-3 text-xs uppercase border-l-0 border-r-0 whitespace-no-wrap font-semibold text-left"
           >
            Kerja Mulai
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
            {pegawai.UserID}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
           {pegawai.Nama}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
           {pegawai.NamaRole}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
           {pegawai.NamaCabang}
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
             {pegawai.Hari} / {pegawai.Bulan} / {pegawai.Tahun}     
          </td>
          <td
          class="border-t-0 px-6 align-middle border-l-0 border-r-0 text-xs whitespace-no-wrap p-4"
           >
           <button class="bg-orange-500 text-white active:bg-orange-600 font-bold uppercase text-xs px-4 py-2 rounded-full shadow hover:shadow-md outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150" type="button">
            <i class="fas fa-user-edit"></i> Edit
          </button>
          <button class="bg-orange-500 text-white active:bg-orange-600 font-bold uppercase text-xs px-4 py-2 rounded-full shadow hover:shadow-md outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150" type="button">
            <i class="fas fa-user-minus"></i> Delete
          </button>
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
