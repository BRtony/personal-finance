<template>
  <v-app-bar flat>
    <v-app-bar-title>
      <v-btn icon @click="toggleTheme">
        <v-icon>{{ darkMode ? 'mdi-white-balance-sunny' : 'mdi-weather-night' }}</v-icon>
      </v-btn>

      Personal finance
    </v-app-bar-title>
  </v-app-bar>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { useTheme } from 'vuetify'

const darkMode = ref(false)
const theme = useTheme()
const toggleTheme = () => {
  darkMode.value = !darkMode.value
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
</script>
