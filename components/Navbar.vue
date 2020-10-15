<template>
  <div>
    <div style="height: 62px"></div>
    <b-navbar
      class="fixed-top p-2"
      toggleable="lg"
      style="background-color: #272727; box-shadow: 0px 2px 5px 1px rgba(0,0,0,0.75);"
    >
      <b-container
        class="d-flex align-items-center justify-content-space-around"
      >
        <!-- Content here -->
        <b-navbar-toggle target="nav-collapse">
          <template v-slot:default>
            <b-icon
              color="white"
              icon="list"
              width="1.5em"
              height="1.5em"
            ></b-icon>
          </template>
        </b-navbar-toggle>

        <b-navbar-nav>
          <b-navbar-brand href="/">
            <h2 class="brand-name m-0">Jelly Party</h2></b-navbar-brand
          >
        </b-navbar-nav>
        <b-collapse id="nav-collapse" is-nav>
          <div
            class="d-flex align-items-center w-100"
            style="justify-content: flex-end; flex-wrap: wrap"
          >
            <b-navbar-nav>
              <b-navbar-brand
                :href="getDownloadLink"
                class="text-white cta-button"
              >
                <p class="m-0">Get the extension now</p></b-navbar-brand
              >
            </b-navbar-nav>
            <b-navbar-nav>
              <KofiButton
                style="margin-left: 1em"
                p-text="Buy Me a Coffee"
                p-color=" #007bff"
              />
            </b-navbar-nav>
          </div>
        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>

<script>
import KofiButton from './KofiButton'
export default {
  components: { KofiButton },
  computed: {
    getDownloadLink() {
      if (window.navigator.userAgent.includes('Firefox')) {
        return 'https://addons.mozilla.org/en-US/firefox/addon/jelly-party/'
      } else {
        return 'https://chrome.google.com/webstore/detail/jelly-party/aiecbkandfgpphpdilbaaagnampmdgpd'
      }
    }
  }
}
</script>

<style lang="scss">
@mixin cta-button-template() {
  background: #007bff;
  color: white;
  border-radius: 7px;
  padding: 0.3em 0.5em;
  transition: 500ms all ease;
  margin: 3px 0em;
  cursor: pointer;
  &:hover {
    filter: grayscale(80%);
  }
}

.brand-name {
  color: white;
}

.brand-name:hover {
  transition: color 0.2s ease-in-out;
  color: red;
}
.navbar-light .navbar-toggler-icon {
  background: url('data:image/svg+xml,%3csvg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 30 30"%3e%3cpath stroke="rgba(255, 255, 255, 1)" stroke-linecap="round" stroke-miterlimit="10" stroke-width="2" d="M4 7h22M4 15h22M4 23h22"/%3e%3c/svg%3e') !important;
}

.cta-button {
  @include cta-button-template;
}
</style>
