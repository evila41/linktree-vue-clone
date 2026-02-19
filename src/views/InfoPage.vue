<script setup>
import { ref } from 'vue'

const bio = ref({
  name: 'Elias Villarreal',
  avatar:
    'https://api.dicebear.com/9.x/avataaars/svg?seed=Jack&accessories=sunglasses&accessoriesColor=25557c&accessoriesProbability=90&clothesColor=25557c&clothing=hoodie&clothingGraphic=pizza&eyebrows=defaultNatural&eyes=default&facialHair[]&facialHairColor[]&facialHairProbability=0&hairColor=4a312c&hatColor[]&mouth=twinkle&skinColor=edb98a&top=shortFlat&backgroundColor=c0aede',
  about: `I'm a student at South Texas College learning about Javascript and Web Development. It is a fun and interactive experience to further my knowledge in this field.`,
  skills: ['Vue.js', 'React', 'Typescript', 'Node.js', 'Tailwind CSS'],
  email: 'evilla41@southtexascollege.edu',
  location: 'Austin, Tx',
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center bg-indigo-950 px-4 py-8 sm:py-12">
    <RouterLink
      to="/"
      class="my-8 self-start text-sm text-indigo-400 underline-offset-4 transition-colors duration-200 hover:text-cyan-400 hover:underline"
    >
      ← Back to Links
    </RouterLink>

    <!-- Profile Card -->
    <div
      class="w-full max-w-lg rounded-2xl border border-indigo-700 bg-indigo-900 p-6 shadow-xl shadow-indigo-900/50 sm:p-8"
    >
      <!-- Header -->
      <div class="mb-6 flex flex-col items-center text-center sm:flex-row sm:text-left">
        <div
          class="mb-4 h-20 w-20 shrink-0 overflow-hidden rounded-full border-4 border-cyan-400 shadow-lg shadow-cyan-500/30 sm:mr-6 sm:mb-0"
        >
          <img
            :src="bio.avatar"
            :alt="bio.name"
            class="h-full w-full object-cover"
          />
        </div>

        <div>
          <h1 class="mb-1 font-display text-2xl font-bold text-white">
            {{ bio.name }}
          </h1>
          <p class="text-sm text-indigo-300">📍 {{ bio.location }}</p>
        </div>
      </div>

      <!-- About Section -->
      <div class="mb-6">
        <h2 class="mb-3 text-lg font-semibold text-white">About</h2>
        <p class="leading-relaxed text-indigo-200">
          {{ bio.about }}
        </p>
      </div>

      <!-- Skills Section -->
      <div class="mb-6">
        <h2 class="mb-3 text-lg font-semibold text-white">Skills</h2>
        <div class="flex flex-wrap gap-2">
          <span
            v-for="skill in bio.skills"
            :key="skill"
            class="rounded-full border border-cyan-500/20 bg-cyan-900/40 px-3 py-1 text-sm text-cyan-300"
          >
            {{ skill }}
          </span>
        </div>
      </div>

      <!-- Contact -->
      <div>
        <h2 class="mb-3 text-lg font-semibold text-white">Get in Touch</h2>
        <a
          :href="`mailto:${bio.email}`"
          class="group inline-flex items-center gap-2 rounded-xl bg-cyan-500 px-6 py-3 font-medium text-indigo-950 shadow-lg shadow-cyan-500/30 transition-all duration-200 hover:scale-105 hover:bg-cyan-400 hover:shadow-xl hover:shadow-cyan-500/40 active:scale-95"
        >
          <svg
            fill="none"
            stroke-width="1.5"
            stroke="currentColor"
            viewBox="0 0 24 24"
            class="h-5 w-5 transition-transform duration-200 group-hover:rotate-12"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75"
            ></path>
          </svg>
          Send Email
        </a>
      </div>
    </div>
  </main>
</template>
