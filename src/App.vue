<template>
  <f7-app :params="f7Params" color-theme="red">
    <f7-statusbar></f7-statusbar>
    <f7-panel right cover>
      <f7-view url="/right-panel/" links-view=".view-main"></f7-view>
    </f7-panel>
    <f7-view url="/main/"></f7-view>
  </f7-app>
</template>

<script>
  import { f7App, f7Panel, f7View, f7Statusbar } from 'framework7-vue';
  import routes from './used_routes';

  export default {
    components: {
      f7App,
      f7Panel,
      f7View,
      f7Statusbar,
    },
    data() {
      // Demo Theme
      let theme = 'ios';
      if (document.location.search.indexOf('theme=') >= 0) {
        theme = document.location.search.split('theme=')[1].split('&')[0];
      }

      return {
        f7Params: {
          theme,
          routes,
          id: 'io.framework7.app',
        },
      };
    },
  };
</script>


<style>
@import url("./assets/css/app.css");
@import url("./assets/css/framework7.css");
</style>
