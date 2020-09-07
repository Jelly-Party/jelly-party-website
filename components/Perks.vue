<template>
  <b-container fluid class="pt-5 my-5">
    <h1 class="display-4 text-center mb-5">Worry-free watch parties</h1>
    <b-row>
      <b-col sm class="perk-col">
        <h2 class="text-center">(Video-) Chat with your friends.</h2>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          focusable="false"
          data-prefix="fas"
          data-icon="video"
          class="svg-inline--fa fa-video fa-w-18 svg-elem"
          role="img"
          viewBox="0 0 576 512"
        >
          <path
            fill="currentColor"
            d="M336.2 64H47.8C21.4 64 0 85.4 0 111.8v288.4C0 426.6 21.4 448 47.8 448h288.4c26.4 0 47.8-21.4 47.8-47.8V111.8c0-26.4-21.4-47.8-47.8-47.8zm189.4 37.7L416 177.3v157.4l109.6 75.5c21.2 14.6 50.4-.3 50.4-25.8V127.5c0-25.4-29.1-40.4-50.4-25.8z"
          />
        </svg>
      </b-col>
      <b-col sm class="perk-col">
        <h2 class="text-center">Always watch in sync.</h2>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          focusable="false"
          data-prefix="fas"
          data-icon="sync"
          class="svg-inline--fa fa-sync fa-w-16 svg-elem"
          role="img"
          viewBox="0 0 512 512"
        >
          <path
            fill="currentColor"
            d="M440.65 12.57l4 82.77A247.16 247.16 0 0 0 255.83 8C134.73 8 33.91 94.92 12.29 209.82A12 12 0 0 0 24.09 224h49.05a12 12 0 0 0 11.67-9.26 175.91 175.91 0 0 1 317-56.94l-101.46-4.86a12 12 0 0 0-12.57 12v47.41a12 12 0 0 0 12 12H500a12 12 0 0 0 12-12V12a12 12 0 0 0-12-12h-47.37a12 12 0 0 0-11.98 12.57zM255.83 432a175.61 175.61 0 0 1-146-77.8l101.8 4.87a12 12 0 0 0 12.57-12v-47.4a12 12 0 0 0-12-12H12a12 12 0 0 0-12 12V500a12 12 0 0 0 12 12h47.35a12 12 0 0 0 12-12.6l-4.15-82.57A247.17 247.17 0 0 0 255.83 504c121.11 0 221.93-86.92 243.55-201.82a12 12 0 0 0-11.8-14.18h-49.05a12 12 0 0 0-11.67 9.26A175.86 175.86 0 0 1 255.83 432z"
          />
        </svg>
      </b-col>
      <b-col sm class="perk-col">
        <h2 class="text-center">Free. No registration required.</h2>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          focusable="false"
          data-prefix="fas"
          data-icon="sign-in-alt"
          class="svg-inline--fa fa-sign-in-alt fa-w-16 svg-elem"
          role="img"
          viewBox="0 0 512 512"
        >
          <path
            fill="currentColor"
            d="M416 448h-84c-6.6 0-12-5.4-12-12v-40c0-6.6 5.4-12 12-12h84c17.7 0 32-14.3 32-32V160c0-17.7-14.3-32-32-32h-84c-6.6 0-12-5.4-12-12V76c0-6.6 5.4-12 12-12h84c53 0 96 43 96 96v192c0 53-43 96-96 96zm-47-201L201 79c-15-15-41-4.5-41 17v96H24c-13.3 0-24 10.7-24 24v96c0 13.3 10.7 24 24 24h136v96c0 21.5 26 32 41 17l168-168c9.3-9.4 9.3-24.6 0-34z"
          />
        </svg>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {}
</script>

<style>
.svg-elem {
  height: 5em;
  width: 5em;
}

.perk-col {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}
</style>
