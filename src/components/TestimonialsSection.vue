<template>
    <section class="section-padding bg-white">
        <div class="container-max">
            <!-- Section Header -->
            <div class="text-center mb-16 animate-fade-in-up">
                <h2 class="text-3xl md:text-4xl font-bold text-text mb-4">
                    What Clients Say
                </h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">
                    Don't just take my word for it. Here's what my clients have to say about
                    working with me on their projects.
                </p>
            </div>

            <!-- Testimonials Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div v-for="(testimonial, index) in testimonials" :key="testimonial.id"
                    class="bg-background rounded-xl p-8 shadow-lg hover:shadow-xl transition-all duration-300 animate-fade-in-up group"
                    :style="{ animationDelay: `${index * 0.1}s` }">
                    <!-- Quote Icon -->
                    <div class="mb-6">
                        <svg class="w-8 h-8 text-accent opacity-60" fill="currentColor" viewBox="0 0 24 24">
                            <path
                                d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z" />
                        </svg>
                    </div>

                    <!-- Testimonial Text -->
                    <p class="text-gray-700 mb-6 leading-relaxed">
                        "{{ testimonial.text }}"
                    </p>

                    <!-- Client Info -->
                    <div class="flex items-center">
                        <img :src="testimonial.avatar" :alt="testimonial.name"
                            class="w-12 h-12 rounded-full object-cover mr-4" />
                        <div>
                            <h4 class="font-semibold text-text">{{ testimonial.name }}</h4>
                            <p class="text-sm text-gray-600">{{ testimonial.position }}</p>
                            <p class="text-sm text-accent">{{ testimonial.company }}</p>
                        </div>
                    </div>

                    <!-- Rating Stars -->
                    <div class="flex mt-4">
                        <svg v-for="star in 5" :key="star" class="w-4 h-4"
                            :class="star <= testimonial.rating ? 'text-yellow-400' : 'text-gray-300'"
                            fill="currentColor" viewBox="0 0 20 20">
                            <path
                                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
interface Testimonial {
    id: number
    name: string
    position: string
    company: string
    text: string
    avatar: string
    rating: number
}

const testimonials: Testimonial[] = [
    {
        id: 1,
        name: "Sarah Chen",
        position: "Product Manager",
        company: "TechFlow Inc.",
        text: "Alex delivered an exceptional e-commerce platform that exceeded our expectations. His attention to detail and user experience expertise made all the difference.",
        avatar: "https://images.unsplash.com/photo-1494790108755-2616b612b786?w=100&h=100&fit=crop&crop=face",
        rating: 5
    },
    {
        id: 2,
        name: "Michael Rodriguez",
        position: "CEO",
        company: "StartupXYZ",
        text: "Working with Alex was a game-changer for our startup. He built a robust task management system that our team uses daily. Highly recommended!",
        avatar: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=100&h=100&fit=crop&crop=face",
        rating: 5
    },
    {
        id: 3,
        name: "Emily Watson",
        position: "Marketing Director",
        company: "Creative Agency",
        text: "Alex's design skills are outstanding. He created a beautiful portfolio website that perfectly represents our brand and has significantly increased our client inquiries.",
        avatar: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=100&h=100&fit=crop&crop=face",
        rating: 5
    },
    {
        id: 4,
        name: "David Kim",
        position: "CTO",
        company: "DataCorp",
        text: "The social media dashboard Alex developed for us is incredibly powerful and user-friendly. It has streamlined our entire marketing workflow.",
        avatar: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&h=100&fit=crop&crop=face",
        rating: 5
    },
    {
        id: 5,
        name: "Lisa Thompson",
        position: "Founder",
        company: "FitnessApp",
        text: "Alex built our fitness tracking app from the ground up. His technical expertise and understanding of user needs resulted in an app our users love.",
        avatar: "https://images.unsplash.com/photo-1544005313-94ddf0286df2?w=100&h=100&fit=crop&crop=face",
        rating: 5
    },
    {
        id: 6,
        name: "James Wilson",
        position: "Operations Manager",
        company: "Global Solutions",
        text: "The weather dashboard Alex created is not only beautiful but also highly functional. It's become an essential tool for our logistics team.",
        avatar: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=100&h=100&fit=crop&crop=face",
        rating: 5
    }
]
</script>
