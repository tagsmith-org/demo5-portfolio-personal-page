<template>
    <section class="section-padding min-h-screen flex items-center justify-center">
        <div class="container-max text-center">
            <div class="animate-fade-in-up">
                <!-- Profile Photo -->
                <div class="mb-8">
                    <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=200&h=200&fit=crop&crop=face"
                        alt="Profile Photo"
                        class="w-32 h-32 rounded-full mx-auto object-cover border-4 border-white shadow-lg" />
                </div>

                <!-- Name and Profession -->
                <h1 class="text-4xl md:text-6xl font-bold text-text mb-4">
                    Alex Johnson
                </h1>
                <h2 class="text-xl md:text-2xl text-accent font-medium mb-6">
                    Full Stack Developer & UI/UX Designer
                </h2>

                <!-- Description -->
                <p class="text-lg text-gray-600 max-w-2xl mx-auto mb-8 leading-relaxed">
                    Passionate about creating beautiful, functional, and user-centered digital experiences.
                    I specialize in modern web technologies and love turning complex problems into simple,
                    elegant solutions.
                </p>

                <!-- CTA Buttons -->
                <div class="flex flex-col sm:flex-row gap-4 justify-center">
                    <button @click="scrollToPortfolio" class="btn-primary">
                        View My Work
                    </button>
                    <button class="btn-secondary">
                        Download Resume
                    </button>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
function scrollToPortfolio() {
    const portfolioSection = document.getElementById('portfolio')
    
    if (portfolioSection) {
        portfolioSection.scrollIntoView({ 
            behavior: 'smooth',
            block: 'start'
        })
    }
}
</script>
