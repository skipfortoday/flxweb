<script>
  import { Router, Route } from "svelte-routing";

  // components for this layout
  import AdminNavbar from "components/Navbars/AdminNavbar.svelte";
  import Sidebar from "components/Sidebar/Sidebar.svelte";
  import HeaderStats from "components/Headers/HeaderStats.svelte";
  import FooterAdmin from "components/Footers/FooterAdmin.svelte";

  // pages for this layout
  import Dashboard from "views/admin/Dashboard.svelte";
  import Pegawai from "views/admin/Pegawai.svelte";
  import Absensi from "views/admin/Absensi.svelte";
  import Izin from "views/admin/Izin.svelte";
  import LaporanKaryawan from "views/admin/LaporanKaryawan.svelte";

  export let location;
  export let admin = "";
</script>

<div>
  <Sidebar location={location}/>
  <div class="relative md:ml-64 bg-gray-200">
    <AdminNavbar />
    <HeaderStats />
    <div class="px-4 md:px-10 mx-auto w-full -m-24">
      <Router url="admin">
        <Route path="dashboard" component="{Dashboard}" />
        <Route path="pegawai" component="{Pegawai}" />
        <Route path="absensi" component="{Absensi}" />
        <Route path="izin" component="{Izin}" />
        <Route path="laporankaryawan" component="{LaporanKaryawan}" />
      </Router>
    <FooterAdmin />
    </div>
  </div>
</div>
