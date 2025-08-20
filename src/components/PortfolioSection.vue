<template>
    <section id="portfolio" class="section-padding bg-white">
        <div class="container-max">
            <!-- Section Header -->
            <div class="text-center mb-16 animate-fade-in-up">
                <h2 class="text-3xl md:text-4xl font-bold text-text mb-4">
                    My Portfolio
                </h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">
                    A collection of my recent work showcasing my skills in web development,
                    design, and problem-solving.
                </p>
            </div>

            <!-- Portfolio Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div v-for="(project, index) in projects" :key="project.id"
                    class="group bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-all duration-300 animate-fade-in-up"
                    :style="{ animationDelay: `${index * 0.1}s` }">
                    <!-- Project Image -->
                    <div class="relative overflow-hidden">
                        <img :src="project.image" :alt="project.title"
                            class="w-full h-48 object-cover group-hover:scale-105 transition-transform duration-300" />
                        <div
                            class="absolute inset-0 bg-black bg-opacity-0 group-hover:bg-opacity-20 transition-all duration-300">
                        </div>
                    </div>

                    <!-- Project Content -->
                    <div class="p-6">
                        <h3 class="text-xl font-semibold text-text mb-2">
                            {{ project.title }}
                        </h3>
                        <p class="text-gray-600 mb-4">
                            {{ project.description }}
                        </p>
                        <div class="flex flex-wrap gap-2 mb-4">
                            <span v-for="tech in project.technologies" :key="tech"
                                class="px-3 py-1 bg-gray-100 text-gray-700 text-sm rounded-full">
                                {{ tech }}
                            </span>
                        </div>
                        <div class="flex gap-3">
                            <button class="text-accent hover:text-accent/80 font-medium text-sm transition-colors">
                                View Project
                            </button>
                            <button class="text-gray-500 hover:text-gray-700 font-medium text-sm transition-colors">
                                Source Code
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
interface Project {
    id: number
    title: string
    description: string
    image: string
    technologies: string[]
}

const projects: Project[] = [
    {
        id: 1,
        title: "E-Commerce Platform",
        description: "A modern e-commerce platform built with Vue.js and Node.js, featuring real-time inventory management and payment processing.",
        image: "https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=400&h=300&fit=crop",
        technologies: ["Vue.js", "Node.js", "MongoDB", "Stripe"]
    },
    {
        id: 2,
        title: "Task Management App",
        description: "A collaborative task management application with real-time updates, drag-and-drop functionality, and team collaboration features.",
        image: "https://images.unsplash.com/photo-1484480974693-6ca0a78fb36b?w=400&h=300&fit=crop",
        technologies: ["React", "Firebase", "TypeScript", "Tailwind"]
    },
    {
        id: 3,
        title: "Weather Dashboard",
        description: "A beautiful weather dashboard with location-based forecasts, interactive maps, and detailed weather analytics.",
        image: "https://images.unsplash.com/photo-1592210454359-9043f067919b?w=400&h=300&fit=crop",
        technologies: ["Vue.js", "OpenWeather API", "Chart.js", "PWA"]
    },
    {
        id: 4,
        title: "Portfolio Website",
        description: "A responsive portfolio website showcasing creative work with smooth animations and modern design principles.",
        image: "https://images.unsplash.com/photo-1467232004584-a241de8bcf5d?w=400&h=300&fit=crop",
        technologies: ["HTML", "CSS", "JavaScript", "GSAP"]
    },
    {
        id: 5,
        title: "Social Media Dashboard",
        description: "A comprehensive social media management dashboard with analytics, scheduling, and content creation tools.",
        image: "https://images.unsplash.com/photo-1611162617213-7d7a39e9b1d7?w=400&h=300&fit=crop",
        technologies: ["React", "Node.js", "PostgreSQL", "Redis"]
    },
    {
        id: 6,
        title: "Fitness Tracking App",
        description: "A mobile-first fitness tracking application with workout planning, progress tracking, and social features.",
        image: "https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=400&h=300&fit=crop",
        technologies: ["Vue.js", "PWA", "IndexedDB", "Web APIs"]
    }
]
</script>
