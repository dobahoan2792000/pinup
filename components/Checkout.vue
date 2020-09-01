<template>
  <div class="w-full flex justify-center">
    <!-- Control width -->
    <div class="w-11/12 sm:w-10/12">
      <!-- Coupon -->
      <div class="w-full mb-10">
        <div
          class="flex justify-center items-center px-5 py-4 border border-gray-300 leading-7"
        >
          <span
            class="font-mon text-sm text-gray-600 sm:flex sm:justify-between sm:w-full xl:text-xs"
            >Have a coupon?
            <span
              class="cursor-pointer font-mon text-sm text-gray-600 xl:text-xs"
              @click="isDisplay = !isDisplay"
              >Click here to enter your code</span
            ></span
          >
        </div>
        <div
          class="transition-all duration-300"
          :class="
            isDisplay ? 'h-56 visible opacity-100' : 'h-0 invisible opacity-0'
          "
        >
          <div class="py-6">
            <p class="font-mon text-sm text-gray-600 xl:text-xs">
              If you have a coupon code, please apply it below.
            </p>
            <input
              type="text"
              placeholder="Coupon code"
              class="text-xs font-mon py-4 border-b border-black outline-none w-full"
            />
            <p
              class="px-5 py-3 border border-black uppercase font-mon tracking-widest text-xs text-gray-600 mt-8 inline-block"
            >
              Apply coupon
            </p>
          </div>
        </div>
      </div>
      <!-- Đăng ký -->
      <div class="md:flex">
        <!-- Billing details -->
        <form class="md:w-1/2 md:mr-2">
          <h3 class="font-vida text-xl xl:text-2xl">Billing details</h3>
          <!-- firstname and lastname -->
          <div class="sm:flex sm:w-full md:mt-8">
            <!-- firstname -->
            <div class="mt-5 sm:mt-0 sm:w-1/2 sm:mr-1">
              <label
                for="fname"
                class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
                >First name <abbr title="required">*</abbr></label
              >
              <input
                id="fname"
                type="text"
                class="py-4 border-b border-black w-full outline-none text-xs font-mon"
              />
            </div>
            <!-- lastname -->
            <div class="mt-5 sm:mt-0 sm:w-1/2 sm:ml-1">
              <label
                for="lname"
                class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
                >Last name <abbr title="required">*</abbr></label
              >
              <input
                id="lname"
                type="text"
                class="py-4 border-b border-black w-full outline-none text-xs font-mon"
              />
            </div>
            <!-- companyname -->
          </div>
          <div class="mt-5">
            <label
              for="cpn"
              class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
              >Company name (optional)</label
            >
            <input
              id="cpn"
              type="text"
              class="py-4 border-b border-black w-full outline-none text-xs font-mon"
            />
          </div>
          <!-- country -->
          <div class="mt-5">
            <p class="font-mon text-sm text-gray-700 mb-2 xl:text-xs">
              Country / Region <abbr title="required">*</abbr>
            </p>
            <div class="flex justify-center border relative">
              <div
                class="flex w-11/12 justify-between items-center py-3 cursor-pointer"
                @click="displayCountries = !displayCountries"
              >
                <span class="font-mon text-sm xl:text-xs text-gray-700"
                  >Vietnam</span
                >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  aria-hidden="true"
                  focusable="false"
                  width="1em"
                  height="1em"
                  style="
                    -ms-transform: rotate(360deg);
                    -webkit-transform: rotate(360deg);
                    transform: rotate(360deg);
                  "
                  preserveAspectRatio="xMidYMid meet"
                  viewBox="0 0 20 20"
                >
                  <path
                    d="M4.516 7.548c.436-.446 1.043-.481 1.576 0L10 11.295l3.908-3.747c.533-.481 1.141-.446 1.574 0c.436.445.408 1.197 0 1.615c-.406.418-4.695 4.502-4.695 4.502a1.095 1.095 0 0 1-1.576 0S4.924 9.581 4.516 9.163c-.409-.418-.436-1.17 0-1.615z"
                    fill="#626262"
                  />
                </svg>
              </div>
              <div
                class="absolute h-56 style-country flex flex-wrap justify-center bg-white border-b border-l border-r border-gray-300"
                :class="displayCountries ? 'block' : 'hidden'"
              >
                <input
                  type="text"
                  class="border outline-none w-11/12 mt-4 mb-3 font-mon text-sm text-gray-800"
                />
                <ul class="w-full pl-5 overflow-y-scroll h-40">
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Afghanistan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Åland Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Albania
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Algeria
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    American Samoa
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Andorra
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Angola
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Anguilla
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Antarctica
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Antigua and Barbuda
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Argentina
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Armenia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Aruba
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Australia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Austria
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Azerbaijan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bahamas
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bahrain
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bangladesh
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Barbados
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Belarus
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Belgium
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Belize
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Benin
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bermuda
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bhutan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bolivia, Plurinational State of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bonaire, Sint Eustatius and Saba
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bosnia and Herzegovina
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Botswana
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bouvet Island
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Brazil
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    British Indian Ocean Territory
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Brunei Darussalam
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Bulgaria
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Burkina Faso
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Burundi
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cambodia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cameroon
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Canada
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cape Verde
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cayman Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Central African Republic
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Chad
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Chile
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    China
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Christmas Island
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cocos (Keeling) Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Colombia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Comoros
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Congo
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Congo, the Democratic Republic of the
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cook Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Costa Rica
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Côte d'Ivoire
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Croatia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cuba
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Curaçao
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Cyprus
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Czech Republic
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Denmark
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Djibouti
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Dominica
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Dominican Republic
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Ecuador
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Egypt
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    El Salvador
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Equatorial Guinea
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Eritrea
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Estonia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Ethiopia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Faroe Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Fiji
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Falkland Islands (Malvinas)
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Finland
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    France
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    French Guiana
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    French Polynesia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    French Southern Territories
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Gabon
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Gambia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Georgia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Germany
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Ghana
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Gibraltar
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Greece
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Greenland
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Grenada
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Guadeloupe
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Guam
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Guatemala
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Guernsey
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Guinea
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Guinea-Bissau
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Guyana
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Haiti
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Heard Island and McDonald Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Holy See (Vatican City State)
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Honduras
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Hong Kong
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Hungary
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Iceland
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    India
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Indonesia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Iran, Islamic Republic of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Iraq
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Ireland
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Isle of Man
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Israel
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Italy
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Jamaica
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Japan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Jersey
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Jordan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Kazakhstan
                  </li>
                  <li />
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Kenya
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Kiribati
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Korea, Democratic People's Republic of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Korea, Republic of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Kuwait
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Kyrgyzstan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Lao People's Democratic Republic
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Latvia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Lebanon
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Lesotho
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Liberia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Libya
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Liechtenstein
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Lithuania
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Luxembourg
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Macao
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Macedonia, the former Yugoslav Republic of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Madagascar
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Malawi
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Malaysia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Maldives
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Mali
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Malta
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Marshall Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Martinique
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Mauritania
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Mauritius
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Mayotte
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Mexico
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Micronesia, Federated States of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Moldova, Republic of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Monaco
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Mongolia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Montenegro
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Montserrat
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Morocco
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Mozambique
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Myanmar
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Namibia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Nauru
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Nepal
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Netherlands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    New Caledonia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    New Zealand
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Nicaragua
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Niger
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Nigeria
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Niue
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Norfolk Island
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Northern Mariana Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Norway
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Oman
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Pakistan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Palau
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Palestinian Territory, Occupied
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Panama
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Papua New Guinea
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Paraguay
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Peru
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Philippines
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Pitcairn
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Poland
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Portugal
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Puerto Rico
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Qatar
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Réunion
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Romania
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Russian Federation
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Rwanda
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saint Barthélemy
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saint Helena, Ascension and Tristan da Cunha
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saint Kitts and Nevis
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saint Lucia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saint Martin (French part)
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saint Pierre and Miquelon
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saint Vincent and the Grenadines
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Samoa
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    San Marino
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Sao Tome and Principe
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Saudi Arabia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Senegal
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Serbia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Seychelles
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Sierra Leone
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Singapore
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Sint Maarten (Dutch part)
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Slovakia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Slovenia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Solomon Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Somalia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    South Africa
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    South Georgia and the South Sandwich Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Spain
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    South Sudan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Sri Lanka
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Sudan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Suriname
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Svalbard and Jan Mayen
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Swaziland
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Sweden
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Switzerland
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Syrian Arab Republic
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Taiwan, Province of China
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Tajikistan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Tanzania, United Republic of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Thailand
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Timor-Leste
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Togo
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Tokelau
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Tonga
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Trinidad and Tobago
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Tunisia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Turkey
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Turkmenistan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Turks and Caicos Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Tuvalu
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Uganda
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Ukraine
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    United Arab Emirates
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    United Kingdom
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    United States
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    United States Minor Outlying Islands
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Uruguay
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Uzbekistan
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Vanuatu
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Venezuela, Bolivarian Republic of
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Viet Nam
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Virgin Islands, British
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Virgin Islands, U.S.
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Wallis and Futuna
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Western Sahara
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Yemen
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Zambia
                  </li>
                  <li class="font-mon text-sm xl:text-xs text-gray-700 py-2">
                    Zimbabwe
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <!-- streetaddress -->
          <div class="mt-5">
            <label
              for="street"
              class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
              >Street address <abbr title="required">*</abbr></label
            >
            <input
              id="street"
              type="text"
              class="py-4 border-b border-black w-full outline-none text-xs font-mon"
              placeholder="House number and street name"
            />
          </div>
          <!-- postcode -->
          <div class="mt-5">
            <label
              for="postcode"
              class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
              >Postcode / ZIP (optional)</label
            >
            <input
              id="postcode"
              type="text"
              class="py-4 border-b border-black w-full outline-none text-xs font-mon"
              placeholder="House number and street name"
            />
          </div>
          <!-- Town / City -->
          <div class="mt-5">
            <label
              for="towncity"
              class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
              >Town / City <abbr title="required">*</abbr></label
            >
            <input
              id="towncity"
              type="text"
              class="py-4 border-b border-black w-full outline-none text-xs font-mon"
            />
          </div>
          <!-- phone -->
          <div class="mt-5">
            <label
              for="phone"
              class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
              >Phone <abbr title="required">*</abbr></label
            >
            <input
              id="phone"
              type="text"
              class="py-4 border-b border-black w-full outline-none text-xs font-mon xl:text-xs"
            />
          </div>
          <!-- email -->
          <div class="mt-5">
            <label
              for="phone"
              class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
              >Email address <abbr title="required">*</abbr></label
            >
            <input
              id="phone"
              type="text"
              class="py-4 border-b border-black w-full outline-none text-xs font-mon"
            />
          </div>
        </form>
        <!-- Additional information -->
        <div class="md:w-1/2 md:ml-2">
          <h3 class="font-vida text-xl mt-8 mb-3 md:mt-0 xl:text-2xl">
            Additional information
          </h3>
          <div class="mt-5">
            <label
              for="fname"
              class="block font-mon text-sm text-gray-700 mb-2 xl:text-xs"
              >Order notes (optional)</label
            >
            <textarea
              id="fname"
              class="py-4 border-b border-black w-full outline-none text-xs xl:text-xs font-mon text-black"
              placeholder="Notes about your order, e.g special notes for delivery"
            ></textarea>
          </div>
        </div>
      </div>
      <!-- your order -->
      <div>
        <h3 class="font-vida text-2xl mt-10 mb-6">Your order</h3>
        <!-- bill -->
        <table class="w-full">
          <tr class="border-b">
            <td class="font-vida text-base text-gray-800 py-3 xl:text-sm">
              Product
            </td>
            <td class="font-vida text-base text-gray-800 xl:text-sm">
              Subtotal
            </td>
          </tr>
          <!-- run v-for here -->
          <tr class="border-b">
            <td class="font-mon text-sm text-gray-800 py-3 xl:text-sm">
              Turquoise
            </td>
            <td class="font-mon text-sm text-gray-800 xl:text-sm">75</td>
          </tr>
          <!-- subtototal -->
          <tr class="border-b">
            <td class="font-vida text-base text-gray-800 py-3 xl:text-sm">
              Subtotal
            </td>
            <td class="font-mon text-sm text-gray-800 xl:text-sm">150</td>
          </tr>
          <!-- total -->
          <tr class="border-b">
            <td class="font-vida text-base text-gray-800 py-3 xl:text-sm">
              Total
            </td>
            <td class="font-mon text-sm text-gray-800 font-bold xl:text-sm">
              150
            </td>
          </tr>
        </table>
        <!-- delivery -->
        <div class="flex flex-wrap justify-center mt-6 relative">
          <div
            class="w-4/5 sm:w-11/12 md:w-full border-b pb-8 mt-4 px-4 transition-all duration-200"
            :class="isBank ? 'h-40 sm:h-32 lg:h-24' : 'h-16'"
          >
            <input
              id="bank"
              name="delivery"
              type="radio"
              checked
              @click="deliveryBank"
            />
            <label
              for="bank"
              class="font-mon text-sm text-gray-800 ml-1 xl:text-xs"
              >Direct bank transfer</label
            >
            <p
              class="absolute font-mon text-sm xl:text-xs text-gray-800 mt-4 transition-all duration-200"
              :class="isBank ? 'opacity-100' : 'opacity-0'"
            >
              Make your payment directly into our bank account. Please use your
              Order ID as the payment reference. Your order will not be shipped
              until the funds have cleared in our account.
            </p>
          </div>
          <div
            class="w-4/5 sm:w-11/12 md:w-full border-b pb-8 mt-8 px-4 transition-all duration-200"
            :class="isCash ? ' h-24' : 'h-16'"
          >
            <input
              id="cash"
              name="delivery"
              type="radio"
              @click="deliveryCash"
            />
            <label
              for="cash"
              class="font-mon text-sm text-gray-800 ml-1 xl:text-xs"
              >Direct bank transfer</label
            >
            <p
              class="absolute font-mon text-sm xl:text-xs text-gray-800 mt-4"
              :class="isCash ? 'opacity-100' : 'opacity-0'"
            >
              Pay with cash upon delivery.
            </p>
          </div>
          <!-- placeorder -->
          <div class="w-4/5 sm:w-11/12 md:w-full">
            <p class="mt-6 font-mon text-sm text-gray-700 xl:text-xs">
              Your personal data will be used to process your order, support
              your experience throughout this website, and for other purposes
              described in our <a href="#">privacy policy</a>
            </p>
            <a
              href="#"
              class="px-8 py-3 inline-block font-mon text-xs tracking-widest mt-3 uppercase border border-black"
              >Place order</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDisplay: false,
      isBank: true,
      isCash: false,
      displayCountries: false,
    }
  },
  methods: {
    deliveryBank() {
      this.isBank = true
      this.isCash = false
    },
    deliveryCash() {
      this.isBank = false
      this.isCash = true
    },
  },
}
</script>
<style scoped>
.style-country{
    width: calc(100% + 2px);
    left: -1px;
    margin-top: 45px;
}
</style>
