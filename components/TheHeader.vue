<template>
  <div>
    <nav
      class="
        flex flex-col
        text-center
        sm:flex-row sm:text-left sm:justify-between
        py-4
        px-6
        bg-white
        shadow
        sm:items-baseline
        w-full
      "
    >
      <div class="mb-2 sm:mb-0">
        <a class="text-2xl no-underline text-grey-darkest hover:text-blue-dark"
          >Refinitiv</a
        >
      </div>
      <div>
        <Nuxt-Link to="/">
          <a
            class="
              text-lg
              no-underline
              text-grey-darkest
              hover:text-blue-dark
              ml-2
            "
            >Quiz1</a
          ></Nuxt-Link
        >
        <Nuxt-Link to="/quizTwo">
          <a
            class="
              text-lg
              no-underline
              text-grey-darkest
              hover:text-blue-dark
              ml-2
            "
            >Quiz2</a
          ></Nuxt-Link
        >
      </div>
    </nav>
  </div>
</template>