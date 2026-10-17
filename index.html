<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>PíoPitch - Entrenador de Oído Absoluto</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Fredoka (títulos amigables) y Quicksand (lectura relajante) -->
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&family=Quicksand:wght@500;600;700&display=swap" rel="stylesheet">
    <!-- Tone.js para cargar muestras de Piano Acústico Real (Salamander Grand Piano) -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.8.49/Tone.js"></script>
    <!-- Phosphor Icons -->
    <script src="https://unpkg.com/@phosphor-icons/web"></script>

    <style>
        :root {
            --bg-cream: #FFFDF7;
            --bg-sand: #F7F1E1;
            --pipe-green: #58B852;
            --pipe-dark: #388835;
            --pipe-highlight: #8EE286;
            --chick-yellow: #FFE14D;
            --text-brown: #4A3E35;
        }

        * {
            user-select: none;
            -webkit-user-select: none;
            -webkit-touch-callout: none;
            box-sizing: border-box;
        }

        body {
            font-family: 'Quicksand', sans-serif;
            background-color: var(--bg-cream);
            color: var(--text-brown);
            overflow: hidden;
            touch-action: none;
        }

        h1, h2, h3, .font-display {
            font-family: 'Fredoka', sans-serif;
        }

        /* Botones estilo Mario / Nube cremosa con relieve 3D */
        .btn-retro {
            transition: all 0.12s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 5px 0 rgba(74, 62, 53, 0.22);
            border: 3px solid #4A3E35;
        }
        .btn-retro:active:not(:disabled) {
            transform: translateY(4px);
            box-shadow: 0 1px 0 rgba(74, 62, 53, 0.22);
        }

        .btn-green {
            background: linear-gradient(180deg, #74D66D 0%, #52B64B 100%);
            color: #ffffff;
            text-shadow: 0 2px 0 #2F752A;
            box-shadow: 0 5px 0 #2F752A;
        }
        .btn-green:active:not(:disabled) {
            box-shadow: 0 1px 0 #2F752A;
        }

        .btn-amber {
            background: linear-gradient(180deg, #FFE156 0%, #F5C227 100%);
            color: #4A3E35;
            box-shadow: 0 5px 0 #C2910E;
        }
        .btn-amber:active:not(:disabled) {
            box-shadow: 0 1px 0 #C2910E;
        }

        /* Estilo de tarjeta cremosa */
        .cream-card {
            background-color: #FFFDF9;
            border: 3px solid #4A3E35;
            box-shadow: 0 8px 0 rgba(74, 62, 53, 0.12);
        }

        /* Animación flotante suave */
        @keyframes floatSlow {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-7px); }
        }
        .animate-float {
            animation: floatSlow 2.6s ease-in-out infinite;
        }

        /* Tecla de piano en el modal */
        .piano-key {
            transition: transform 0.1s ease, background-color 0.15s ease;
            box-shadow: 0 6px 0 #D8CCB8;
        }
        .piano-key:active, .piano-key.playing {
            transform: translateY(4px);
            box-shadow: 0 2px 0 #D8CCB8;
            background-color: #FFF3B0 !important;
        }

        /* Scrollbar suave para pantallas pequeñas */
        .custom-scroll::-webkit-scrollbar {
            width: 6px;
        }
        .custom-scroll::-webkit-scrollbar-track {
            background: #F4EFE6;
            border-radius: 8px;
        }
        .custom-scroll::-webkit-scrollbar-thumb {
            background: #D5C8B4;
            border-radius: 8px;
        }
    </style>
</head>

