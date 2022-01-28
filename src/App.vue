<template>
  <router-view/>
</template>

<script>
import { initializeApp } from "firebase/app";
import { getAnalytics,logEvent } from "firebase/analytics";
// 以下firebase
const firebaseConfig = {
    apiKey: "***",
    authDomain: "***",
    projectId: "***",
    storageBucket: "***",
    messagingSenderId: "***",
    appId: "***",
    measurementId: "***"
};

const app = initializeApp(firebaseConfig);

const analytics = getAnalytics(app);
logEvent(analytics, 'notification_received');

export default {
  name: "app"
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
