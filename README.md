<script setup>
import { Link } from '@inertiajs/vue3';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
});
</script>

<template>
    <div class="min-h-screen bg-gradient-to-br from-blue-50 to-cyan-50 relative overflow-hidden">
        <!-- Background decorative elements -->
        <div class="absolute top-0 left-0 w-96 h-96 bg-blue-100 rounded-full opacity-40 -translate-x-1/2 -translate-y-1/2"></div>
        <div class="absolute bottom-0 left-0 w-80 h-80 bg-cyan-100 rounded-full opacity-50 -translate-x-1/3 translate-y-1/3"></div>
        <div class="absolute top-1/2 right-0 w-[500px] h-[500px] bg-gradient-to-br from-purple-100 to-blue-100 rounded-full opacity-60 translate-x-1/2 -translate-y-1/2"></div>
        
        <!-- Header -->
        <header class="relative z-10 bg-white shadow-sm border-b-2 border-blue-600">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex items-center justify-between h-16">
                    <!-- Logo -->
                    <div class="flex items-center">
                        <div class="flex items-center space-x-3">
                            <div class="w-12 h-12 bg-gradient-to-r from-blue-600 to-cyan-500 rounded-full flex items-center justify-center shadow-lg">
                                <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                                </svg>
                            </div>
                            <div>
                                <h1 class="text-2xl font-bold text-blue-800">LARANA</h1>
                                <p class="text-sm text-blue-600 font-medium">CLÍNICA DENTAL</p>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Navigation -->
                    <nav class="hidden md:flex items-center space-x-8">
                        <a href="#inicio" class="text-gray-800 hover:text-blue-600 font-semibold transition-colors">INICIO</a>
                        <a href="#servicios" class="text-gray-800 hover:text-blue-600 font-semibold transition-colors">SERVICIOS</a>
                        <a href="#equipo" class="text-gray-800 hover:text-blue-600 font-semibold transition-colors">EQUIPO MÉDICO</a>
                        
                        <!-- Auth Links -->
                        <div v-if="canLogin" class="flex items-center space-x-4">
                            <Link
                                v-if="$page.props.auth.user"
                                :href="route('dashboard')"
                                class="bg-blue-100 text-blue-800 px-4 py-2 rounded-lg font-medium hover:bg-blue-200 transition-colors"
                            >
                                Dashboard
                            </Link>
                            
                            <template v-else>
                                <Link
                                    :href="route('login')"
                                    class="text-gray-800 hover:text-blue-600 font-semibold transition-colors"
                                >
                                    Iniciar Sesión
                                </Link>
                                
                                <Link
                                    v-if="canRegister"
                                    :href="route('register')"
                                    class="bg-blue-100 text-blue-800 px-4 py-2 rounded-lg font-medium hover:bg-blue-200 transition-colors"
                                >
                                    Registrarse
                                </Link>
                            </template>
                        </div>
                        
                
                    </nav>
                </div>
            </div>
        </header>

        <!-- Hero Section -->
        <section id="inicio" class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="grid lg:grid-cols-2 gap-16 items-center">
                <!-- Left Content -->
                <div class="space-y-8">
                    <div class="space-y-6">
                        <h2 class="text-4xl lg:text-5xl font-bold text-gray-900 leading-tight">
                            LAS SONRISAS<br>
                            PERFECTAS<br>
                            COMIENZAN<br>
                            <span class="text-blue-600">AQUÍ</span>
                        </h2>
                        
                        <p class="text-lg text-gray-700 max-w-lg leading-relaxed">
                            Transformamos tu sonrisa con tratamientos innovadores y personalizados. ¡Descubre tu mejor versión con nosotros!
                        </p>
                    </div>
                    
                    <div class="flex flex-col sm:flex-row gap-4">
                        <button class="bg-gradient-to-r from-purple-200 to-blue-200 text-blue-800 px-8 py-4 rounded-full font-semibold hover:from-purple-300 hover:to-blue-300 transition-all shadow-lg flex items-center justify-center space-x-2">
                            <span>AGENDAR CITA</span>
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
                            </svg>
                        </button>
                        
                        <!-- Auth buttons for mobile -->
                        
                    </div>
                </div>
                
                <!-- Right Content - Image -->
                <div class="relative">
                    <div class="relative bg-white rounded-3xl shadow-2xl overflow-hidden border-4 border-blue-100">
                        <img 
                            src="https://images.unsplash.com/photo-1559059689-f26997e3d063?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80" 
                            alt="Dentista trabajando con paciente" 
                            class="w-full h-96 object-cover"
                        />
                        <!-- Overlay gradient -->
                        <div class="absolute inset-0 bg-gradient-to-t from-blue-900/20 to-transparent"></div>
                    </div>
                    
                    <!-- Decorative elements -->
                    <div class="absolute -top-6 -right-6 w-12 h-12 bg-gradient-to-r from-blue-400 to-cyan-400 rounded-full shadow-lg"></div>
                    <div class="absolute -bottom-6 -left-6 w-8 h-8 bg-gradient-to-r from-blue-500 to-cyan-500 rounded-full shadow-lg"></div>
                    <div class="absolute top-1/2 -left-8 w-6 h-6 bg-gradient-to-r from-blue-300 to-cyan-300 rounded-full shadow-lg"></div>
                    <div class="absolute top-1/4 -right-4 w-4 h-4 bg-gradient-to-r from-purple-300 to-blue-300 rounded-full shadow-lg"></div>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section id="servicios" class="py-20 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900 mb-4">Nuestros Servicios</h2>
                    <p class="text-xl text-gray-600 max-w-2xl mx-auto">Ofrecemos una amplia gama de tratamientos dentales con tecnología de vanguardia</p>
                </div>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Service 1 -->
                    <div class="bg-gradient-to-br from-blue-50 to-cyan-50 rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow">
                        <div class="w-16 h-16 bg-gradient-to-r from-blue-500 to-cyan-500 rounded-full flex items-center justify-center mb-6">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Ortodoncia</h3>
                        <p class="text-gray-600 mb-4">Brackets tradicionales y invisibles para corregir la posición de tus dientes</p>
                        <div class="text-blue-600 font-semibold">Desde $2,500</div>
                    </div>
                    
                    <!-- Service 2 -->
                    <div class="bg-gradient-to-br from-purple-50 to-blue-50 rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow">
                        <div class="w-16 h-16 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full flex items-center justify-center mb-6">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Blanqueamiento</h3>
                        <p class="text-gray-600 mb-4">Recupera la blancura natural de tus dientes con tratamientos seguros</p>
                        <div class="text-blue-600 font-semibold">Desde $800</div>
                    </div>
                    
                    <!-- Service 3 -->
                    <div class="bg-gradient-to-br from-green-50 to-blue-50 rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow">
                        <div class="w-16 h-16 bg-gradient-to-r from-green-500 to-blue-500 rounded-full flex items-center justify-center mb-6">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Implantes</h3>
                        <p class="text-gray-600 mb-4">Reemplaza piezas dentales perdidas con implantes de titanio</p>
                        <div class="text-blue-600 font-semibold">Desde $15,000</div>
                    </div>
                    
                    <!-- Service 4 -->
                    <div class="bg-gradient-to-br from-yellow-50 to-orange-50 rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow">
                        <div class="w-16 h-16 bg-gradient-to-r from-yellow-500 to-orange-500 rounded-full flex items-center justify-center mb-6">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Limpieza Dental</h3>
                        <p class="text-gray-600 mb-4">Profilaxis profesional para mantener tu salud bucal óptima</p>
                        <div class="text-blue-600 font-semibold">Desde $400</div>
                    </div>
                    
                    <!-- Service 5 -->
                    <div class="bg-gradient-to-br from-pink-50 to-purple-50 rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow">
                        <div class="w-16 h-16 bg-gradient-to-r from-pink-500 to-purple-500 rounded-full flex items-center justify-center mb-6">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Endodoncia</h3>
                        <p class="text-gray-600 mb-4">Tratamiento de conductos para salvar dientes dañados</p>
                        <div class="text-blue-600 font-semibold">Desde $3,500</div>
                    </div>
                    
                    <!-- Service 6 -->
                    <div class="bg-gradient-to-br from-indigo-50 to-purple-50 rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow">
                        <div class="w-16 h-16 bg-gradient-to-r from-indigo-500 to-purple-500 rounded-full flex items-center justify-center mb-6">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Odontopediatría</h3>
                        <p class="text-gray-600 mb-4">Cuidado dental especializado para los más pequeños</p>
                        <div class="text-blue-600 font-semibold">Desde $600</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Team Section -->
        <section id="equipo" class="py-20 bg-gradient-to-br from-blue-50 to-cyan-50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900 mb-4">Nuestro Equipo Médico</h2>
                    <p class="text-xl text-gray-600 max-w-2xl mx-auto">Profesionales altamente capacitados comprometidos con tu salud dental</p>
                </div>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <!-- Doctor 1 -->
                    <div class="bg-white rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow text-center">
                        <div class="w-32 h-32 bg-gradient-to-r from-blue-500 to-cyan-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-16 h-16 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Dr. María García</h3>
                        <p class="text-blue-600 font-semibold mb-4">Directora Médica</p>
                        <p class="text-gray-600 mb-4">Especialista en Ortodoncia con 15 años de experiencia</p>
                        <div class="text-sm text-gray-500">Cédula: 4567890</div>
                    </div>
                    
                    <!-- Doctor 2 -->
                    <div class="bg-white rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow text-center">
                        <div class="w-32 h-32 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-16 h-16 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Dr. Carlos Rodríguez</h3>
                        <p class="text-blue-600 font-semibold mb-4">Cirujano Oral</p>
                        <p class="text-gray-600 mb-4">Especialista en Implantes y Cirugía Oral</p>
                        <div class="text-sm text-gray-500">Cédula: 7890123</div>
                    </div>
                    
                    <!-- Doctor 3 -->
                    <div class="bg-white rounded-2xl p-8 shadow-lg hover:shadow-xl transition-shadow text-center">
                        <div class="w-32 h-32 bg-gradient-to-r from-green-500 to-blue-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-16 h-16 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Dra. Ana López</h3>
                        <p class="text-blue-600 font-semibold mb-4">Odontopediatra</p>
                        <p class="text-gray-600 mb-4">Especialista en tratamientos dentales para niños</p>
                        <div class="text-sm text-gray-500">Cédula: 3456789</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Why Choose Us Section -->
        <section class="py-20 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900 mb-4">¿Por qué elegir Larana?</h2>
                    <p class="text-xl text-gray-600 max-w-2xl mx-auto">Nos diferenciamos por nuestro compromiso con la excelencia</p>
                </div>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                    <div class="text-center">
                        <div class="w-20 h-20 bg-gradient-to-r from-blue-500 to-cyan-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Tecnología Avanzada</h3>
                        <p class="text-gray-600">Equipos de última generación para tratamientos precisos y cómodos</p>
                    </div>
                    
                    <div class="text-center">
                        <div class="w-20 h-20 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Especialistas Certificados</h3>
                        <p class="text-gray-600">Profesionales con años de experiencia y formación continua</p>
                    </div>
                    
                    <div class="text-center">
                        <div class="w-20 h-20 bg-gradient-to-r from-green-500 to-blue-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Horarios Flexibles</h3>
                        <p class="text-gray-600">Atención de lunes a sábado con horarios que se adaptan a ti</p>
                    </div>
                    
                    <div class="text-center">
                        <div class="w-20 h-20 bg-gradient-to-r from-yellow-500 to-orange-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Garantía de Calidad</h3>
                        <p class="text-gray-600">Garantizamos nuestros tratamientos con seguimiento postoperatorio</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="py-20 bg-gradient-to-br from-blue-50 to-cyan-50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900 mb-4">Contáctanos</h2>
                    <p class="text-xl text-gray-600 max-w-2xl mx-auto">Estamos aquí para resolver todas tus dudas</p>
                </div>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div class="bg-white rounded-2xl p-8 shadow-lg text-center">
                        <div class="w-16 h-16 bg-gradient-to-r from-blue-500 to-cyan-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Teléfono</h3>
                        <p class="text-gray-600 mb-2">+51 987 654 321</p>
                        <p class="text-gray-600">+51 954 123 456</p>
                    </div>
                    
                    <div class="bg-white rounded-2xl p-8 shadow-lg text-center">
                        <div class="w-16 h-16 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Email</h3>
                        <p class="text-gray-600 mb-2">citas@larana.com</p>
                        <p class="text-gray-600">info@larana.com</p>
                    </div>
                    
                    <div class="bg-white rounded-2xl p-8 shadow-lg text-center">
                        <div class="w-16 h-16 bg-gradient-to-r from-green-500 to-blue-500 rounded-full mx-auto mb-6 flex items-center justify-center">
                            <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                                <path d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-4">Dirección</h3>
                        <p class="text-gray-600">Av. El Sol 123, Puno</p>
                        <p class="text-gray-600">Centro Médico Plaza</p>
                    </div>
                </div>
                
                <!-- Schedule -->
                <div class="mt-16 bg-white rounded-2xl p-8 shadow-lg">
                    <h3 class="text-2xl font-bold text-gray-900 mb-8 text-center">Horarios de Atención</h3>
                    <div class="grid md:grid-cols-2 gap-8">
                        <div class="space-y-4">
                            <div class="flex justify-between items-center py-2 border-b border-gray-200">
                                <span class="font-semibold text-gray-900">Lunes - Viernes</span>
                                <span class="text-blue-600">8:00 AM - 7:00 PM</span>
                            </div>
                            <div class="flex justify-between items-center py-2 border-b border-gray-200">
                                <span class="font-semibold text-gray-900">Sábados</span>
                                <span class="text-blue-600">9:00 AM - 4:00 PM</span>
                            </div>
                            <div class="flex justify-between items-center py-2 border-b border-gray-200">
                                <span class="font-semibold text-gray-900">Domingos</span>
                                <span class="text-red-600">Cerrado</span>
                            </div>
                        </div>
                        <div class="space-y-4">
                            <div class="bg-blue-50 p-4 rounded-lg">
                                <h4 class="font-semibold text-blue-800 mb-2">Emergencias</h4>
                                <p class="text-blue-700">Disponible 24/7</p>
                                <p class="text-blue-700">+51 999 888 777</p>
                            </div>
                            <div class="bg-green-50 p-4 rounded-lg">
                                <h4 class="font-semibold text-green-800 mb-2">Citas Online</h4>
                                <p class="text-green-700">Agenda tu cita las 24 horas</p>
                                <p class="text-green-700">desde nuestra web</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Testimonials Section -->
        <section class="py-20 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-gray-900 mb-4">Lo que dicen nuestros pacientes</h2>
                    <p class="text-xl text-gray-600 max-w-2xl mx-auto">Testimonios reales de personas satisfechas con nuestros servicios</p>
                </div>
                
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div class="bg-gradient-to-br from-blue-50 to-cyan-50 rounded-2xl p-8 shadow-lg">
                        <div class="flex items-center mb-4">
                            <div class="w-12 h-12 bg-gradient-to-r from-blue-500 to-cyan-500 rounded-full flex items-center justify-center">
                                <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                                </svg>
                            </div>
                            <div class="ml-4">
                                <h4 class="font-semibold text-gray-900">María Pérez</h4>
                                <div class="flex text-yellow-400">
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                </div>
                            </div>
                        </div>
                        <p class="text-gray-600 italic">"Excelente atención y profesionalismo. Mi tratamiento de ortodoncia fue un éxito total. Recomiendo ampliamente la clínica Larana."</p>
                    </div>
                    
                    <div class="bg-gradient-to-br from-purple-50 to-blue-50 rounded-2xl p-8 shadow-lg">
                        <div class="flex items-center mb-4">
                            <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-blue-500 rounded-full flex items-center justify-center">
                                <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                                </svg>
                            </div>
                            <div class="ml-4">
                                <h4 class="font-semibold text-gray-900">Carlos Mamani</h4>
                                <div class="flex text-yellow-400">
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                </div>
                            </div>
                        </div>
                        <p class="text-gray-600 italic">"El Dr. Rodríguez me hizo un implante dental perfecto. Sin dolor y con resultados increíbles. Muy agradecido con todo el equipo."</p>
                    </div>
                    
                    <div class="bg-gradient-to-br from-green-50 to-blue-50 rounded-2xl p-8 shadow-lg">
                        <div class="flex items-center mb-4">
                            <div class="w-12 h-12 bg-gradient-to-r from-green-500 to-blue-500 rounded-full flex items-center justify-center">
                                <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                                </svg>
                            </div>
                            <div class="ml-4">
                                <h4 class="font-semibold text-gray-900">Ana Quispe</h4>
                                <div class="flex text-yellow-400">
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                                    </svg>
                                </div>
                            </div>
                        </div>
                        <p class="text-gray-600 italic">"Mi hija se siente muy cómoda con la Dra. López. Excelente trato con los niños y ambiente muy acogedor."</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="bg-gray-900 text-white py-12">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid md:grid-cols-4 gap-8">
                    <div class="col-span-2">
                        <div class="flex items-center space-x-3 mb-6">
                            <div class="w-12 h-12 bg-gradient-to-r from-blue-600 to-cyan-500 rounded-full flex items-center justify-center">
                                <svg class="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                                </svg>
                            </div>
                            <div>
                                <h3 class="text-2xl font-bold">LARANA</h3>
                                <p class="text-blue-300">CLÍNICA DENTAL</p>
                            </div>
                        </div>
                        <p class="text-gray-300 mb-4">Transformando sonrisas con tecnología de vanguardia y atención personalizada en el corazón de Puno.</p>
                        <div class="flex space-x-4">
                            <a href="#" class="w-10 h-10 bg-blue-600 rounded-full flex items-center justify-center hover:bg-blue-700 transition-colors">
                                <span class="text-sm font-bold">f</span>
                            </a>
                            <a href="#" class="w-10 h-10 bg-blue-400 rounded-full flex items-center justify-center hover:bg-blue-500 transition-colors">
                                <span class="text-sm font-bold">@</span>
                            </a>
                            <a href="#" class="w-10 h-10 bg-pink-600 rounded-full flex items-center justify-center hover:bg-pink-700 transition-colors">
                                <span class="text-sm font-bold">IG</span>
                            </a>
                            <a href="#" class="w-10 h-10 bg-green-600 rounded-full flex items-center justify-center hover:bg-green-700 transition-colors">
                                <span class="text-sm font-bold">WA</span>
                            </a>
                        </div>
                    </div>
                    
                    <div>
                        <h4 class="text-lg font-semibold mb-4">Servicios</h4>
                        <ul class="space-y-2 text-gray-300">
                            <li><a href="#" class="hover:text-blue-300 transition-colors">Ortodoncia</a></li>
                            <li><a href="#" class="hover:text-blue-300 transition-colors">Implantes</a></li>
                            <li><a href="#" class="hover:text-blue-300 transition-colors">Blanqueamiento</a></li>
                            <li><a href="#" class="hover:text-blue-300 transition-colors">Endodoncia</a></li>
                            <li><a href="#" class="hover:text-blue-300 transition-colors">Limpieza Dental</a></li>
                        </ul>
                    </div>
                    
                    <div>
                        <h4 class="text-lg font-semibold mb-4">Contacto</h4>
                        <ul class="space-y-2 text-gray-300">
                            <li>+51 987 654 321</li>
                            <li>info@larana.com</li>
                            <li>Av. El Sol 123, Puno</li>
                            <li>Lun-Vie: 8AM-7PM</li>
                            <li>Sáb: 9AM-4PM</li>
                        </ul>
                    </div>
                </div>
                
                <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
                    <p>&copy; 2024 Clínica Dental Larana. Todos los derechos reservados.</p>
                </div>
            </div>
        </footer>

        <!-- Mobile Navigation -->
        <nav class="md:hidden fixed bottom-0 left-0 right-0 bg-white border-t-2 border-blue-200 px-4 py-3 z-20 shadow-lg">
            <div class="flex justify-around items-center">
                <a href="#inicio" class="flex flex-col items-center space-y-1 text-blue-600">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"></path>
                    </svg>
                    <span class="text-xs font-medium">Inicio</span>
                </a>
                <a href="#servicios" class="flex flex-col items-center space-y-1 text-gray-600">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"></path>
                    </svg>
                    <span class="text-xs font-medium">Servicios</span>
                </a>
                <a href="#equipo" class="flex flex-col items-center space-y-1 text-gray-600">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"></path>
                    </svg>
                    <span class="text-xs font-medium">Equipo</span>
                </a>
                <button class="flex flex-col items-center space-y-1 text-blue-600">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"></path>
                    </svg>
                    <span class="text-xs font-medium">Cita</span>
                </button>
            </div>
        </nav>
    </div>
</template>
