<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <button v-on:click="upload">upload!!!!</button>
  </div>
</template>

<script>
import { getFirestore, collection, addDoc } from "firebase/firestore";

async function hoge() {
  const db = getFirestore();

  try {
    const docRef = await addDoc(collection(db, "users"), {
      first: "Ada",
      last: "Lovelace",
      born: 1815
    });
    console.log("Document written with ID: ", docRef.id);
  } catch (e) {
    console.error("Error adding document: ", e);
  }
}

export default {
  name: 'Home',
  methods: {
    upload (){
      hoge()
    }
  }
}
</script>
