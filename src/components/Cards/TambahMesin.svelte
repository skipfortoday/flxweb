<div
  class="relative flex flex-col min-w-0 break-words w-full mb-6 shadow-lg rounded-lg bg-gray-200 border-0"
>
  <div class="rounded-t bg-white mb-0 px-6 py-6">
    <div class="text-center flex justify-between">
      <h6 class="text-gray-800 text-xl font-bold">Tambah Mesin</h6>
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
        Tambahkan Serial Number Dan Nama Cabang
      </h6>
      <div class="flex flex-wrap">
        <div class="w-full lg:w-6/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-username"
            >
              Serial Number
            </label>
            <input
              id="grid-username"
              type="text"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="66666127671267"
            />
          </div>
        </div>
        <div class="w-full lg:w-6/12 px-4">
          <div class="relative w-full mb-3">
            <label
              class="block uppercase text-gray-700 text-xs font-bold mb-2"
              for="grid-email"
            >
              Nama Cabang
            </label>
            <input
              id="grid-email"
              type="email"
              class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
              placeholder="Karanga Asem"
            />
          </div>
        </div>
      </div>
    </form>
  </div>
</div>
