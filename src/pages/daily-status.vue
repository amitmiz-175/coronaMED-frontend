<template>
  <f7-page name="daily status">
    <f7-navbar title="Daily Status" back-link="Back"></f7-navbar>

    <f7-list-input
        label="Pulse"
        :input="false"
      >
        <f7-range slot="input" :value="120" :min="0" :max="200" :step="1"></f7-range>
    </f7-list-input>

    <f7-list-input
        label="Fever"
        :input="false"
      >
        <f7-range slot="input" :value="37" :min="35" :max="43" :step="0.1"></f7-range>
    </f7-list-input>
    
    <f7-row tag="p">
      <f7-button @click="submit" class="col" large fill raised>Submit</f7-button>
    </f7-row>

    <f7-block-title>Cough</f7-block-title>
    <f7-list>
      <f7-list-item
        radio
        name="radio"
        value="No Cough"
        title="No Cough"
      ></f7-list-item>
      <f7-list-item
        radio
        name="radio"
        value="Light Cough"
        title="Light Cough"
      ></f7-list-item>
      <f7-list-item
        radio
        name="radio"
        value="Medium Cough"
        title="Medium Cough"
      ></f7-list-item>
      <f7-list-item
        radio
        name="radio"
        value="Heavy Cough"
        title="Heavy Cough"
      ></f7-list-item>
    </f7-list>
  </f7-page>
</template>

<script>
import { Device }  from '../js/framework7-custom.js';
  import cordovaApp from '../js/cordova-app.js';
  import routes from '../js/routes.js';

  export default {
    data() {
      return {
        // Framework7 Parameters
        f7params: {
          id: 'com.amitmiz.coronaMED', // App bundle ID
          name: 'CoronaMED', // App name
          theme: 'auto', // Automatic theme detection


          // App routes
          routes: routes,


          // Input settings
          input: {
            scrollIntoViewOnFocus: Device.cordova && !Device.electron,
            scrollIntoViewCentered: Device.cordova && !Device.electron,
          },
          // Cordova Statusbar settings
          statusbar: {
            iosOverlaysWebView: true,
            androidOverlaysWebView: false,
          },
        },

        // Login screen data
        username: '',
        password: '',
      }
    },
    methods: {
      submit() {
        this.$f7.dialog.alert('Thank you for your information!');
      }
    }
  }
</script>