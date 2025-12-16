<script setup lang="ts">
// Layout padrão com header

// Estado do modal sobre
const isAboutModalOpen = ref(false)

// Handler para abrir modal sobre
const handleOpenAbout = () => {
  isAboutModalOpen.value = true
}
</script>

<template>
  <div class="min-h-screen bg-gray-50 dark:bg-gray-900 flex flex-col">
    <!-- Header -->
    <AppHeader @open-about="handleOpenAbout" />

    <!-- Conteúdo principal -->
    <main class="flex-1">
      <slot />
    </main>

    <!-- Footer -->
    <UFooter class="border-t border-gray-200 dark:border-gray-800">
      <template #left>
        <p class="text-sm text-gray-600 dark:text-gray-400">
          Awk Chat - Assistente de IA, Suporte Omnicanal
        </p>
      </template>

      <template #right>
        <div class="flex items-center space-x-4">
          <a 
            href="https://awkchat.com.br/"
            target="_blank"
            rel="noopener noreferrer"
            class="text-gray-600 dark:text-gray-400 hover:text-red-600 dark:hover:text-red-400 transition-colors"
            aria-label="Acesse Awk Chat"
          >
            <i data-lucide="circle-chevron-down" class="w-5 h-5" />
          </a>
        </div>
      </template>
    </UFooter>

    <!-- Modal Sobre -->
    <AboutModal v-model:open="isAboutModalOpen" />
  </div>
</template>
