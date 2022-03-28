<template>
  <v-row justify="center" align="center">
    <v-col cols="12" >
      <div id="page">
        <div class="container">
          <div class="searching" data-widget-search-panel="doctors">
            <form class="search-form" id="searching-form" action="">

              <InputSelect
                placeholder="Клиника"
                :options="clinics"
                :value="clinicSelected"
                icon-path="M 8.421 19.999 C 8.421 19.999 0 12.288 0 7.916 C 0 3.544 3.582 0 8 0 C 12.418 0 16 3.544 16 7.916 C 16 12.288 8.421 19.999 8.421 19.999 Z M 8 4.625 C 6.24 4.625 4.812 6.003 4.812 7.703 C 4.812 9.403 6.24 10.781 8 10.781 C 9.76 10.781 11.187 9.403 11.187 7.703 C 11.187 6.003 9.76 4.625 8 4.625 Z"
              />

              <InputSelect
                placeholder="Специализация"
                :options="specials"
                :value="clinicSelected"
                icon-path="M 19.565 19.596 C 18.979 20.181 18.029 20.181 17.444 19.596 L 14.191 16.344 C 12.724 17.383 10.935 18 9 18 C 4.029 18 0 13.97 0 9 C 0 4.029 4.029 0 9 0 C 13.97 0 18 4.029 18 9 C 18 10.951 17.372 12.752 16.317 14.227 L 19.565 17.474 C 20.151 18.06 20.151 19.01 19.565 19.596 Z M 9 3 C 5.686 3 3 5.686 3 9 C 3 12.314 5.686 15 9 15 C 12.314 15 15 12.314 15 9 C 15 5.686 12.314 3 9 3 Z"
              />

              <InputSelect
                placeholder="Врач"
                :options="doctors"
                :value="clinicSelected"
                icon-path="M 19.565 19.596 C 18.979 20.181 18.029 20.181 17.444 19.596 L 14.191 16.344 C 12.724 17.383 10.935 18 9 18 C 4.029 18 0 13.97 0 9 C 0 4.029 4.029 0 9 0 C 13.97 0 18 4.029 18 9 C 18 10.951 17.372 12.752 16.317 14.227 L 19.565 17.474 C 20.151 18.06 20.151 19.01 19.565 19.596 Z M 9 3 C 5.686 3 3 5.686 3 9 C 3 12.314 5.686 15 9 15 C 12.314 15 15 12.314 15 9 C 15 5.686 12.314 3 9 3 Z"
              />

            </form>
          </div>
        </div>
      </div>
    </v-col>
  </v-row>
</template>

<script>

  import InputSelect from "../widgets/InputSelect";

  export default {
    components: {
      InputSelect

    },
    layout: 'doctors',
    name: 'doctors',
    data: () => ({
      clinics: [
        {text: 'Все клиники', value: 'all'},
        {text: 'Сокол', value: 'sokol'},
        {text: 'Королёв', value: 'korolev'},
      ],



      specials: [
        {text: 'Аллерголог', value: '6'},
        {text: 'Андролог', value: '16'},
        {text: 'Вертебролог', value: '22'},
      ],

      doctors: [
        {text: 'Шишов Георгий Владимирович', value: '2869'},
        {text: 'Цой Анжела Сергеевна', value: '2034'},
      ],
      clinicSelected: 'all',
    }),
  }
</script>


