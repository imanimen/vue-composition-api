<template>
  <Navbar/>
  <Hero title="Test Title" subTitle="Become a Vue Dev"/>
  <HomeCards/>
  <JobList/>
</template>

<script setup>
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import HomeCards from './components/HomeCards.vue';
import JobList from './components/JobList.vue';
</script>