<body class="h-[100dvh] w-screen flex flex-col justify-between overflow-hidden select-none bg-[#FFFDF7]">

    <!-- ÁREA PRINCIPAL DE LA APLICACIÓN (Menú + Juego + Modales) -->
    <main class="relative flex-1 w-full max-w-4xl mx-auto flex flex-col overflow-hidden md:my-2 md:rounded-3xl md:border-4 md:border-[#4A3E35] md:shadow-xl bg-[#FFFDF7]">

        <!-- ==========================================
             BARRA SUPERIOR DE ESTADO Y SONIDO
             ========================================== -->
        <header class="z-30 flex items-center justify-between px-3 sm:px-5 py-2.5 bg-[#F7F1E1] border-b-3 border-[#4A3E35] shrink-0">
            <div class="flex items-center gap-2">
                <div class="w-9 h-9 rounded-xl bg-[#FFE14D] border-2 border-[#4A3E35] flex items-center justify-center shadow-sm">
                    <span class="text-xl">🐥</span>
                </div>
                <div>
                    <h1 class="font-display font-bold text-base sm:text-lg leading-tight text-[#4A3E35]">PíoPitch</h1>
                    <div id="pianoStatusBadge" class="flex items-center gap-1.5 text-[11px] font-semibold text-amber-700">
                        <span id="pianoStatusDot" class="w-2 h-2 rounded-full bg-amber-500 animate-pulse"></span>
                        <span id="pianoStatusText">Cargando Piano Real...</span>
                    </div>
                </div>
            </div>

            <!-- Controles rápidos siempre visibles -->
            <div class="flex items-center gap-2">
                <!-- Botón para abrir la barra/estudio de oír todas las notas -->
                <button id="openNoteStudioBtn" class="btn-retro bg-[#FFFDF9] hover:bg-[#FFF6D6] text-[#4A3E35] px-3 py-1.5 rounded-xl font-display font-semibold text-xs sm:text-sm flex items-center gap-1.5">
                    <i class="ph-fill ph-piano-keys text-lg text-[#58B852]"></i>
                    <span>Oír Notas</span>
                </button>

                <!-- Botón para volver al menú de ajustes cuando está jugando -->
                <button id="backToMenuBtn" class="hidden btn-retro bg-[#FDE8E8] hover:bg-[#FBD5D5] text-[#4A3E35] px-2.5 py-1.5 rounded-xl font-display font-semibold text-xs sm:text-sm flex items-center gap-1">
                    <i class="ph-bold ph-gear text-base"></i>
                    <span class="hidden sm:inline">Ajustes</span>
                </button>
            </div>
        </header>

        <!-- ==========================================
             PANTALLA 1: BIENVENIDA Y CONFIGURACIÓN
             ========================================== -->
        <section id="welcomeScreen" class="z-20 flex-1 overflow-y-auto custom-scroll p-3 sm:p-6 flex flex-col justify-between gap-4 bg-gradient-to-b from-[#FFFDF7] to-[#F7F1E1]">
            
            <!-- Tarjeta de Explicación Amigable -->
            <div class="cream-card rounded-2xl p-4 sm:p-5 flex flex-col sm:flex-row items-center gap-4">
                <div class="animate-float shrink-0 w-20 h-20 sm:w-24 sm:h-24 rounded-2xl bg-[#FFF5C0] border-3 border-[#4A3E35] flex items-center justify-center relative">
                    <!-- SVG del Pollito Cantor -->
                    <svg viewBox="0 0 100 100" class="w-16 h-16 sm:w-20 sm:h-20">
                        <ellipse cx="48" cy="56" rx="28" ry="25" fill="#FFE14D" stroke="#4A3E35" stroke-width="5"/>
                        <path d="M42 32 C38 20, 52 20, 48 31" fill="#FFE14D" stroke="#4A3E35" stroke-width="4" stroke-linecap="round"/>
                        <ellipse cx="40" cy="58" rx="11" ry="7" fill="#F5C227" stroke="#4A3E35" stroke-width="4"/>
                        <circle cx="60" cy="48" r="4.5" fill="#4A3E35"/>
                        <circle cx="61.5" cy="46.5" r="1.5" fill="#FFFFFF"/>
                        <ellipse cx="55" cy="56" rx="4" ry="2.2" fill="#FF8C7A"/>
                        <polygon points="73,47 88,52 73,58" fill="#FF9233" stroke="#4A3E35" stroke-width="4" stroke-linejoin="round"/>
                    </svg>
                    <span class="absolute -top-2 -right-2 bg-[#58B852] text-white text-xs font-display font-bold px-2 py-0.5 rounded-full border-2 border-[#4A3E35]">♪ DO</span>
                </div>
                <div class="text-center sm:text-left">
                    <span class="inline-block bg-[#E6F6E4] text-[#2F752A] border border-[#58B852] font-bold text-xs px-2.5 py-0.5 rounded-full mb-1">
                        Entrenamiento de Oído Absoluto para Principiantes
                    </span>
                    <h2 class="font-display text-xl sm:text-2xl font-bold text-[#4A3E35]">¡Aprende a reconocer notas reales!</h2>
                    <p class="text-xs sm:text-sm text-[#6E5E52] font-semibold mt-1 leading-relaxed">
                        Escucha el <strong>piano acústico real</strong> cuando aparezcan los <strong>dos tubos verdes</strong>. Desliza tu dedo para guiar al pollito hacia el hueco con la burbuja de la nota correcta. Si aciertas se ilumina en <span class="text-[#2F752A] font-bold">verde</span>; si te equivocas, verás tu tubo en <span class="text-red-600 font-bold">rojo</span> y el correcto en <span class="text-[#2F752A] font-bold">verde</span> para entrenar tu oído.
                    </p>
                </div>
            </div>

            <!-- Configuración de Dificultad Selectiva -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-3 sm:gap-4">
                
                <!-- 1. Selección de Notas (Memoria Muscular de 2 en 2, 3 en 3...) -->
                <div class="cream-card rounded-2xl p-3.5 sm:p-4 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-1.5">
                            <h3 class="font-display font-bold text-sm sm:text-base text-[#4A3E35] flex items-center gap-1.5">
                                <i class="ph-fill ph-music-notes text-[#58B852] text-lg"></i>
                                1. Elige tus Notas (Mínimo 2)
                            </h3>
                            <span id="selectedNotesCount" class="text-xs font-bold bg-[#F7F1E1] px-2 py-0.5 rounded-lg border border-[#4A3E35]">2 activas</span>
                        </div>
                        <p class="text-[11px] sm:text-xs text-[#6E5E52] mb-2.5 font-semibold">
                            Empieza de 2 en 2 para crear memoria auditiva y sube poco a poco:
                        </p>

                        <!-- Botones rápidos de progresión -->
                        <div class="flex flex-wrap gap-1.5 mb-3">
                            <button data-preset="2" class="preset-btn text-xs font-bold px-2.5 py-1 rounded-lg border-2 border-[#4A3E35] bg-[#FFF5C0] hover:bg-[#FFE14D] transition">
                                De 2 en 2 (DO - RE)
                            </button>
                            <button data-preset="3" class="preset-btn text-xs font-bold px-2.5 py-1 rounded-lg border-2 border-[#4A3E35] bg-[#F7F1E1] hover:bg-[#FFE14D] transition">
                                De 3 en 3 (DO a MI)
                            </button>
                            <button data-preset="4" class="preset-btn text-xs font-bold px-2.5 py-1 rounded-lg border-2 border-[#4A3E35] bg-[#F7F1E1] hover:bg-[#FFE14D] transition">
                                De 4 en 4
                            </button>
                            <button data-preset="7" class="preset-btn text-xs font-bold px-2.5 py-1 rounded-lg border-2 border-[#4A3E35] bg-[#F7F1E1] hover:bg-[#FFE14D] transition">
                                Todas (7 Notas)
                            </button>
                        </div>

                        <!-- Selector individual de las 7 notas simples -->
                        <div id="noteTogglesContainer" class="grid grid-cols-7 gap-1.5">
                            <!-- Generado dinámicamente por JS -->
                        </div>
                    </div>
                    <p id="noteWarningMsg" class="text-[11px] text-amber-700 font-bold mt-2 hidden">
                        ⚠️ Mantén al menos 2 notas seleccionadas para los dos huecos de los tubos.
                    </p>
                </div>

                <!-- 2. Selección de Velocidad (x1 a x5) -->
                <div class="cream-card rounded-2xl p-3.5 sm:p-4 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-1.5">
                            <h3 class="font-display font-bold text-sm sm:text-base text-[#4A3E35] flex items-center gap-1.5">
                                <i class="ph-fill ph-gauge text-[#FF9233] text-lg"></i>
                                2. Velocidad del Juego
                            </h3>
                            <span id="speedLabelBadge" class="text-xs font-bold bg-[#FFF5C0] px-2.5 py-0.5 rounded-lg border border-[#4A3E35]">Velocidad x1 (Relajado)</span>
                        </div>
                        <p class="text-[11px] sm:text-xs text-[#6E5E52] mb-3 font-semibold">
                            Aumenta la rapidez cuando tu oído identifique las notas al instante:
                        </p>

                        <!-- Botones de velocidad x1, x2, x3, x4, x5 -->
                        <div id="speedButtonsContainer" class="grid grid-cols-5 gap-2 my-1">
                            <button data-speed="1" class="speed-btn btn-retro py-2.5 rounded-xl font-display font-bold text-sm sm:text-base bg-[#58B852] text-white">x1</button>
                            <button data-speed="2" class="speed-btn btn-retro py-2.5 rounded-xl font-display font-bold text-sm sm:text-base bg-[#F7F1E1] text-[#4A3E35]">x2</button>
                            <button data-speed="3" class="speed-btn btn-retro py-2.5 rounded-xl font-display font-bold text-sm sm:text-base bg-[#F7F1E1] text-[#4A3E35]">x3</button>
                            <button data-speed="4" class="speed-btn btn-retro py-2.5 rounded-xl font-display font-bold text-sm sm:text-base bg-[#F7F1E1] text-[#4A3E35]">x4</button>
                            <button data-speed="5" class="speed-btn btn-retro py-2.5 rounded-xl font-display font-bold text-sm sm:text-base bg-[#F7F1E1] text-[#4A3E35]">x5</button>
                        </div>
                    </div>

                    <!-- Consejo de entrenamiento -->
                    <div class="mt-3 bg-[#F7F1E1] rounded-xl p-2.5 border-2 border-[#E5DEC9] flex items-center gap-2.5">
                        <i class="ph-fill ph-speaker-high text-xl text-[#58B852] shrink-0"></i>
                        <p class="text-[11px] sm:text-xs font-semibold text-[#5A4C41]">
                            Sube el volumen de tu dispositivo. Toca cualquier nota arriba para escuchar su sonido real antes de empezar.
                        </p>
                    </div>
                </div>
            </div>

            <!-- Botones de Acción Principal -->
            <div class="flex flex-col sm:flex-row items-center gap-2.5 pt-1">
                <button id="startGameBtn" class="w-full sm:flex-1 btn-retro btn-green py-3.5 px-6 rounded-2xl font-display font-bold text-lg sm:text-xl flex items-center justify-center gap-2 tracking-wide">
                    <i class="ph-fill ph-play-circle text-2xl"></i>
                    <span>¡EMPEZAR EL JUEGO!</span>
                </button>
                <button id="openStudioFromHomeBtn" class="w-full sm:w-auto btn-retro btn-amber py-3.5 px-5 rounded-2xl font-display font-bold text-sm sm:text-base flex items-center justify-center gap-2">
                    <i class="ph-fill ph-ear text-xl"></i>
                    <span>Repasar Sonidos en Fila</span>
                </button>
            </div>
        </section>

        <!-- ==========================================
             PANTALLA 2: LIENZO DEL JUEGO (CANVAS)
             ========================================== -->
        <section id="gameScreen" class="hidden relative flex-1 w-full h-full overflow-hidden flex flex-col bg-[#FFFDF7]">
            
            <!-- HUD Flotante sobre el juego -->
            <div class="z-10 absolute top-3 left-3 right-3 flex flex-wrap items-center justify-between gap-2 pointer-events-none">
                <!-- Puntuación y Racha -->
                <div class="flex items-center gap-2 pointer-events-auto">
                    <div class="bg-[#FFFDF9]/95 backdrop-blur border-3 border-[#4A3E35] rounded-2xl px-3 py-1.5 shadow-md flex items-center gap-3">
                        <div class="flex items-center gap-1">
                            <span class="text-xs font-bold text-[#6E5E52]">Aciertos:</span>
                            <span id="scoreDisplay" class="font-display font-bold text-lg text-[#2F752A]">0</span>
                        </div>
                        <div class="w-0.5 h-4 bg-[#E5DEC9]"></div>
                        <div class="flex items-center gap-1">
                            <span class="text-xs font-bold text-[#6E5E52]">Racha:</span>
                            <span id="streakDisplay" class="font-display font-bold text-lg text-[#FF9233]">0🔥</span>
                        </div>
                    </div>
                </div>

                <!-- Botón Central: Repetir la nota que está sonando -->
                <div class="flex items-center gap-2 pointer-events-auto">
                    <button id="replayNoteBtn" class="btn-retro btn-amber px-3.5 py-1.5 rounded-2xl font-display font-bold text-xs sm:text-sm flex items-center gap-1.5">
                        <i class="ph-fill ph-speaker-high text-lg"></i>
                        <span>Repetir Nota</span>
                    </button>

                    <!-- Selector de velocidad en vivo (x1 a x5) -->
                    <div class="bg-[#FFFDF9]/95 border-3 border-[#4A3E35] rounded-2xl p-1 flex items-center gap-1 shadow-md">
                        <span class="text-[10px] font-bold px-1.5 text-[#6E5E52] hidden sm:inline">Vel:</span>
                        <button data-livespeed="1" class="live-speed-btn px-2 py-0.5 rounded-lg font-display font-bold text-xs bg-[#58B852] text-white">1x</button>
                        <button data-livespeed="2" class="live-speed-btn px-2 py-0.5 rounded-lg font-display font-bold text-xs text-[#4A3E35]">2x</button>
                        <button data-livespeed="3" class="live-speed-btn px-2 py-0.5 rounded-lg font-display font-bold text-xs text-[#4A3E35]">3x</button>
                        <button data-livespeed="4" class="live-speed-btn px-2 py-0.5 rounded-lg font-display font-bold text-xs text-[#4A3E35]">4x</button>
                        <button data-livespeed="5" class="live-speed-btn px-2 py-0.5 rounded-lg font-display font-bold text-xs text-[#4A3E35]">5x</button>
                    </div>
                </div>
            </div>

            <!-- Aviso flotante de retroalimentación (Correcto / Incorrecto) -->
            <div id="feedbackBanner" class="z-10 pointer-events-none absolute top-16 left-1/2 -translate-x-1/2 opacity-0 transition-all duration-300 transform -translate-y-2">
                <div id="feedbackBannerInner" class="px-4 py-1.5 rounded-full border-3 border-[#4A3E35] font-display font-bold text-sm sm:text-base shadow-md bg-[#58B852] text-white">
                    ¡Muy bien! Era DO
                </div>
            </div>

            <!-- Canvas Interactivo del Pollito y los Dos Tubos Verdes -->
            <div id="canvasContainer" class="relative flex-1 w-full h-full">
                <canvas id="gameCanvas" class="block w-full h-full cursor-pointer"></canvas>
            </div>

            <!-- Instrucción inferior sutil -->
            <div class="bg-[#EADBC4] border-t-3 border-[#4A3E35] px-4 py-1.5 flex items-center justify-between text-xs font-bold text-[#4A3E35] shrink-0">
                <span class="flex items-center gap-1.5">
                    <i class="ph-fill ph-hand-pointing text-base text-[#58B852]"></i>
                    Desliza tu dedo (o el ratón) arriba y abajo para elegir el hueco
                </span>
                <span id="activeNotesFooter" class="hidden sm:inline text-[#6E5E52]">Notas: DO, RE</span>
            </div>
        </section>

        <!-- ==========================================
             MODAL / BARRA DE REFERENCIA: OÍR TODAS LAS NOTAS EN FILA
             ========================================== -->
        <div id="noteStudioModal" class="hidden z-40 absolute inset-0 bg-[#4A3E35]/60 backdrop-blur-sm flex items-center justify-center p-3 sm:p-6">
            <div class="cream-card w-full max-w-2xl rounded-3xl p-4 sm:p-6 flex flex-col gap-4 max-h-full overflow-y-auto">
                
                <div class="flex items-center justify-between border-b-2 border-[#E5DEC9] pb-3">
                    <div class="flex items-center gap-2.5">
                        <div class="w-10 h-10 rounded-2xl bg-[#E6F6E4] border-2 border-[#4A3E35] flex items-center justify-center">
                            <i class="ph-fill ph-music-notes-simple text-xl text-[#2F752A]"></i>
                        </div>
                        <div>
                            <h2 class="font-display font-bold text-lg sm:text-xl text-[#4A3E35]">Estudio de Notas de Piano Real</h2>
                            <p class="text-xs font-semibold text-[#6E5E52]">Refresca tu memoria auditiva si te pierdes o se te olvida algún sonido</p>
                        </div>
                    </div>
                </div>

                <!-- Las 7 Notas en Fila (DO RE MI FA SOL LA SI) -->
                <div class="bg-[#F7F1E1] p-3 sm:p-4 rounded-2xl border-2 border-[#4A3E35]">
                    <p class="text-xs font-bold text-center text-[#6E5E52] mb-3">
                        Toca cualquier nota para oír su sonido real una por una:
                    </p>
                    <div id="studioPianoRow" class="grid grid-cols-7 gap-1.5 sm:gap-2.5">
                        <!-- Botones de piano generados por JS -->
                    </div>
                </div>

                <!-- Reproductor de Escala / Canción en Fila -->
                <div class="flex flex-col sm:flex-row items-center justify-between gap-3 bg-[#FFF8E1] p-3.5 rounded-2xl border-2 border-[#4A3E35]">
                    <div class="text-center sm:text-left">
                        <h4 class="font-display font-bold text-sm sm:text-base text-[#4A3E35]">¿Quieres oírlas todas juntas como una canción?</h4>
                        <p class="text-xs text-[#6E5E52] font-semibold">Escucha la escala completa en orden para afinar tu oído relativo y absoluto.</p>
                    </div>
                    <div class="flex items-center gap-2 w-full sm:w-auto justify-center shrink-0">
                        <button id="playAllRowBtn" class="btn-retro btn-amber px-4 py-2.5 rounded-xl font-display font-bold text-xs sm:text-sm flex items-center gap-1.5">
                            <i class="ph-fill ph-play text-base"></i>
                            <span>Oír Todas en Fila</span>
                        </button>
                        <button id="playActiveRowBtn" class="btn-retro bg-white hover:bg-[#F7F1E1] text-[#4A3E35] px-3.5 py-2.5 rounded-xl font-display font-bold text-xs sm:text-sm flex items-center gap-1.5">
                            <i class="ph-fill ph-playlist text-base text-[#58B852]"></i>
                            <span>Solo Mis Notas</span>
                        </button>
                    </div>
                </div>

                <!-- Botón de Ir al Juego Otra Vez -->
                <div class="flex justify-end pt-1">
                    <button id="returnToGameBtn" class="w-full btn-retro btn-green py-3 px-6 rounded-2xl font-display font-bold text-base sm:text-lg flex items-center justify-center gap-2">
                        <i class="ph-fill ph-game-controller text-xl"></i>
                        <span>Ir al Juego Otra Vez</span>
                    </button>
                </div>
            </div>
        </div>

    </main>

    <!-- ==========================================
         HUECO RESERVADO PARA ANUNCIO (CÓMODO Y SIN MOLESTAR)
         ========================================== -->
    <footer class="w-full shrink-0 bg-[#F3ECE0] border-t-2 border-[#DFD3C0] px-3 py-1.5 flex items-center justify-center z-30">
        <div class="w-full max-w-[728px] h-[52px] sm:h-[60px] rounded-xl border-2 border-dashed border-[#B8A993] bg-[#FAF6EE] flex items-center justify-between px-4 text-[#8C7A65]">
            <div class="flex items-center gap-2">
                <span class="text-[10px] font-bold uppercase tracking-wider bg-[#E6DEC8] text-[#5A4C41] px-2 py-0.5 rounded">Anuncio</span>
                <span class="text-xs font-semibold hidden sm:inline">Espacio reservado para publicidad no intrusiva</span>
            </div>
            <span class="font-display font-bold text-xs sm:text-sm tracking-wide text-[#7A6A56]">ANUNCIO (Banner 320x50 / 728x90)</span>
            <i class="ph ph-Megaphone text-lg"></i>
        </div>
    </footer>

    <script>
        /**
         * 1. DEFINICIÓN DE LAS 7 NOTAS SIMPLES PARA NOVATOS (Sin sostenidos ni acordes complejos)
         * Usamos la octava central (C4 a B4), ideal para la voz humana y principiantes de canto.
         */
        const MUSICAL_NOTES = [
            { id: 'DO',  pitch: 'C4', freq: 261.63, color: '#FF6B6B', light: '#FFE3E3', desc: 'Do central' },
            { id: 'RE',  pitch: 'D4', freq: 293.66, color: '#FF9233', light: '#FFE8D1', desc: 'Re natural' },
            { id: 'MI',  pitch: 'E4', freq: 329.63, color: '#F5C227', light: '#FFF5C2', desc: 'Mi natural' },
            { id: 'FA',  pitch: 'F4', freq: 349.23, color: '#58B852', light: '#E2F7E1', desc: 'Fa natural' },
            { id: 'SOL', pitch: 'G4', freq: 392.00, color: '#38A3F1', light: '#DCF0FF', desc: 'Sol natural' },
            { id: 'LA',  pitch: 'A4', freq: 440.00, color: '#7965F0', light: '#E6E2FF', desc: 'La (440 Hz)' },
            { id: 'SI',  pitch: 'B4', freq: 493.88, color: '#EC62A4', light: '#FCE0EE', desc: 'Si natural' }
        ];

        /**
         * 2. MOTOR DE AUDIO DE PIANO ACÚSTICO REAL (Salamander Grand Piano)
         * Carga grabaciones reales de piano de cola para que el estudiante entrene con timbre real.
         */
        class RealPianoEngine {
            constructor() {
                this.isLoaded = false;
                this.sampler = null;
                this.sequenceTimeouts = [];
                this.initSampler();
            }

            initSampler() {
                try {
                    // Muestras acústicas reales del Salamander Grand Piano alojadas en el CDN oficial de Tone.js
                    this.sampler = new Tone.Sampler({
                        urls: {
                            "C4": "C4.mp3",
                            "D#4": "Ds4.mp3",
                            "F#4": "Fs4.mp3",
                            "A4": "A4.mp3",
                            "C5": "C5.mp3"
                        },
                        release: 1.4,
                        baseUrl: "https://tonejs.github.io/audio/salamander/",
                        onload: () => {
                            this.isLoaded = true;
                            const dot = document.getElementById('pianoStatusDot');
                            const text = document.getElementById('pianoStatusText');
                            const badge = document.getElementById('pianoStatusBadge');
                            if (dot && text && badge) {
                                dot.className = "w-2 h-2 rounded-full bg-[#58B852]";
                                badge.className = "flex items-center gap-1.5 text-[11px] font-bold text-[#2F752A]";
                                text.textContent = "Piano Acústico Real Listo";
                            }
                        }
                    }).toDestination();
                } catch (err) {
                    console.warn("Error inicializando Tone.Sampler, usando respaldo armónico:", err);
                }
            }

            async unlockAudio() {
                if (Tone.context.state !== 'running') {
                    await Tone.start();
                }
            }

            async playNote(noteObj, duration = "1.5") {
                await this.unlockAudio();

                if (this.isLoaded && this.sampler) {
                    try {
                        this.sampler.triggerAttackRelease(noteObj.pitch, duration);
                        return;
                    } catch (e) {
                        console.warn("Fallo al disparar muestra:", e);
                    }
                }

                // Respaldo de emergencia solo si aún está descargando el archivo MP3 en el primer segundo
                const synth = new Tone.PolySynth(Tone.Synth, {
                    oscillator: { type: "triangle" },
                    envelope: { attack: 0.01, decay: 0.8, sustain: 0.1, release: 1.2 }
                }).toDestination();
                synth.triggerAttackRelease(noteObj.pitch, "2n");
            }

            stopSequence() {
                this.sequenceTimeouts.forEach(t => clearTimeout(t));
                this.sequenceTimeouts = [];
                document.querySelectorAll('.piano-key').forEach(el => el.classList.remove('playing'));
            }

            async playNotesInRow(notesArray) {
                this.stopSequence();
                await this.unlockAudio();

                notesArray.forEach((note, index) => {
                    const timeoutId = setTimeout(() => {
                        this.playNote(note, "1.1");
                        // Iluminar la tecla en el modal
                        document.querySelectorAll('.piano-key').forEach(el => el.classList.remove('playing'));
                        const keyBtn = document.getElementById(`studio-key-${note.id}`);
                        if (keyBtn) {
                            keyBtn.classList.add('playing');
                            setTimeout(() => keyBtn.classList.remove('playing'), 550);
                        }
                    }, index * 650);
                    this.sequenceTimeouts.push(timeoutId);
                });
            }
        }

        const piano = new RealPianoEngine();

        /**
         * 3. ESTADO GLOBAL DE LA APLICACIÓN Y DIFICULTAD SELECTIVA
         */
        const appState = {
            selectedNoteIds: ['DO', 'RE'], // Empieza de 2 en 2 para novatos
            speedMultiplier: 1,            // Velocidad x1, x2, x3, x4, x5
            isPlaying: false,
            isPausedInStudio: false,
            score: 0,
            streak: 0,
            currentTargetNote: null
        };

        const SPEED_DESCRIPTIONS = {
            1: 'Velocidad x1 (Relajado)',
            2: 'Velocidad x2 (Suave)',
            3: 'Velocidad x3 (Normal)',
            4: 'Velocidad x4 (Rápido)',
            5: 'Velocidad x5 (Maestro)'
        };

        // Obtener objetos de notas activas
        function getActiveNotes() {
            return MUSICAL_NOTES.filter(n => appState.selectedNoteIds.includes(n.id));
        }

        // Renderizar los interruptores de notas en la pantalla de inicio y en el estudio
        function renderNoteSelectors() {
            const container = document.getElementById('noteTogglesContainer');
            const studioRow = document.getElementById('studioPianoRow');
            container.innerHTML = '';
            studioRow.innerHTML = '';

            MUSICAL_NOTES.forEach(note => {
                const isSelected = appState.selectedNoteIds.includes(note.id);

                // Botón en el menú de configuración
                const btn = document.createElement('button');
                btn.type = 'button';
                btn.className = `btn-retro flex flex-col items-center justify-center py-2 px-1 rounded-xl font-display transition ${
                    isSelected 
                        ? 'bg-[#58B852] text-white border-[#4A3E35]' 
                        : 'bg-[#F7F1E1] text-[#7A6A56] border-[#4A3E35] opacity-75'
                }`;
                btn.innerHTML = `
                    <span class="text-xs sm:text-sm font-bold">${note.id}</span>
                    <span class="text-[9px] opacity-90">${isSelected ? 'Activa' : 'Off'}</span>
                `;
                btn.addEventListener('click', () => {
                    piano.playNote(note);
                    toggleNoteSelection(note.id);
                });
                container.appendChild(btn);

                // Tecla de piano en la barra/modal "Oír Notas en Fila"
                const studioKey = document.createElement('button');
                studioKey.type = 'button';
                studioKey.id = `studio-key-${note.id}`;
                studioKey.className = `piano-key bg-white hover:bg-[#FFFDF0] border-3 border-[#4A3E35] rounded-2xl py-4 sm:py-6 px-1 flex flex-col items-center justify-between gap-2 relative`;
                studioKey.innerHTML = `
                    <span class="w-6 h-6 sm:w-8 sm:h-8 rounded-full flex items-center justify-center font-display font-bold text-[11px] sm:text-xs text-white border-2 border-[#4A3E35]" style="background:${note.color}">
                        ♪
                    </span>
                    <span class="font-display font-bold text-sm sm:text-lg text-[#4A3E35]">${note.id}</span>
                    <span class="text-[10px] font-bold px-1.5 py-0.5 rounded-full ${isSelected ? 'bg-[#E6F6E4] text-[#2F752A]' : 'bg-gray-100 text-gray-400'}">
                        ${isSelected ? 'En juego' : 'Libre'}
                    </span>
                `;
                studioKey.addEventListener('click', () => {
                    piano.stopSequence();
                    piano.playNote(note);
                    studioKey.classList.add('playing');
                    setTimeout(() => studioKey.classList.remove('playing'), 350);
                });
                studioRow.appendChild(studioKey);
            });

            // Actualizar contadores
            document.getElementById('selectedNotesCount').textContent = `${appState.selectedNoteIds.length} activas`;
            document.getElementById('activeNotesFooter').textContent = `Notas: ${appState.selectedNoteIds.join(', ')}`;
        }

        function toggleNoteSelection(noteId) {
            const warnEl = document.getElementById('noteWarningMsg');
            const idx = appState.selectedNoteIds.indexOf(noteId);
            if (idx > -1) {
                if (appState.selectedNoteIds.length <= 2) {
                    warnEl.classList.remove('hidden');
                    setTimeout(() => warnEl.classList.add('hidden'), 2800);
                    return;
                }
                appState.selectedNoteIds.splice(idx, 1);
            } else {
                // Mantener el orden natural DO RE MI FA SOL LA SI
                appState.selectedNoteIds.push(noteId);
                const order = MUSICAL_NOTES.map(n => n.id);
                appState.selectedNoteIds.sort((a, b) => order.indexOf(a) - order.indexOf(b));
            }
            warnEl.classList.add('hidden');
            renderNoteSelectors();
        }

        function setSpeedMultiplier(speed) {
            appState.speedMultiplier = speed;
            document.getElementById('speedLabelBadge').textContent = SPEED_DESCRIPTIONS[speed];

            // Actualizar botones del menú principal
            document.querySelectorAll('.speed-btn').forEach(btn => {
                const s = parseInt(btn.getAttribute('data-speed'), 10);
                if (s === speed) {
                    btn.className = "speed-btn btn-retro py-2.5 rounded-xl font-display font-bold text-sm sm:text-base bg-[#58B852] text-white";
                } else {
                    btn.className = "speed-btn btn-retro py-2.5 rounded-xl font-display font-bold text-sm sm:text-base bg-[#F7F1E1] text-[#4A3E35]";
                }
            });

            // Actualizar botones en vivo dentro del juego
            document.querySelectorAll('.live-speed-btn').forEach(btn => {
                const s = parseInt(btn.getAttribute('data-livespeed'), 10);
                if (s === speed) {
                    btn.className = "live-speed-btn px-2 py-0.5 rounded-lg font-display font-bold text-xs bg-[#58B852] text-white";
                } else {
                    btn.className = "live-speed-btn px-2 py-0.5 rounded-lg font-display font-bold text-xs text-[#4A3E35] hover:bg-[#F7F1E1]";
                }
            });
        }

        /**
         * 4. MOTOR DEL JUEGO (CANVAS 2D: Pollito Amarillo + Dos Tubos Verdes con Huecos y Burbuja de Nota)
         */
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');

        // Entidades del juego
        const chick = {
            x: 90,
            y: 200,
            targetY: 200,
            radius: 24,
            wingAngle: 0,
            isDragging: false
        };

        let pipePair = null;
        let clouds = [];
        let hills = [];
        let floatingParticles = [];
        let lastFrameTime = performance.now();

        function resizeCanvas() {
            const container = document.getElementById('canvasContainer');
            if (!container) return;
            const rect = container.getBoundingClientRect();
            canvas.width = rect.width || 800;
            canvas.height = rect.height || 450;

            chick.x = Math.max(70, Math.min(130, canvas.width * 0.18));
            if (!appState.isPlaying) {
                chick.y = canvas.height / 2;
                chick.targetY = canvas.height / 2;
            }
            initScenery();
        }

        function initScenery() {
            clouds = [
                { x: canvas.width * 0.15, y: canvas.height * 0.18, scale: 1.0, speed: 12 },
                { x: canvas.width * 0.55, y: canvas.height * 0.12, scale: 0.8, speed: 9 },
                { x: canvas.width * 0.85, y: canvas.height * 0.25, scale: 1.15, speed: 15 }
            ];
            hills = [
                { x: canvas.width * 0.2, width: 260, height: 95, color: '#E8F3D6' },
                { x: canvas.width * 0.65, width: 340, height: 125, color: '#DCECC3' },
                { x: canvas.width * 1.05, width: 280, height: 100, color: '#E8F3D6' }
            ];
        }

        /**
         * Genera una nueva columna con DOS TUBOS VERDES:
         * - Tubo 1 (Arriba): Tiene un hueco en el medio con su burbuja y nombre de nota.
         * - Tubo 2 (Abajo): Tiene un hueco en el medio con su burbuja y nombre de nota diferente.
         */
        function spawnTwoPipesWall() {
            const activeNotes = getActiveNotes();
            // Elegir nota correcta al azar entre las seleccionadas
            const correctNote = activeNotes[Math.floor(Math.random() * activeNotes.length)];
            // Elegir nota incorrecta diferente para el otro tubo
            const otherNotes = activeNotes.filter(n => n.id !== correctNote.id);
            const wrongNote = otherNotes[Math.floor(Math.random() * otherNotes.length)] || MUSICAL_NOTES[0];

            // Decidir aleatoriamente si la nota correcta va en el tubo superior o en el inferior
            const correctIsTop = Math.random() < 0.5;
            const topNote = correctIsTop ? correctNote : wrongNote;
            const bottomNote = correctIsTop ? wrongNote : correctNote;

            const h = canvas.height;
            // El centro del hueco del Tubo Superior está en 27% de la altura
            // El centro del hueco del Tubo Inferior está en 73% de la altura
            const gapHeight = Math.max(86, Math.min(125, h * 0.27));

            pipePair = {
                x: canvas.width + 60,
                width: Math.max(76, Math.min(96, canvas.width * 0.12)),
                topGapCenterY: h * 0.27,
                bottomGapCenterY: h * 0.73,
                gapHeight: gapHeight,
                topNote: topNote,
                bottomNote: bottomNote,
                correctNote: correctNote,
                evaluated: false,
                topStatus: 'neutral',    // 'neutral' | 'correct' | 'wrong'
                bottomStatus: 'neutral'  // 'neutral' | 'correct' | 'wrong'
            };

            appState.currentTargetNote = correctNote;

            // Hacer sonar la nota real de piano cuando empieza a avanzar el par de tubos
            if (appState.isPlaying && !appState.isPausedInStudio) {
                piano.playNote(correctNote);
            }
        }

        function drawBackground(dt) {
            // Cielo cremoso relajante
            const skyGrad = ctx.createLinearGradient(0, 0, 0, canvas.height);
            skyGrad.addColorStop(0, '#FFFDF7');
            skyGrad.addColorStop(1, '#F6EFE0');
            ctx.fillStyle = skyGrad;
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            // Colinas suaves estilo Mario Bros pastel
            hills.forEach(hill => {
                hill.x -= dt * 25 * (0.5 + appState.speedMultiplier * 0.2);
                if (hill.x + hill.width < -50) {
                    hill.x = canvas.width + 60;
                }
                ctx.save();
                ctx.beginPath();
                ctx.arc(hill.x, canvas.height, hill.height, Math.PI, 0);
                ctx.fillStyle = hill.color;
                ctx.fill();
                ctx.lineWidth = 3;
                ctx.strokeStyle = '#C9DFB0';
                ctx.stroke();
                ctx.restore();
            });

            // Nubes cremosas
            clouds.forEach(c => {
                c.x -= dt * c.speed * (0.6 + appState.speedMultiplier * 0.15);
                if (c.x < -100) c.x = canvas.width + 80;

                ctx.save();
                ctx.translate(c.x, c.y);
                ctx.scale(c.scale, c.scale);
                ctx.fillStyle = '#FFFFFF';
                ctx.strokeStyle = '#E6DEC8';
                ctx.lineWidth = 3;
                ctx.beginPath();
                ctx.arc(0, 0, 22, 0, Math.PI * 2);
                ctx.arc(22, -6, 26, 0, Math.PI * 2);
                ctx.arc(46, 0, 20, 0, Math.PI * 2);
                ctx.fill();
                ctx.stroke();
                ctx.restore();
            });

            // Línea guía punteada sutil donde vuela el pollito
            ctx.save();
            ctx.setLineDash([6, 8]);
            ctx.strokeStyle = 'rgba(74, 62, 53, 0.14)';
            ctx.lineWidth = 2;
            ctx.beginPath();
            ctx.moveTo(chick.x, 20);
            ctx.lineTo(chick.x, canvas.height - 20);
            ctx.stroke();
            ctx.restore();
        }

        /**
         * Dibuja una sección de tubo estilo Mario Bros con bisel, brillo y borde limpio
         */
        function drawMarioPipeSegment(x, y, width, height, capPosition, statusColor) {
            if (height <= 0) return;

            // Paleta según estado: neutral (verde Mario), correcto (verde brillante), incorrecto (rojo)
            let mainColor = '#58B852';
            let highlightColor = '#8EE286';
            let shadowColor = '#388835';

            if (statusColor === 'correct') {
                mainColor = '#2ECC71';
                highlightColor = '#A3F7BF';
                shadowColor = '#1E8449';
            } else if (statusColor === 'wrong') {
                mainColor = '#E74C3C';
                highlightColor = '#FF9F97';
                shadowColor = '#922B21';
            }

            ctx.save();
            const capHeight = Math.min(22, height);
            const capHang = 6;

            // Cuerpo del tubo
            ctx.fillStyle = mainColor;
            ctx.strokeStyle = '#4A3E35';
            ctx.lineWidth = 3.5;
            ctx.fillRect(x, y, width, height);

            // Brillo vertical izquierdo estilo Mario
            ctx.fillStyle = highlightColor;
            ctx.fillRect(x + 8, y, width * 0.22, height);

            // Sombra vertical derecha
            ctx.fillStyle = shadowColor;
            ctx.fillRect(x + width - width * 0.22, y, width * 0.22, height);

            // Contorno del cuerpo
            ctx.strokeRect(x, y, width, height);

            // Boca/Borde del tubo (Cap) junto al hueco
            if (capPosition === 'bottom' || capPosition === 'both') {
                const cy = y + height - capHeight;
                ctx.fillStyle = mainColor;
                ctx.fillRect(x - capHang, cy, width + capHang * 2, capHeight);
                ctx.fillStyle = highlightColor;
                ctx.fillRect(x - capHang + 8, cy, width * 0.22, capHeight);
                ctx.fillStyle = shadowColor;
                ctx.fillRect(x + width + capHang - width * 0.22, cy, width * 0.22, capHeight);
                ctx.strokeRect(x - capHang, cy, width + capHang * 2, capHeight);
            }

            if (capPosition === 'top' || capPosition === 'both') {
                const cy = y;
                ctx.fillStyle = mainColor;
                ctx.fillRect(x - capHang, cy, width + capHang * 2, capHeight);
                ctx.fillStyle = highlightColor;
                ctx.fillRect(x - capHang + 8, cy, width * 0.22, capHeight);
                ctx.fillStyle = shadowColor;
                ctx.fillRect(x + width + capHang - width * 0.22, cy, width * 0.22, capHeight);
                ctx.strokeRect(x - capHang, cy, width + capHang * 2, capHeight);
            }

            ctx.restore();
        }

        /**
         * Dibuja la burbuja con el nombre de la nota musical en el centro del hueco del tubo
         */
        function drawNoteBubble(centerX, centerY, radius, noteObj, status) {
            ctx.save();

            // Colores de la burbuja: crema traslúcido antes de pasar, verde si es la correcta, rojo si pasó por la mala
            let bgFill = 'rgba(255, 253, 247, 0.92)';
            let borderStroke = '#4A3E35';
            let textColor = '#4A3E35';

            if (status === 'correct') {
                bgFill = '#2ECC71';
                borderStroke = '#1B5E20';
                textColor = '#FFFFFF';
            } else if (status === 'wrong') {
                bgFill = '#E74C3C';
                borderStroke = '#7F1D1D';
                textColor = '#FFFFFF';
            }

            // Círculo exterior de la burbuja
            ctx.beginPath();
            ctx.arc(centerX, centerY, radius, 0, Math.PI * 2);
            ctx.fillStyle = bgFill;
            ctx.fill();
            ctx.lineWidth = 3.5;
            ctx.strokeStyle = borderStroke;
            ctx.stroke();

            // Reflejo brillante de la burbuja
            ctx.beginPath();
            ctx.arc(centerX - radius * 0.32, centerY - radius * 0.32, radius * 0.22, 0, Math.PI * 2);
            ctx.fillStyle = status === 'neutral' ? 'rgba(255, 255, 255, 0.9)' : 'rgba(255, 255, 255, 0.35)';
            ctx.fill();

            // Nombre de la nota musical (DO, RE, MI...)
            ctx.fillStyle = textColor;
            ctx.font = `700 ${Math.round(radius * 0.72)}px 'Fredoka', sans-serif`;
            ctx.textAlign = 'center';
            ctx.textBaseline = 'middle';
            ctx.fillText(noteObj.id, centerX, centerY + 2);

            ctx.restore();
        }

        /**
         * Dibuja los DOS TUBOS VERDES, cada uno con su hueco en el medio y su burbuja musical
         */
        function drawTwoPipesColumn() {
            if (!pipePair) return;

            const x = pipePair.x;
            const w = pipePair.width;
            const h = canvas.height;
            const midY = h * 0.5;
            const halfGap = pipePair.gapHeight / 2;

            // --- TUBO 1 (SUPERIOR): Va de 0 a midY con un hueco en el medio ---
            const topGapStart = pipePair.topGapCenterY - halfGap;
            const topGapEnd = pipePair.topGapCenterY + halfGap;

            // Parte alta del Tubo 1
            drawMarioPipeSegment(x, 0, w, topGapStart, 'bottom', pipePair.topStatus);
            // Parte baja del Tubo 1 (hasta la mitad de la pantalla)
            drawMarioPipeSegment(x, topGapEnd, w, midY - topGapEnd, 'top', pipePair.topStatus);

            // --- TUBO 2 (INFERIOR): Va de midY a canvas.height con un hueco en el medio ---
            const botGapStart = pipePair.bottomGapCenterY - halfGap;
            const botGapEnd = pipePair.bottomGapCenterY + halfGap;

            // Parte alta del Tubo 2 (desde la mitad de la pantalla)
            drawMarioPipeSegment(x, midY, w, botGapStart - midY, 'top', pipePair.bottomStatus);
            // Parte baja del Tubo 2 (hasta el suelo)
            drawMarioPipeSegment(x, botGapEnd, w, h - botGapEnd, 'top', pipePair.bottomStatus);

            // Anillo divisor limpio entre el Tubo 1 y el Tubo 2 en el centro
            ctx.save();
            ctx.fillStyle = '#4A3E35';
            ctx.fillRect(x - 4, midY - 2, w + 8, 4);
            ctx.restore();

            // Burbujas con la nota musical dentro de cada hueco
            const bubbleRadius = Math.min(32, halfGap * 0.76);
            drawNoteBubble(x + w / 2, pipePair.topGapCenterY, bubbleRadius, pipePair.topNote, pipePair.topStatus);
            drawNoteBubble(x + w / 2, pipePair.bottomGapCenterY, bubbleRadius, pipePair.bottomNote, pipePair.bottomStatus);
        }

        /**
         * Dibuja el personaje principal: El Pollito Amarillo
         */
        function drawYellowChick(dt) {
            // Movimiento vertical suave siguiendo el dedo o ratón
            const lerpSpeed = 14;
            chick.y += (chick.targetY - chick.y) * Math.min(1, dt * lerpSpeed);
            chick.wingAngle += dt * (8 + appState.speedMultiplier * 2);

            const r = chick.radius;
            const tilt = Math.max(-0.35, Math.min(0.35, (chick.targetY - chick.y) * 0.008));

            ctx.save();
            ctx.translate(chick.x, chick.y);
            ctx.rotate(tilt);

            // Sombra suave bajo el pollito
            ctx.beginPath();
            ctx.ellipse(0, r + 6, r * 0.7, 5, 0, 0, Math.PI * 2);
            ctx.fillStyle = 'rgba(74, 62, 53, 0.12)';
            ctx.fill();

            // Cuerpo redondo amarillo del pollito
            ctx.beginPath();
            ctx.ellipse(0, 0, r * 1.08, r * 0.95, 0, 0, Math.PI * 2);
            ctx.fillStyle = '#FFE14D';
            ctx.fill();
            ctx.lineWidth = 3.5;
            ctx.strokeStyle = '#4A3E35';
            ctx.stroke();

            // Copete de plumas arriba
            ctx.beginPath();
            ctx.moveTo(-4, -r * 0.9);
            ctx.quadraticCurveTo(-8, -r * 1.35, 2, -r * 1.15);
            ctx.quadraticCurveTo(8, -r * 1.4, 6, -r * 0.9);
            ctx.fillStyle = '#FFE14D';
            ctx.fill();
            ctx.stroke();

            // Alita batiente
            const wingOffset = Math.sin(chick.wingAngle) * 4;
            ctx.beginPath();
            ctx.ellipse(-6, 3 + wingOffset, r * 0.48, r * 0.3, -0.2, 0, Math.PI * 2);
            ctx.fillStyle = '#F5C227';
            ctx.fill();
            ctx.stroke();

            // Ojo expresivo
            ctx.beginPath();
            ctx.arc(r * 0.42, -r * 0.2, 4.5, 0, Math.PI * 2);
            ctx.fillStyle = '#4A3E35';
            ctx.fill();

            // Brillo del ojo
            ctx.beginPath();
            ctx.arc(r * 0.48, -r * 0.26, 1.6, 0, Math.PI * 2);
            ctx.fillStyle = '#FFFFFF';
            ctx.fill();

            // Mejilla sonrojada
            ctx.beginPath();
            ctx.ellipse(r * 0.25, r * 0.12, 4.5, 2.6, 0, 0, Math.PI * 2);
            ctx.fillStyle = '#FF8C7A';
            ctx.fill();

            // Pico naranja
            ctx.beginPath();
            ctx.moveTo(r * 0.95, -5);
            ctx.lineTo(r * 1.45, 1);
            ctx.lineTo(r * 0.95, 7);
            ctx.closePath();
            ctx.fillStyle = '#FF9233';
            ctx.fill();
            ctx.stroke();

            ctx.restore();
        }

        /**
         * Evalúa por cuál de los dos huecos pasa el pollito y aplica la regla de colores:
         * - Si pasa por la nota correcta -> se pone VERDE.
         * - Si pasa por la nota incorrecta o choca -> la incorrecta se pone ROJA y la otra correcta se pone VERDE.
         */
        function updateGameLogic(dt) {
            if (!appState.isPlaying || appState.isPausedInStudio || !pipePair) return;

            // Velocidad progresiva según x1, x2, x3, x4, x5
            const basePixelsPerSec = 135;
            const speedFactors = { 1: 1.0, 2: 1.35, 3: 1.75, 4: 2.2, 5: 2.7 };
            const currentSpeed = basePixelsPerSec * (speedFactors[appState.speedMultiplier] || 1);

            pipePair.x -= currentSpeed * dt;

            // Evaluar cuando el centro de la burbuja/tubo cruza la posición del pollito
            const pipeCenterX = pipePair.x + pipePair.width / 2;
            if (!pipePair.evaluated && pipeCenterX <= chick.x) {
                pipePair.evaluated = true;

                // Determinar si el pollito está en la mitad superior (Tubo 1) o inferior (Tubo 2)
                const choseTopTube = chick.y < canvas.height / 2;
                const chosenNote = choseTopTube ? pipePair.topNote : pipePair.bottomNote;
                const isCorrectNote = chosenNote.id === pipePair.correctNote.id;

                // Verificar además si pasó limpiamente cerca del hueco elegido
                const chosenGapCenterY = choseTopTube ? pipePair.topGapCenterY : pipePair.bottomGapCenterY;
                const insideGap = Math.abs(chick.y - chosenGapCenterY) <= (pipePair.gapHeight * 0.62);

                if (isCorrectNote && insideGap) {
                    // ¡ACIERTO! La nota correcta se pone en color VERDE (sin sonido extra para no confundir con la que viene)
                    if (choseTopTube) {
                        pipePair.topStatus = 'correct';
                    } else {
                        pipePair.bottomStatus = 'correct';
                    }

                    appState.score += 1;
                    appState.streak += 1;
                    showFeedbackBanner(`¡Correcto! Era ${pipePair.correctNote.id} ♪`, true);
                    spawnCelebrationNotes(chick.x, chick.y, '#2ECC71');
                } else {
                    // ¡ERROR! La incorrecta se pone en ROJO y la otra correcta se ilumina en VERDE (en silencio)
                    if (pipePair.topNote.id === pipePair.correctNote.id) {
                        pipePair.topStatus = 'correct';    // La correcta en VERDE
                        pipePair.bottomStatus = 'wrong';   // La incorrecta en ROJO
                    } else {
                        pipePair.bottomStatus = 'correct'; // La correcta en VERDE
                        pipePair.topStatus = 'wrong';      // La incorrecta en ROJO
                    }

                    appState.streak = 0;
                    showFeedbackBanner(`Era ${pipePair.correctNote.id} (Marcada en Verde)`, false);
                    spawnCelebrationNotes(chick.x, chick.y, '#E74C3C');
                }

                document.getElementById('scoreDisplay').textContent = appState.score;
                document.getElementById('streakDisplay').textContent = `${appState.streak}🔥`;
            }

            // Cuando los tubos salen por la izquierda, generamos el siguiente par
            if (pipePair.x + pipePair.width < -30) {
                spawnTwoPipesWall();
            }
        }

        function showFeedbackBanner(message, isSuccess) {
            const banner = document.getElementById('feedbackBanner');
            const inner = document.getElementById('feedbackBannerInner');
            inner.textContent = message;
            inner.className = `px-4 py-1.5 rounded-full border-3 border-[#4A3E35] font-display font-bold text-xs sm:text-sm shadow-md ${
                isSuccess ? 'bg-[#2ECC71] text-white' : 'bg-[#E74C3C] text-white'
            }`;
            banner.classList.remove('opacity-0', '-translate-y-2');
            banner.classList.add('opacity-100', 'translate-y-0');

            clearTimeout(banner.hideTimer);
            banner.hideTimer = setTimeout(() => {
                banner.classList.remove('opacity-100', 'translate-y-0');
                banner.classList.add('opacity-0', '-translate-y-2');
            }, 1600);
        }

        function spawnCelebrationNotes(x, y, color) {
            const symbols = ['♪', '♫', '♩'];
            for (let i = 0; i < 6; i++) {
                floatingParticles.push({
                    x: x + (Math.random() * 20 - 10),
                    y: y + (Math.random() * 20 - 10),
                    vx: (Math.random() - 0.3) * 90,
                    vy: -40 - Math.random() * 70,
                    symbol: symbols[i % symbols.length],
                    color: color,
                    alpha: 1
                });
            }
        }

        function drawFloatingParticles(dt) {
            for (let i = floatingParticles.length - 1; i >= 0; i--) {
                const p = floatingParticles[i];
                p.x += p.vx * dt;
                p.y += p.vy * dt;
                p.alpha -= dt * 1.1;
                if (p.alpha <= 0) {
                    floatingParticles.splice(i, 1);
                    continue;
                }
                ctx.save();
                ctx.globalAlpha = Math.max(0, p.alpha);
                ctx.font = "bold 20px 'Fredoka', sans-serif";
                ctx.fillStyle = p.color;
                ctx.fillText(p.symbol, p.x, p.y);
                ctx.restore();
            }
        }

        // Bucle principal de animación
        function gameLoop(now) {
            const dt = Math.min(0.05, (now - lastFrameTime) / 1000);
            lastFrameTime = now;

            if (appState.isPlaying) {
                drawBackground(dt);
                updateGameLogic(dt);
                drawTwoPipesColumn();
                drawYellowChick(dt);
                drawFloatingParticles(dt);
            }

            requestAnimationFrame(gameLoop);
        }

        /**
         * 5. CONTROLES CON EL DEDO (TOUCH) Y RATÓN PARA MOVER AL POLLITO
         */
        function handlePointerMove(clientY) {
            const rect = canvas.getBoundingClientRect();
            const relY = clientY - rect.top;
            const margin = chick.radius + 10;
            chick.targetY = Math.max(margin, Math.min(canvas.height - margin, relY));
        }

        canvas.addEventListener('pointerdown', (e) => {
            chick.isDragging = true;
            handlePointerMove(e.clientY);
        });

        window.addEventListener('pointermove', (e) => {
            if (!appState.isPlaying || appState.isPausedInStudio) return;
            if (chick.isDragging || e.pointerType === 'mouse') {
                handlePointerMove(e.clientY);
            }
        });

        window.addEventListener('pointerup', () => {
            chick.isDragging = false;
        });

        canvas.addEventListener('touchmove', (e) => {
            if (e.touches.length > 0) {
                handlePointerMove(e.touches[0].clientY);
            }
        }, { passive: true });

        // Soporte adicional para flechas de teclado en ordenadores
        window.addEventListener('keydown', (e) => {
            if (!appState.isPlaying || appState.isPausedInStudio) return;
            if (e.key === 'ArrowUp' || e.key === 'w' || e.key === 'W') {
                chick.targetY = canvas.height * 0.27;
            } else if (e.key === 'ArrowDown' || e.key === 's' || e.key === 'S') {
                chick.targetY = canvas.height * 0.73;
            } else if (e.key === ' ') {
                if (appState.currentTargetNote) piano.playNote(appState.currentTargetNote);
            }
        });

        /**
         * 6. NAVEGACIÓN ENTRE PANTALLAS Y EVENTOS DE INTERFAZ
         */
        function startGame() {
            document.getElementById('welcomeScreen').classList.add('hidden');
            document.getElementById('gameScreen').classList.remove('hidden');
            document.getElementById('backToMenuBtn').classList.remove('hidden');

            appState.isPlaying = true;
            appState.isPausedInStudio = false;
            resizeCanvas();
            chick.y = canvas.height / 2;
            chick.targetY = canvas.height / 2;
            spawnTwoPipesWall();
        }

        function returnToWelcomeMenu() {
            appState.isPlaying = false;
            document.getElementById('gameScreen').classList.add('hidden');
            document.getElementById('backToMenuBtn').classList.add('hidden');
            document.getElementById('welcomeScreen').classList.remove('hidden');
        }

        function openNoteStudio() {
            appState.isPausedInStudio = true;
            renderNoteSelectors();
            document.getElementById('noteStudioModal').classList.remove('hidden');
        }

        function closeNoteStudioAndResume() {
            piano.stopSequence();
            document.getElementById('noteStudioModal').classList.add('hidden');
            appState.isPausedInStudio = false;

            // Si el usuario abrió el estudio desde la bienvenida y pulsa "Ir al juego otra vez", iniciamos o reanudamos
            if (!appState.isPlaying) {
                startGame();
            } else if (appState.currentTargetNote) {
                // Volver a tocar la nota actual al regresar al juego
                piano.playNote(appState.currentTargetNote);
            }
        }

        window.onload = function () {
            renderNoteSelectors();
            setSpeedMultiplier(1);
            resizeCanvas();

            window.addEventListener('resize', resizeCanvas);

            // Botones de preajustes (De 2 en 2, de 3 en 3, de 4 en 4, Todas)
            document.querySelectorAll('.preset-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    const count = parseInt(btn.getAttribute('data-preset'), 10);
                    appState.selectedNoteIds = MUSICAL_NOTES.slice(0, count).map(n => n.id);
                    renderNoteSelectors();
                    // Sonar la última nota agregada como confirmación
                    piano.playNote(MUSICAL_NOTES[count - 1]);
                });
            });

            // Botones de velocidad en el menú (x1 a x5)
            document.querySelectorAll('.speed-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    const s = parseInt(btn.getAttribute('data-speed'), 10);
                    setSpeedMultiplier(s);
                });
            });

            // Botones de velocidad en vivo dentro del juego (1x a 5x)
            document.querySelectorAll('.live-speed-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    const s = parseInt(btn.getAttribute('data-livespeed'), 10);
                    setSpeedMultiplier(s);
                });
            });

            // Botones principales de navegación
            document.getElementById('startGameBtn').addEventListener('click', startGame);
            document.getElementById('backToMenuBtn').addEventListener('click', returnToWelcomeMenu);
            document.getElementById('openNoteStudioBtn').addEventListener('click', openNoteStudio);
            document.getElementById('openStudioFromHomeBtn').addEventListener('click', openNoteStudio);
            document.getElementById('returnToGameBtn').addEventListener('click', closeNoteStudioAndResume);

            // Botón de repetir la nota actual durante el vuelo
            document.getElementById('replayNoteBtn').addEventListener('click', () => {
                if (appState.currentTargetNote) {
                    piano.playNote(appState.currentTargetNote);
                }
            });

            // Botones de reproducir todas las notas en fila como una canción
            document.getElementById('playAllRowBtn').addEventListener('click', () => {
                piano.playNotesInRow(MUSICAL_NOTES);
            });

            document.getElementById('playActiveRowBtn').addEventListener('click', () => {
                piano.playNotesInRow(getActiveNotes());
            });

            // Iniciar bucle de animación
            lastFrameTime = performance.now();
            requestAnimationFrame(gameLoop);
        };
    </script>
</body>
</html>
