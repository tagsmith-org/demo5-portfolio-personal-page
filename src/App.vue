<template>
    <div class="min-h-screen bg-background">
        <HeroSection />
        <PortfolioSection />
        <SkillsSection />
        <TestimonialsSection />
        <ContactSection />
    </div>
</template>

<script setup lang="ts">
import HeroSection from './components/HeroSection.vue'
import PortfolioSection from './components/PortfolioSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import ContactSection from './components/ContactSection.vue'
</script>
