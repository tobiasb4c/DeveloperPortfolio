<script setup>
// save dropdown value in local Storage
const themeCookie = useCookie('theme', {
  maxAge: 24 * 60 * 60 * 365,
  secure: true
})
const activeTheme = reactive(themeCookie || 'default')

// function to change theme
function changeTheme () {
  console.log(activeTheme.value)
  console.log('Saving Theme in Cookie')
  themeCookie.value = activeTheme.value
  console.log(themeCookie.value)
}
</script>
<template>
  <div class="dropdown mb-72" @change="changeTheme">
    <div tabindex="0" role="button" class="btn m-1">
      Theme
      <svg
        width="12px"
        height="12px"
        class="h-2 w-2 fill-current opacity-60 inline-block"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 2048 2048"
      >
        <path
          d="M1799 349l242 241-1017 1017L7 590l242-241 775 775 775-775z"
        ></path>
      </svg>
    </div>
    <ul
      tabindex="0"
      class="dropdown-content z-[1] p-2 shadow-2xl bg-base-300 rounded-box w-52"
    >
      <li>
        <input
          type="radio"
          name="theme-dropdown"
          class="theme-controller btn btn-sm btn-block btn-ghost justify-start"
          aria-label="Light"
          value="light"
          v-model="activeTheme"
        />
      </li>
      <li>
        <input
          type="radio"
          name="theme-dropdown"
          class="theme-controller btn btn-sm btn-block btn-ghost justify-start"
          aria-label="Dark"
          value="dark"
          v-model="activeTheme"
        />
      </li>
      <li>
        <input
          type="radio"
          name="theme-dropdown"
          class="theme-controller btn btn-sm btn-block btn-ghost justify-start"
          aria-label="Retro"
          value="retro"
          v-model="activeTheme"
        />
      </li>
      <li>
        <input
          type="radio"
          name="theme-dropdown"
          class="theme-controller btn btn-sm btn-block btn-ghost justify-start"
          aria-label="Cyberpunk"
          value="cyberpunk"
          v-model="activeTheme"
        />
      </li>
      <li>
        <input
          type="radio"
          name="theme-dropdown"
          class="theme-controller btn btn-sm btn-block btn-ghost justify-start"
          aria-label="Valentine"
          value="valentine"
          v-model="activeTheme"
        />
      </li>
      <li>
        <input
          type="radio"
          name="theme-dropdown"
          class="theme-controller btn btn-sm btn-block btn-ghost justify-start"
          aria-label="Aqua"
          value="aqua"
          v-model="activeTheme"
        />
      </li>
    </ul>
  </div>
</template>
