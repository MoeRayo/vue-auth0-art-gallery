<template>
  <div>
    <div class=" pv4 ph3 ">
      <img class="br-100 ba b--gold bw3 db center" :src="$auth.user.picture">
      <h2 class="tc black-70 pv3">{{ $auth.user.name }}</h2>
    </div>
  </div>
</template>