<style scoped>
  *, ::after, ::before {
    box-sizing: border-box;
  }

  .searching {
    margin: 30px 0 15px 0;
  }

  .container {
    width: 100%;
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
  }

  /* @media all and (min-width:576px) */
  .container {
    max-width: 540px;
  }

  /* @media all and (min-width:768px) */
  .container {
    max-width: 720px;
  }

  /* @media all and (min-width:992px) */
  .container {
    max-width: 960px;
  }

  /* @media all and (min-width:1200px) */
  .container {
    max-width: 1140px;
  }

  .container {
    padding: 0 !important;
    max-width: 1200px;
  }

  body {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    color: #212529;
    text-align: left;
    background-color: #fff;
  }

  body {
    background-color: #f2f3f5;
    font-family: "OpenSans", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  }

  body {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    color: #212529;
    background-color: #fff;
  }

  body {
    background-color: #f3f3f3;
    font-size: 0.87em;
    overflow-x: hidden;
    color: #353c4e;
    font-family: open sans, sans-serif;
    background-attachment: fixed;
  }

  html {
    font-family: sans-serif;
    line-height: 1.15;
    -webkit-text-size-adjust: 100%;
    -webkit-tap-highlight-color: transparent;
  }

  html {
    box-sizing: border-box;
    font-family: sans-serif;
    line-height: 1.15;
    -webkit-text-size-adjust: 100%;
    -ms-text-size-adjust: 100%;
    -ms-overflow-style: scrollbar;
    -webkit-tap-highlight-color: transparent;
  }

  :root {
    --blue: #007bff;
    --indigo: #6610f2;
    --purple: #6f42c1;
    --pink: #e83e8c;
    --red: #dc3545;
    --orange: #fd7e14;
    --yellow: #ffc107;
    --green: #28a745;
    --teal: #20c997;
    --cyan: #17a2b8;
    --white: #fff;
    --gray: #6c757d;
    --gray-dark: #343a40;
    --primary: #007bff;
    --secondary: #6c757d;
    --success: #28a745;
    --info: #17a2b8;
    --warning: #ffc107;
    --danger: #dc3545;
    --light: #f8f9fa;
    --dark: #343a40;
    --breakpoint-xs: 0;
    --breakpoint-sm: 576px;
    --breakpoint-md: 768px;
    --breakpoint-lg: 992px;
    --breakpoint-xl: 1200px;
    --font-family-sans-serif: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    --font-family-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  }

  :root {
    --green-color: #009999;
    --green-back: #e9f5f5;
    --orange: #fc674c;
    --text-color: #222224;
    --text-color-light: #8790a1;
    --placeholder-color: #aeb6c5;
    --border-color: #c5c5c5;
    --light-border-color: #dcdfe9;
    --footer-color-text: #b5bdcd;
    --back-color: #f2f3f5;
    --dark-back-color: #DCDEE1;
    --dark: #3e434b;
    --darker: #393d44;
    --light-back-color: #f9f9f9;
    --stars-color: #fa364d;
    --red-text-color: #ff4242;
    --metro-1-color: #EE2D24;
    --metro-2-color: #029A55;
    --metro-3-color: #0078BF;
    --metro-4-color: #19c1f3;
    --metro-5-color: #894e35;
    --metro-6-color: #3399cc;
    --metro-6a-color: #ff3366;
    --metro-6b-color: #F48335;
    --metro-7-color: #8F479D;
    --metro-8-color: #ffcb31;
    --metro-9-color: #798ea2;
    --metro-10-color: #b3d445;
    --metro-11-color: #79cdcd;
    --metro-12-color: #acbfe1;
    --metro-14-color: #ffa8af;
    --metro-mck-color: #ffa8af;
    --metro-mcd2-color: #df477c;
    --metro-lub-color: #8F479D;
    --metro-myt-color: #3399cc;
    --metro-kor-color: #ff3366;
    --active: #009999;
    --active-inner: #fff;
    --focus: 2px rgba(11, 207, 191, 0.3);
    --border: #9fdfd1;
    --border-hover: #016363;
    --background: #fff;
    --disabled: #f6f8ff;
    --disabled-inner: #e1e6f9;
  }

  :root {
    --mm-line-height: 20px;
    --mm-listitem-size: 44px;
    --mm-navbar-size: 44px;
    --mm-offset-top: 0;
    --mm-offset-right: 0;
    --mm-offset-bottom: 0;
    --mm-offset-left: 0;
    --mm-color-border: rgba(0, 0, 0, 0.1);
    --mm-color-button: rgba(0, 0, 0, 0.3);
    --mm-color-text: rgba(0, 0, 0, 0.75);
    --mm-color-text-dimmed: rgba(0, 0, 0, 0.3);
    --mm-color-background: #f3f3f3;
    --mm-color-background-highlight: rgba(0, 0, 0, 0.05);
    --mm-color-background-emphasis: rgba(255, 255, 255, 0.4);
    --mm-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  }

  :root {
    --mm-iconbar-size: 44px;
  }

  :root {
    --mm-iconpanel-size: 44px;
  }

  :root {
    --mm-sidebar-collapsed-size: 44px;
    --mm-sidebar-expanded-size: 440px;
  }

  .search-form {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }

  .search-special-container, .search-location-container, .search-container {
    position: relative;
    display: inline-block;
  }

  .search-special-icon {
    top: 6px;
    left: 8px;
    position: absolute;
    display: block;
  }

  .search-special-icon {
    z-index: 110;
  }

  button, input, optgroup, select, textarea {
    margin: 0;
    font-family: inherit;
    font-size: inherit;
    line-height: inherit;
  }

  button, input {
    overflow: visible;
  }

  a {
    color: #007bff;
    text-decoration: none;
    background-color: transparent;
  }

  a, a:hover {
    color: #151515;
  }

  a {
    color: #007bff;
    text-decoration: none;
    background-color: transparent;
    -webkit-text-decoration-skip: objects;
  }

  [role=button], a, area, button, input, label, select, summary, textarea {
    -ms-touch-action: manipulation;
    touch-action: manipulation;
  }

  button, input, optgroup, select, textarea {
    margin: 0;
    font-family: inherit;
    font-size: inherit;
    line-height: inherit;
  }

  button, input {
    overflow: visible;
  }

  a {
    font-size: 13px;
    color: #151515;
  }

  a {
    font-size: 14px;
  }

  [role=button], a, area, button, input, label, select, summary, textarea {
    -ms-touch-action: manipulation;
    touch-action: manipulation;
  }

  button, input, optgroup, select, textarea {
    margin: 0;
    font-family: inherit;
    font-size: inherit;
    line-height: inherit;
  }

  button, input {
    overflow: visible;
  }

  input {
    outline: none;
  }

  *:focus {
    outline: none;
  }

  *:focus {
    outline: none;
  }

  .search-special-input {
    z-index: 100;
  }

  .search-location-input {
    z-index: 100;
  }

  #searching-form input {
    width: 320px;
    margin: 0 5px 15px 0;
    padding: 8px 4px 8px 35px;
    line-height: 0.9em;
    border-radius: 4px;
    border: 1px solid var(--border-color);
  }

  .dropdown-menus.search {
    background-color: white;
    z-index: 999;
    position: relative;
    max-height: 300px;
    overflow-x: hidden;
    overflow-y: scroll;
    width: 317px;
    position: absolute;
    top: 68%;
    left: 1px;
    display: none;
    float: left;
    min-width: 10rem;
    margin: .125rem 0 0;
    font-size: 1rem;
    color: #212529;
    text-align: left;
    list-style: none;
    border-bottom: 4px solid #009999;
    border-radius: 0 0 .25rem .25rem;
  }

  .dropdown-menus.search {
    z-index: 101;
  }

  .category {
    margin: 10px 0;
  }

  .dropdown-menus.search :nth-child(1).category {
    margin-top: 0px;
  }


  .item-search, .item-search-header {
    padding: 0px 7px;
    transition: .2s;
    cursor: pointer;
    color: #212529 !important;
    display: block;
    text-decoration: none;
    border-bottom: 1px solid transparent;
    border-top: 1px solid transparent;
  }

  svg {
    overflow: hidden;
    vertical-align: middle;
  }

  .search-special-icon.second {
    z-index: 110;
  }

  .item-metro {
    padding-top: 8px;
  }

  .category.metro-wrap :nth-child(1).item-search {
    background: none;
    cursor: pointer;
  }

  .metro-6a, .metro-6a-background {
    background-color: #ff3366;
  }

  .metro-6, .metro-6-background {
    background-color: #3399cc;
  }

  .metro-1, .metro-d1-background {
    background-color: #f6a800;
  }

  .metro-7, .metro-7-background {
    background-color: #8F479D;
  }

  .metro-9, .metro-9-background {
    background-color: #798ea2;
  }

  .metro-6b, .metro-6b-background {
    background-color: #F48335;
  }

  .metro-1, .metro-1-background {
    background-color: #EE2D24;
  }

  .metro-2, .metro-2-background {
    background-color: #029A55;
  }

  .point {
    width: 10px;
    height: 10px;
    border-radius: 100%;
    position: relative;
    margin-right: 10px;
    margin-bottom: 15px;
    top: 8px;
    float: left;
  }

  .metro-name, .metro-addr {
    color: #222224;
    font-size: 14px;
  }

  .metro-name {
    font-size: 1em;
    font-family: "OpenSans Bold", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
    padding: 0;
    color: #000;
  }

  .metro-name.drops {
    line-height: inherit;
  }

  .item-metro span {
    color: var(--gray);
  }

  .metro-name span {
    font-size: 14px;
  }

</style>
