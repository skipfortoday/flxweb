<script>
export let pegawai
$: fetch(`http://192.168.1.17:3000/api/user`)
      .then(r => r.json())
      .then(user => {
          pegawai = user
      }); 
</script>