<template>
  <f7-page name="Detailes">
    <f7-navbar title="Personal Detailes" back-link="Back"></f7-navbar>

    <f7-block-title>Dry Detailes</f7-block-title>
    <f7-list no-hairlines-md>
      <f7-list-input
        label="Name"
        type="text"
        placeholder="Your name"
      ></f7-list-input>

      <f7-list-input
        label="E-mail"
        type="email"
        placeholder="E-mail"
      ></f7-list-input>

      <f7-list-input
        label="URL"
        type="url"
        placeholder="URL"
      ></f7-list-input>

      <f7-list-input
        label="Password"
        type="password"
        placeholder="Password"
      ></f7-list-input>

      <f7-list-input
        label="Phone"
        type="tel"
        placeholder="Phone"
      ></f7-list-input>

      <f7-list-input
        label="Gender"
        type="select"
        >
        <option>Male</option>
        <option>Female</option>
      </f7-list-input>

      <f7-list-input
        label="Birth date"
        type="date"
        placeholder="Birth day"
        defaultValue="2014-04-30"
      ></f7-list-input>
      </f7-list>

      <f7-block-title>Background Diseases</f7-block-title>
    <f7-list>
      <f7-list-item
        checkbox
        name="my-checkbox"
        value="Cancer"
        title="Cancer"
      ></f7-list-item>
      <f7-list-item
        checkbox
        name="my-checkbox"
        value="Diabetes"
        title="Diabetes"
      ></f7-list-item>
      <f7-list-item
        checkbox
        name="my-checkbox"
        value="Asthma"
        title="Asthma"
      ></f7-list-item>
      <f7-list-input
        label="Other"
        type="text"
        placeholder="Other"
      ></f7-list-input>
    </f7-list>
    <f7-row tag="p">
      <f7-button @click="submit" class="col" large fill raised>Submit</f7-button>
    </f7-row>

      <!-- <f7-list-item
        title="Toggle"
      >
        <f7-toggle slot="after"></f7-toggle>
      </f7-list-item>

      <f7-list-input
        label="Range"
        :input="false"
      >
        <f7-range slot="input" :value="50" :min="0" :max="100" :step="1"></f7-range>
      </f7-list-input>

      <f7-list-input
        type="textarea"
        label="Textarea"
        placeholder="Bio"
      ></f7-list-input>
      <f7-list-input
        type="textarea"
        label="Resizable"
        placeholder="Bio"
        resizable
      ></f7-list-input>
    </f7-list>

    <f7-block-title>Buttons</f7-block-title>
    <f7-block strong>
      <f7-row tag="p">
        <f7-button class="col">Button</f7-button>
        <f7-button class="col" fill>Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" raised>Raised</f7-button>
        <f7-button class="col" raised fill>Raised Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" round>Round</f7-button>
        <f7-button class="col" round fill>Round Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" outline>Outline</f7-button>
        <f7-button class="col" round outline>Outline Round</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" small outline>Small</f7-button>
        <f7-button class="col" small round outline>Small Round</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" small fill>Small</f7-button>
        <f7-button class="col" small round fill>Small Round</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" large raised>Large</f7-button>
        <f7-button class="col" large fill raised>Large Fill</f7-button>
      </f7-row>
      <f7-row tag="p">
        <f7-button class="col" large fill raised color="red">Large Red</f7-button>
        <f7-button class="col" large fill raised color="green">Large Green</f7-button>
      </f7-row>
    </f7-block>

    <f7-block-title>Checkbox group</f7-block-title>
    <f7-list>
      <f7-list-item
        checkbox
        name="my-checkbox"
        value="Books"
        title="Books"
      ></f7-list-item>
      <f7-list-item
        checkbox
        name="my-checkbox"
        value="Movies"
        title="Movies"
      ></f7-list-item>
      <f7-list-item
        checkbox
        name="my-checkbox"
        value="Food"
        title="Food"
      ></f7-list-item>
    </f7-list>

    <f7-block-title>Radio buttons group</f7-block-title>
    <f7-list>
      <f7-list-item
        radio
        name="radio"
        value="Books"
        title="Books"
      ></f7-list-item>
      <f7-list-item
        radio
        name="radio"
        value="Movies"
        title="Movies"
      ></f7-list-item>
      <f7-list-item
        radio
        name="radio"
        value="Food"
        title="Food"
      ></f7-list-item>
    </f7-list> -->
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
    },
    mounted() {
      this.$f7ready((f7) => {
        // Init cordova APIs (see cordova-app.js)
        if (Device.cordova) {
          cordovaApp.init(f7);
        }
        // Call F7 APIs here
      });
    }
  }
</script>