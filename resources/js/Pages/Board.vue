<script setup>
import { Icon } from '@iconify/vue';
import {Menu, MenuButton, MenuItem, MenuItems} from '@headlessui/vue';

</script>
<template>
  <div class="flex flex-col h-screen bg-blue-600">
    <header class="shrink-0 flex justify-between bg-white px-4 py-3">
      <a class="text-2xl font-black tracking-tight" href="/">kanboard</a>
      <nav class="flex items-center">
        <a class="text-sm font-medium px-3 py-2 rounded-md hover:bg-gray-100" href="#">My boards</a>

        <Menu as="div" class="ml-3 relative z-10">
          <MenuButton class="focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-400 rounded-full">
            <img class="h-9 w-9 inline rounded-full" src="https://pbs.twimg.com/profile_images/1333896976602193922/MtWztkxt_400x400.jpg" alt="">
          </MenuButton>

          <transition
            enter-active-class="transition transform duration-100 ease-out"
            enter-from-class="opacity-0 scale-90"
            enter-to-class="opacity-100 scale-100"
            leave-active-class="transition transform duration-100 ease-in"
            leave-from-class="opacity-100 scale-100"
            leave-to-class="opacity-0 scale-90"
          >
            <MenuItems class="origin-top-right mt-2 focus:outline-none absolute right-0 bg-white overflow-hidden rounded-md shadow-lg border w-48">
              <MenuItem v-slot="{active}">
                <a href="#" :class="{'bg-gray-100': active}" class="block px-4 py-2 text-sm text-gray-700">My Profile</a>
              </MenuItem>
              <MenuItem v-slot="{active}">
                <a href="#" :class="{'bg-gray-100': active}" class="block px-4 py-2 text-sm text-gray-700">Log out</a>
              </MenuItem>
            </MenuItems>
          </transition>
        </Menu>

      </nav>
    </header>

    <main class="flex-1 overflow-hidden">
      <div class="flex flex-col h-full">
        <div class="shrink-0 flex justify-between items-center p-4">
          <h1 class="text-2xl text-white font-bold">Board title</h1>
          <div>
            <button class="inline-flex items-center bg-white/10 hover:bg-white/20 px-3 py-2 font-medium text-sm text-white rounded-md">
              <Icon icon="pepicons-pop:dots-x" class="w-5 h-5" />
              <span class="ml-1">Settings</span>
            </button>
          </div>
        </div>
        <div class="flex-1 overflow-x-auto">
          <div class="inline-flex h-full items-start px-4 pb-4 space-x-4">
            <div
            v-for="item in Array.from({length: 3})"
            class="w-72 bg-gray-200 max-h-full flex flex-col rounded-md">
              <div class="flex items-center justify-between px-3 py-2">
                <h3 class="text-sm font-semibold text-gray-700">Backlog</h3>
                <Menu as="div" class="relative z-10">
                  <MenuButton class="hover:bg-gray-300 w-8 h-8 rounded-md grid place-content-center">
                    <Icon icon="pepicons-pop:dots-x" class="w-5 h-5" />
                  </MenuButton>

                  <transition
                    enter-active-class="transition transform duration-100 ease-out"
                    enter-from-class="opacity-0 scale-90"
                    enter-to-class="opacity-100 scale-100"
                    leave-active-class="transition transform duration-100 ease-in"
                    leave-from-class="opacity-100 scale-100"
                    leave-to-class="opacity-0 scale-90"
                  >
                    <MenuItems class="origin-top-left mt-2 focus:outline-none absolute left-0 bg-white overflow-hidden rounded-md shadow-lg border w-40">
                      <MenuItem v-slot="{active}">
                        <a href="#" :class="{'bg-gray-100': active}" class="block px-4 py-2 text-sm text-gray-700">Add card</a>
                      </MenuItem>
                      <MenuItem v-slot="{active}">
                        <a href="#" :class="{'bg-gray-100': active}" class="block px-4 py-2 text-sm text-red-600">Delete list</a>
                      </MenuItem>
                    </MenuItems>
                  </transition>
                </Menu>
              </div>
              <div class="pb-3 flex flex-col overflow-hidden">
                <div class="px-3 flex-1 overflow-y-auto">
                  <ul class="space-y-3">
                  <li
                  v-for="item in Array.from({length: 100})"
                  class="group relative bg-white p-3 shadow rounded-md border-b border-gray-300 hover:bg-gray-500">
                    <a href="" class="text-sm">Card item</a>
                    <button class="hidden absolute top-1 right-1 w-8 h-8 bg-gray-50 group-hover:grid place-content-center rounded-md text-gray-600 hover:text-black hover:bg-gray-200">
                      <Icon icon="mdi:pencil" class="w-5 h-5"/>
                    </button>
                  </li>
                  <li class="group relative bg-white p-3 shadow rounded-md border-b border-gray-300 hover:bg-gray-500">
                    <a href="" class="text-sm">Card item</a>
                    <button class="hidden absolute top-1 right-1 w-8 h-8 bg-gray-50 group-hover:grid place-content-center rounded-md text-gray-600 hover:text-black hover:bg-gray-200">
                      <Icon icon="mdi:pencil" class="w-5 h-5"/>
                    </button>
                  </li>
                </ul>
                </div>
                <div class="px-3 mt-3">
                  <button class="flex items-center p-2 text-sm font-medium text-gray-600 hover:bg-gray-600 hover:text-black hover:bg-gray-300 w-full rounded-md">
                    <Icon icon="ic:baseline-plus" class="h-5 w-5"/>
                    <span class="ml-1">Add card</span>
                  </button>
                </div>
              </div>
            </div>

            <div class="w-72">
                  <button class="flex items-center bg-white/10 w-full hover:bg-white/20 text-white p-2 text-sm font-medium rounded-md">
                    <Icon icon="ic:baseline-plus" class="h-5 w-5"/>
                    <span class="ml-1">Add another list</span>
                  </button>
                </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>



