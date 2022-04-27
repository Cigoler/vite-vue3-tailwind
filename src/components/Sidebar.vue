<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="flex flex-col flex-1 min-h-0 bg-white border-r border-gray-200">
    <div class="flex flex-col flex-1 pt-5 pb-4 overflow-y-auto">
      <nav class="flex-1 px-2 space-y-1 bg-white" aria-label="Sidebar">
        <a v-for="item in navigation" :key="item.name" :href="item.href" :class="[item.current ? 'bg-gray-100 text-gray-900 hover:text-gray-900 hover:bg-gray-100' : 'text-gray-600 hover:text-gray-900 hover:bg-gray-50', 'group flex items-center px-2 py-2 text-sm font-medium rounded-md']">
          <component :is="item.icon" :class="[item.current ? 'text-gray-500' : 'text-gray-400 group-hover:text-gray-500', 'mr-3 flex-shrink-0 h-6 w-6']" aria-hidden="true" />
          <span class="flex-1 hidden sm:flex">
            {{ item.name }}
          </span>
          <span v-if="item.count" :class="[item.current ? 'bg-white' : 'bg-gray-100 group-hover:bg-gray-200', 'inline-block py-0.5 px-3 text-xs font-medium rounded-full']">
            {{ item.count }}
          </span>
        </a>
      </nav>
    </div>
    <div class="flex flex-shrink-0 p-4 border-t border-gray-200">
      <a href="#" class="flex-shrink-0 block w-full group">
        <div class="flex items-center">
          <div>
            <img class="inline-block rounded-full w-14 h-14" src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
          </div>
          <div class="ml-3">
            <p class="text-sm font-medium text-gray-700 group-hover:text-gray-900">Stephan Phelps</p>
            <p class="text-xs font-medium text-gray-500 group-hover:text-gray-700">View profile</p>
          </div>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
import { CalendarIcon, ChartBarIcon, FolderIcon, HomeIcon, InboxIcon, UsersIcon } from '@heroicons/vue/outline'

const navigation = [
  { name: 'Dashboard', icon: HomeIcon, href: '#', current: true },
  { name: 'Team', icon: UsersIcon, href: '#', count: 3, current: false },
  { name: 'Projects', icon: FolderIcon, href: '#', count: 4, current: false },
  { name: 'Calendar', icon: CalendarIcon, href: '#', current: false },
  { name: 'Documents', icon: InboxIcon, href: '#', count: 12, current: false },
  { name: 'Reports', icon: ChartBarIcon, href: '#', current: false },
]

export default {
  setup() {
    return {
      navigation,
    }
  },
}
</script>
