<template>
  <div>
    <section>
      <Filters />

      <BrowserSelector :browser="browser" @clicked="browser = $event" />
      <component :is="browser" :filters="filters" :contributions="contributions" />
    </section>
  </div>
</template>

<script>
import BrowserSelector from './browse/BrowserSelector'
import Filters from './browse/Filters'
import ListBrowser from './browse/ListBrowser'
import TileBrowser from './browse/TileBrowser'

export default {
  components: {
    BrowserSelector,
    Filters,
    ListBrowser,
    TileBrowser,
  },
  props: {
    filters: {type: Object},
    contributions: {type: Array},
  },
  data() {
    return {
      browser: TileBrowser,
    }
  },
}
</script>
