<template>
  <div>
    <div style="height: 72px"></div>
    <b-navbar
      class="fixed-top"
      toggleable="sm"
      style="background-color: #272727"
    >
      <b-container>
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
          <b-navbar-brand href="https://www.jelly-party.com">
            <h2 class="brand-name">Jelly Party</h2></b-navbar-brand
          >
        </b-navbar-nav>
        <b-collapse id="nav-collapse" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <a
              href="https://patreon.com/jellyparty"
              target="_blank"
              class="patreon-button"
            >
              <div class="d-flex align-items-center" style="height: 100%">
                <svg
                  viewBox="0 0 569 546"
                  xmlns="http://www.w3.org/2000/svg"
                  width="18px"
                  height="18px"
                  fill="white"
                  class="mr-2"
                >
                  <g>
                    <circle
                      id="Oval"
                      cx="362.589996"
                      cy="204.589996"
                      data-fill="1"
                      r="204.589996"
                    ></circle>
                    <rect
                      id="Rectangle"
                      fill="#002b49"
                      data-fill="2"
                      height="545.799988"
                      width="100"
                      x="0"
                      y="0"
                    ></rect>
                  </g>
                </svg>
                Support us on Patreon
              </div>
            </a>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
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

.patreon-button {
  height: 40px;
  border-radius: 20px;
  background-color: #f86753;
  color: white;
  font-family: sans-serif;
  font-size: 14px;
  overflow: hidden;
  padding: 0 20px 0 10px;
  cursor: pointer;
  border: 1px solid transparent;
  transition: all 100ms ease;
  border: 2px solid transparent;
  font-weight: bold;
}

.patreon-button:hover {
  border: 2px solid white;
}
</style>
