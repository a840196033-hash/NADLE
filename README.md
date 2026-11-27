# NADLE
Hackathon UVM

Aplicación en *Flutter* que guía paso a paso a personas en México en trámites y servicios (salud, migración, educación y empleo), con traducción dinámica, lectura en voz alta (TTS), asistente conversacional y mapa de centros de apoyo.

About Page: https://docs.google.com/document/d/1f_1UazfnR74jKCwfmbDk2gev9UihfxklA9mrIX03Yxo/edit?tab=t.0
## Funcionalidades

## Funcionalidades principales
* Onboarding multilingüe: Selección de país, idioma (incluyendo lenguas nativas/criollas), traducción de la interfaz y nivel de lectura.
* Guías y checklist: Pasos accionables y documentos útiles por servicio con seguimiento de progreso.
* Asistente personal: Chat en el idioma del usuario con reproducción de respuestas por voz.
* Mapa y rutas:* Búsqueda de centros por categoría (flutter_map + OpenStreetMap), indicaciones paso a paso y enlace a Google Maps.
* Sesión local:* Persistencia de perfil e idioma con SharedPreferences.


## Stack tecnológico

| Capa | Tecnologías |
| :--- | :--- |
| **Frontend (Móvil / Web)** | Flutter, Dart, Material 3, Provider |
| **Persistencia y Voz** | `shared_preferences`, `flutter_tts` |
| **Backend** | Python, FastAPI, Uvicorn |
| **Inteligencia Artificial** | Google Gemini API |
| **Mapas y Ruteo** | OpenStreetMap (OSM) / OSRM |

---

## Estructura del proyecto

NADLE/
├── backend/
│   ├── main.py                      # Servidor FastAPI, CORS y endpoints principales
│   ├── requirements.txt             # Dependencias de Python (si aplica)
│   └── .env                         # Variables de entorno (API keys, configuración)
└── app_movil/
    ├── pubspec.yaml                 # Dependencias de Flutter
    └── lib/
        ├── main.dart                # Punto de entrada y configuración de Provider/Theme
        ├── models/
        │   └── nadle_models.dart    # Modelos de datos (usuario, guías, checklists, etc.)
        ├── providers/
        │   └── app_provider.dart    # Estado global, traducciones, TTS y persistencia
        ├── services/
        │   └── api_service.dart     # Cliente HTTP hacia el backend FastAPI
        └── screens/
            ├── onboarding_screen.dart  # Registro inicial, país, idioma y región
            ├── home_screen.dart        # Pantalla principal y navegación por pestañas
            ├── guia_screen.dart        # Guías paso a paso, checklist, documentos y voz
            ├── asistente_screen.dart   # Chat con el asistente de IA
            └── mapa_screen.dart        # Mapa interactivo de servicios cercanos

## Requisitos previos
* Python 3.10+ y `pip`
* Flutter SDK** instalado y configurado en el `PATH`
* Clave de API de Google Gemini** (configurada en el backend)
* Android Studio / Android SDK** *(solo necesario para emulador Android o compilar el `.apk`)

Proyecto desarrollado para **Hackatón — Quinto Semestre**.

Miguel Angel Castro Salinas
Marcos Carbajal Matias
Juan Marcos Meza Menendez
