<!--
  This example requires Tailwind CSS v2.0+

  This example requires some changes to your config:

  ```
  // tailwind.config.js
  module.exports = {
    // ...
    plugins: [
      // ...
      require('@tailwindcss/forms'),
    ],
  }
  ```
-->
<template>
  <Disclosure as="nav" class="bg-gray-800" v-slot="{ open }">
    <div class="px-2 mx-auto max-w-7xl sm:px-4 lg:px-8">
      <div class="relative flex items-center justify-between h-16">
        <div class="flex items-center px-2 lg:px-0">
          <div class="flex-shrink-0">
            <img class="block w-auto h-8 lg:hidden" src="/images/logos/badge.png" alt="Rovtech Solutions Ltd. Logo" />
            <img class="hidden w-auto h-8 lg:block" src="/images/logos/logo-sd.png" alt="Rovtech Solutions Ltd. Logo" />
          </div>
          <div class="hidden lg:block lg:ml-6">
            <div class="flex space-x-4">
              <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
              <a href="#" class="px-3 py-2 text-sm font-medium text-white bg-gray-900 rounded-md">Dashboard</a>
              <a href="#" class="px-3 py-2 text-sm font-medium text-gray-300 rounded-md hover:bg-gray-700 hover:text-white">Team</a>
              <a href="#" class="px-3 py-2 text-sm font-medium text-gray-300 rounded-md hover:bg-gray-700 hover:text-white">Projects</a>
              <a href="#" class="px-3 py-2 text-sm font-medium text-gray-300 rounded-md hover:bg-gray-700 hover:text-white">Calendar</a>
            </div>
          </div>
        </div>
        <div class="flex justify-center flex-1 px-2 lg:ml-6 lg:justify-end">
          <div class="w-full max-w-lg lg:max-w-xs">
            <label for="search" class="sr-only">Search</label>
            <div class="relative">
              <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                <SearchIcon class="w-5 h-5 text-gray-400" aria-hidden="true" />
              </div>
              <input id="search" name="search" class="block w-full py-2 pl-10 pr-3 leading-5 text-gray-300 placeholder-gray-400 bg-gray-700 border border-transparent rounded-md focus:outline-none focus:bg-white focus:border-white focus:ring-white focus:text-gray-900 sm:text-sm" placeholder="Search" type="search" />
            </div>
          </div>
        </div>
        <div class="flex lg:hidden">
          <!-- Mobile menu button -->
          <DisclosureButton class="inline-flex items-center justify-center p-2 text-gray-400 rounded-md hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
            <span class="sr-only">Open main menu</span>
            <MenuIcon v-if="!open" class="block w-6 h-6" aria-hidden="true" />
            <XIcon v-else class="block w-6 h-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
        <div class="hidden lg:block lg:ml-4">
          <div class="flex items-center">
            <button type="button" class="flex-shrink-0 p-1 text-gray-400 bg-gray-800 rounded-full hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
              <span class="sr-only">View notifications</span>
              <BellIcon class="w-6 h-6" aria-hidden="true" />
            </button>

            <!-- Profile dropdown -->
            <Menu as="div" class="relative flex-shrink-0 ml-4">
              <div>
                <MenuButton class="flex text-sm text-white bg-gray-800 rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
                  <span class="sr-only">Open user menu</span>
                  <img class="w-8 h-8 rounded-full" src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
                </MenuButton>
              </div>
              <transition enter-active-class="transition duration-100 ease-out" enter-from-class="transform scale-95 opacity-0" enter-to-class="transform scale-100 opacity-100" leave-active-class="transition duration-75 ease-in" leave-from-class="transform scale-100 opacity-100" leave-to-class="transform scale-95 opacity-0">
                <MenuItems class="absolute right-0 w-48 py-1 mt-2 origin-top-right bg-white rounded-md shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
                  <MenuItem v-slot="{ active }">
                    <a href="#" :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">Your Profile</a>
                  </MenuItem>
                  <MenuItem v-slot="{ active }">
                    <a href="#" :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">Settings</a>
                  </MenuItem>
                  <MenuItem v-slot="{ active }">
                    <a href="#" :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">Sign out</a>
                  </MenuItem>
                </MenuItems>
              </transition>
            </Menu>
          </div>
        </div>
      </div>
    </div>

    <DisclosurePanel class="lg:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
        <DisclosureButton as="a" href="#" class="block px-3 py-2 text-base font-medium text-white bg-gray-900 rounded-md">Dashboard</DisclosureButton>
        <DisclosureButton as="a" href="#" class="block px-3 py-2 text-base font-medium text-gray-300 rounded-md hover:bg-gray-700 hover:text-white">Team</DisclosureButton>
        <DisclosureButton as="a" href="#" class="block px-3 py-2 text-base font-medium text-gray-300 rounded-md hover:bg-gray-700 hover:text-white">Projects</DisclosureButton>
        <DisclosureButton as="a" href="#" class="block px-3 py-2 text-base font-medium text-gray-300 rounded-md hover:bg-gray-700 hover:text-white">Calendar</DisclosureButton>
      </div>
      <div class="pt-4 pb-3 border-t border-gray-700">
        <div class="flex items-center px-5">
          <div class="flex-shrink-0">
            <img class="w-10 h-10 rounded-full" src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
          </div>
          <div class="ml-3">
            <div class="text-base font-medium text-white">Tom Cook</div>
            <div class="text-sm font-medium text-gray-400">tom@example.com</div>
          </div>
          <button type="button" class="flex-shrink-0 p-1 ml-auto text-gray-400 bg-gray-800 rounded-full hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
            <span class="sr-only">View notifications</span>
            <BellIcon class="w-6 h-6" aria-hidden="true" />
          </button>
        </div>
        <div class="px-2 mt-3 space-y-1">
          <DisclosureButton as="a" href="#" class="block px-3 py-2 text-base font-medium text-gray-400 rounded-md hover:text-white hover:bg-gray-700">Your Profile</DisclosureButton>
          <DisclosureButton as="a" href="#" class="block px-3 py-2 text-base font-medium text-gray-400 rounded-md hover:text-white hover:bg-gray-700">Settings</DisclosureButton>
          <DisclosureButton as="a" href="#" class="block px-3 py-2 text-base font-medium text-gray-400 rounded-md hover:text-white hover:bg-gray-700">Sign out</DisclosureButton>
        </div>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<script>
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { SearchIcon } from '@heroicons/vue/solid'
import { BellIcon, MenuIcon, XIcon } from '@heroicons/vue/outline'

export default {
  components: {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    Menu,
    MenuButton,
    MenuItem,
    MenuItems,
    BellIcon,
    MenuIcon,
    SearchIcon,
    XIcon,
  },
}
</script>
