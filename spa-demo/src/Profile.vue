<template>
  <h1>My Profile</h1>
</template>

<script>
  import { authService } from './main';

  export default {
    beforeRouteEnter(to, from, next) {
      if ( !authService.isLoggedIn ) {
        alert('You must be logged in to perform that action.');
        return next(false);
      }

      return next();
    }
  }
</script>
