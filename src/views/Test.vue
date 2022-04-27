<template>
    <div class="p-6">
        <div class="p-3 bg-white border border-gray-100 rounded-md bg-opacity-80 bg-clip-padding backdrop-filter backdrop-blur-md">
            <ul class="divide-y divide-gray-200">
                <li v-for="person in people" :key="person.email" class="flex py-4">
                    <img class="w-10 h-10 rounded-full" :src="person.image" alt="" />
                    <div class="ml-3">
                        <p class="text-sm font-medium text-gray-900">{{ person.name }}</p>
                        <p class="text-sm text-gray-500">{{ person.email }}</p>
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
const people = [
  {
    name: 'Stephan Phelps',
    email: 'steve@rovtechsolutions.co.uk',
    image:
      'https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
  },
  {
    name: 'Barry Vernon',
    email: 'barry@rovtechsolutions.co.uk',
    image:
      'https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
  },
  {
    name: 'Graham McAvoy',
    email: 'gmcav@rovtechsolutions.co.uk',
    image:
      'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
  },
]

export default {
  setup() {
    return {
      people,
    }
  },
}
</script>
