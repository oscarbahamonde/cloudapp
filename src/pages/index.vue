<script setup lang="ts">
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/hi/${encodeURIComponent(name)}`)
}
</script>

<template>
  <div>
    <div text-4xl>
     <img src="https://smartpro.solutions/public/logo.svg" alt="CloudApp" m-auto w-32 h-32/>
    </div>
    <p>
      <a rel="noreferrer" href="https://dev-znga30kp.us.auth0.com/login?state=hKFo2SBLbjVFQnM2ZXdpNWg4NERuUFVBV2pxWWQycHhCY0dfT6FupWxvZ2luo3RpZNkgNHFMYmowdlltblhncHZqc1FLMnRhU3ZLaG1UZDFFcm6jY2lk2SA5S3pXV1Q2Z1FPckttcU1icURiVVlIa3ZtQnRBdWUyRw&client=9KzWWT6gQOrKmqMbqDbUYHkvmBtAue2G&protocol=oauth2&prompt=consent&response_type=code&redirect_uri=https%3A%2F%2Fmanage.auth0.com%2Ftester%2Fcallback%3Fconnection%3Dgoogle-oauth2&scope=openid%20profile" target="_blank ">
      CloudApp
      </a>
    </p>
   <div py-4 />

    <input
      id="input"
      v-model="name"
      placeholder="john.doe@example.com"
      type="email"
      autocomplete="true"
      p="x4 y2"
      w="250px"
      text="center"
      bg="transparent"
      border="~ rounded gray-200 dark:gray-700"
      outline="none active:none"
      @keydown.enter="go"
    >
    <label class="hidden" for="input">Please put your Email</label>

    <div>
      <button
        btn m-3 text-sm
        :disabled="!name"
        @click="go"
      >
        Register
      </button>
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
