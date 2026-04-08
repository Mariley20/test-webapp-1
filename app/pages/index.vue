<script setup lang="ts">
import { ref } from 'vue'
import { Dialog, DialogPanel, DialogTitle, TransitionChild, TransitionRoot } from '@headlessui/vue'

// Assets from Figma
const heroBackground = "https://www.figma.com/api/mcp/asset/0e0d7bbd-40b9-4aa3-a2ee-f4059c18e967"
const logo = "https://www.figma.com/api/mcp/asset/bc6c8bb1-5210-456b-839b-c21c5d4b9bce"

const isMenuModalOpen = ref(false)
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <!-- Header -->
    <header class="bg-black flex items-center justify-between px-10 py-2 h-20">
      <nav class="flex items-center gap-8">
        <div class="flex items-center gap-6 text-black font-semibold">
          <a href="#" class="text-white hover:text-yellow-400">Nuestros favoritos</a>
          <a href="#" class="text-white hover:text-yellow-400">Galería</a>
          <a href="#" class="text-white hover:text-yellow-400">Reseñas</a>
        </div>
      </nav>
      
      <div class="flex items-center gap-4">
        <!-- Rating -->
        <div class="bg-white flex items-center gap-2 px-2 py-1.5 rounded shadow">
          <Icon name="lucide:star" class="w-4 h-4 text-yellow-400 fill-yellow-400" />
          <span class="font-bold text-black">4.5</span>
        </div>
        
        <!-- Status -->
        <div class="bg-white flex items-center gap-1 px-2 py-1.5 rounded shadow">
          <Icon name="lucide:circle-check" class="w-5 h-5 text-green-500" />
          <span class="font-bold text-black">Abierto</span>
        </div>
        
        <!-- CTA Button -->
        <button class="bg-yellow-400 hover:bg-yellow-500 text-black font-semibold px-4 py-3 rounded-lg w-28">
          Pedir
        </button>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="relative flex items-center justify-center gap-12 py-16 min-h-[491px]">
      <!-- Background -->
      <div class="absolute inset-0">
        <img :src="heroBackground" alt="" class="w-full h-full object-cover" />
        <div class="absolute inset-0 bg-black/70" />
      </div>
      
      <!-- Content Left -->
      <div class="relative z-10 flex flex-col gap-5 w-[504px]">
        <!-- Logo -->
        <div class="w-26 h-26 rounded-lg border border-white/50 overflow-hidden">
          <img :src="logo" alt="Logo" class="w-full h-full object-cover" />
        </div>
        
        <!-- Title & Description -->
        <div class="flex flex-col gap-4">
          <h1 class="text-4xl font-bold text-white leading-tight">
            Bienvenidos a las mejores pizzas
          </h1>
          <p class="text-white text-base max-w-[398px]">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce hendrerit.
          </p>
          
          <!-- Service Options -->
          <div class="flex items-center text-white">
            <div class="flex items-center gap-2 pr-4 border-r border-white/50">
              <Icon name="lucide:utensils" class="w-6 h-6" />
              <span>En sitio</span>
            </div>
            <div class="flex items-center gap-2 px-4 border-r border-white/50">
              <Icon name="lucide:shopping-bag" class="w-5 h-5" />
              <span>Para llevar</span>
            </div>
            <div class="flex items-center gap-2 px-4">
              <Icon name="lucide:bike" class="w-6 h-6" />
              <span>A Domicilio</span>
            </div>
          </div>
          
          <!-- Location -->
          <div class="flex items-center gap-2 text-white">
            <Icon name="lucide:map-pin" class="w-5 h-5" />
            <span>Av. Dirección del negocio</span>
          </div>
        </div>
      </div>
      
      <!-- CTA Buttons Right -->
      <div class="relative z-10 flex flex-col gap-4 w-[400px]">
        <button 
          @click="isMenuModalOpen = true"
          class="bg-yellow-400 hover:bg-yellow-500 text-black font-semibold text-xl py-4 rounded-lg w-full"
        >
          Menú
        </button>
        <button class="bg-yellow-400 hover:bg-yellow-500 text-black font-semibold text-xl py-4 rounded-lg w-full">
          WhatsApp
        </button>
        <button class="bg-yellow-400 hover:bg-yellow-500 text-black font-semibold text-xl py-4 rounded-lg w-full">
          Botón 3
        </button>
        <button class="bg-yellow-400 hover:bg-yellow-500 text-black font-semibold text-xl py-4 rounded-lg w-full">
          Botón 4
        </button>
      </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-50 flex items-center justify-between px-10 py-4">
      <div class="flex items-center gap-4">
        <!-- OlaClick branding -->
        <div class="flex flex-col gap-1">
          <span class="text-sm text-black">Crea tu menú digital con</span>
          <span class="font-bold text-black">OlaClick</span>
        </div>
        
        <!-- Footer Links -->
        <div class="flex items-center h-10 text-sm text-black">
          <span class="px-4 border-l border-r border-black/10">Menú digital de Pizza Restaurant</span>
          <span class="px-4 border-r border-black/10">Horarios</span>
          <span class="px-4 border-r border-black/10">Reportar algo</span>
          <div class="flex items-center gap-2 px-4">
            <Icon name="lucide:smartphone" class="w-5 h-5" />
            <span>Descargar Aplicación</span>
          </div>
        </div>
      </div>
      
      <!-- Social Media -->
      <div class="flex items-center gap-2">
        <button class="p-1 hover:bg-gray-200 rounded">
          <Icon name="lucide:message-circle" class="w-8 h-8 text-black" />
        </button>
        <button class="p-1 hover:bg-gray-200 rounded">
          <Icon name="lucide:instagram" class="w-8 h-8 text-black" />
        </button>
        <button class="p-1 hover:bg-gray-200 rounded">
          <Icon name="lucide:facebook" class="w-8 h-8 text-black" />
        </button>
        <button class="p-1 hover:bg-gray-200 rounded">
          <Icon name="lucide:music-2" class="w-8 h-8 text-black" />
        </button>
        <button class="p-1 hover:bg-gray-200 rounded">
          <Icon name="lucide:phone" class="w-8 h-8 text-black" />
        </button>
      </div>
    </footer>

    <!-- Menu Modal -->
    <TransitionRoot appear :show="isMenuModalOpen" as="template">
      <Dialog as="div" @close="isMenuModalOpen = false" class="relative z-50">
        <TransitionChild
          as="template"
          enter="duration-300 ease-out"
          enter-from="opacity-0"
          enter-to="opacity-100"
          leave="duration-200 ease-in"
          leave-from="opacity-100"
          leave-to="opacity-0"
        >
          <div class="fixed inset-0 bg-black/50" />
        </TransitionChild>

        <div class="fixed inset-0 overflow-y-auto">
          <div class="flex min-h-full items-center justify-center p-4">
            <TransitionChild
              as="template"
              enter="duration-300 ease-out"
              enter-from="opacity-0 scale-95"
              enter-to="opacity-100 scale-100"
              leave="duration-200 ease-in"
              leave-from="opacity-100 scale-100"
              leave-to="opacity-0 scale-95"
            >
              <DialogPanel class="w-full max-w-md rounded-2xl bg-white p-6 shadow-xl">
                <DialogTitle as="h3" class="text-xl font-bold text-gray-900">
                  Nuestro Menú
                </DialogTitle>
                
                <div class="mt-4 text-gray-600">
                  <p>Aquí se mostrará el menú de productos.</p>
                </div>

                <div class="mt-6">
                  <button
                    type="button"
                    @click="isMenuModalOpen = false"
                    class="w-full rounded-lg bg-yellow-400 px-4 py-3 font-semibold text-black hover:bg-yellow-500"
                  >
                    Cerrar
                  </button>
                </div>
              </DialogPanel>
            </TransitionChild>
          </div>
        </div>
      </Dialog>
    </TransitionRoot>
  </div>
</template>
