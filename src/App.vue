<template>
  <div class="bg-dark">
    <Sidenav/>
    <Playbar/>
  </div>
</template>

<script>
import Sidenav from '@/components/Sidenav'
import Playbar from '@/components/Playbar'

export default {
  components: {
    Sidenav,
    Playbar
  }
}
</script>
