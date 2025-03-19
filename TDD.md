# 1. Lista de características obtenidas del GDD

Basado en el análisis del Game Design Document, se han identificado las siguientes características clave que definen los requisitos técnicos para el desarrollo de Elneitor:

## 1.1 Características principales:
- Juego 2D de alta definición con estilo artístico detallado y efectos dimensionales
- Género Metroidvania con exploración no lineal y entornos interconectados
- Resolución objetivo: 1280x720 a 60 FPS estable

## 1.2 Mecánicas de juego:
- Sistema de combate dinámico con múltiples estilos de ataque:
  - Ataque básico
  - Ataque cargado
  - Combo de ataques
  - Ataque aéreo
  - Bloqueo
- Sistema de movimiento avanzado:
  - Movimiento lateral
  - Salto y doble salto
  - Dash/evasión
  - Correr
  - Agacharse
- Sistema de habilidades desbloqueables que modifican la exploración y el combate
- Sistema de decisiones que afectan el final del juego (múltiples finales)

## 1.3 Estructura de juego:
- Mundo dividido en secciones distintas, cada una con:
  - Enemigos únicos
  - Desafíos específicos
  - Jefes con mecánicas propias
- Progresión del jugador a través de la adquisición de habilidades
- Narrativa ambiental que se revela a través de la exploración

## 1.4 Elementos visuales y de interfaz:
- HUD con:
  - Barra de salud
  - Indicadores de habilidades especiales
  - Minimapa
  - Contador de objetos secretos
- Elementos contextuales como indicadores de interacción
- Cinemáticas en momentos clave para avanzar la narrativa
- Efectos visuales con energía dimensional y transiciones entre realidades

## 1.5 Personajes y enemigos:
- Protagonista: Guerrero misterioso con habilidades desbloqueables
- Jerarquía de enemigos (básicos, intermedios y avanzados)
- Jefes con mecánicas específicas al final de cada sección

## 1.6 Audio:
- Efectos de sonido para combate, movimiento y entorno
- Música atmosférica acorde a las diferentes secciones del mundo

# 2. Elección de Game Engine

## 2.1 Motor seleccionado: Unity 2D

Para el desarrollo de Elneitor, se ha seleccionado Unity como motor de desarrollo por las siguientes razones:

### 2.1.1 Justificación técnica:
- Capacidades 2D robustas:
  - Sistema de sprites optimizado
  - Herramientas específicas para juegos 2D (Sprite Editor, 2D Animation)
  - Sistema de física 2D mediante Box2D
  - Tilemaps y Rule Tiles para creación eficiente de niveles
- Rendimiento optimizado para lograr los 60 FPS estables requeridos
- Pipeline de renderizado 2D con soporte para efectos visuales avanzados
- Sistema de animación que permite crear las animaciones fluidas necesarias para el combate
- Curva de aprendizaje moderada para implementar las mecánicas complejas
- Herramientas de scripting en C# que facilitan la implementación de sistemas complejos

### 2.1.2 Ventajas específicas para Elneitor:
- Universal Render Pipeline (URP) para efectos visuales avanzados en 2D (luces, partículas)
- Sistema de animación 2D para implementar movimientos fluidos de personaje y enemigos
- Herramientas de creación de niveles 2D para diseñar entornos interconectados tipo Metroidvania
- Sistema robusto de físicas 2D para el combate y la detección de colisiones
- Animator Controller para gestionar las complejas transiciones entre animaciones de combate
- Sistema de eventos para la gestión de las decisiones que afectan la narrativa
- Asset Store con recursos complementarios que pueden acelerar el desarrollo

### 2.1.3 Alternativas consideradas:
**Godot Engine:**
- Ventajas: Open source, buen soporte para 2D, tamaño reducido
- Desventajas: Comunidad más pequeña, menos optimización para proyectos comerciales

**GameMaker Studio:**
- Ventajas: Especializado en 2D, fácil de usar
- Desventajas: Limitaciones en escalabilidad y complejidad de sistemas, lenguaje propio GML

**Gdevelop:**
- Ventajas: No requiere programación (sistema de eventos), interfaz intuitiva, exportación multiplataforma
- Desventajas: Menos flexible para mecánicas complejas, rendimiento menos optimizado para proyectos grandes, limitaciones en la personalización avanzada de sistemas

# 3. Planeación (Diagrama de Gantt)

## 3.1 Fases de desarrollo

El desarrollo de Elneitor se dividirá en las siguientes fases:

**Fase 1: Pre-producción (9 de febrero - 18 de marzo)**
- 9 - 16 de febrero: Refinamiento del GDD y creación del TDD
- 17 - 23 de febrero: Prototipado de mecánicas de movimiento
- 24 de febrero - 2 de marzo: Prototipado de mecánicas de combate
- 3 - 7 de marzo: Evaluación de prototipos y ajustes

**Fase 2: Producción - Core Mechanics (18 de marzo - 31 de marzo)**
- 10 - 17 de marzo: Implementación del sistema de movimiento y colisiones
- 18 - 24 de marzo: Implementación del sistema de combate básico
- 25 - 31 de marzo: Implementación del sistema de habilidades desbloqueables

**Fase 3: Producción - Contenido (1 de abril - 30 de abril)**
- 1 - 7 de abril: Diseño e implementación de la primera sección del mundo
- 8 - 14 de abril: Diseño e implementación de la segunda sección del mundo
- 15 - 21 de abril: Diseño e implementación de la tercera sección del mundo
- 22 - 30 de abril: Implementación de enemigos básicos, intermedios, jefes y avanzados

**Fase 4: Producción - Sistemas adicionales (1 de mayo - 15 de mayo)**
- 1 - 7 de mayo: Implementación del sistema de narrativa y decisiones
- 8 - 15 de mayo: Implementación de HUD e interfaces y cinemáticas

**Fase 5: Arte y audio (16 de mayo - 30 de mayo)**
- 16 - 22 de mayo: Creación de assets finales para personaje, enemigos y entornos
- 23 - 30 de mayo: Implementación de efectos visuales y audio

# 4. Diagramas de alto nivel

## 4.1 Arquitectura del software

**Capa Core (Core Layer):**
- Contiene los sistemas fundamentales que dan soporte a toda la aplicación
- Incluye Game Manager, Scene Manager, Input System, Save System y Event System
- Gestiona el flujo principal del juego y las interacciones básicas

**Capa de Gameplay (Gameplay Layer):**
- La capa más extensa que contiene toda la lógica de juego
- Incluye sistemas como Player Controller, Enemy Manager, Combat System
- También contiene los sistemas de Ability, Boss Controller, Physics, Narrative y Quest
- Implementa todas las mecánicas descritas en el GDD

**Capa de Presentación (Presentation Layer):**
- Responsable de la visualización y experiencia sensorial del juego
- Incluye UI Manager, Sprite Renderer, Animation Controller
- Gestiona efectos visuales y sistema de audio

**Capa de Datos (Data Layer):**
- Gestiona la persistencia y estructuras de datos del juego
- Incluye SaveData, PlayerData, LevelData, EnemyData y AbilityData
- Proporciona acceso a la información necesaria para el funcionamiento del juego

## 4.2 Diseño del sistema

1. **Game Manager (Centro)**
   - Componente central que coordina toda la funcionalidad del juego
   - Gestiona el ciclo de vida del juego y la comunicación entre subsistemas
   - Controla los estados del juego (menú principal, gameplay, pausa, etc.)

2. **Subsistemas principales**
   - **Player System**: Gestiona todo lo relacionado con el personaje jugable
     - PlayerController: Control de movimientos y acciones del jugador
     - AbilityManager: Gestión de habilidades desbloqueables
     - InputHandler: Procesamiento de entrada del usuario
   - **Enemy System**: Controla todos los aspectos de los enemigos
     - EnemyManager: Administración de poblaciones de enemigos
     - AIController: Comportamiento e inteligencia artificial
     - BossSystem: Mecánicas específicas para jefes de nivel
   - **World System**: Administra el entorno de juego y niveles
     - LevelManager: Carga y gestión de niveles
     - CheckpointSystem: Sistema de puntos de guardado
     - EnvironmentController: Interacción con elementos del entorno
   - **UI System**: Gestiona todas las interfaces de usuario
     - UIManager: Coordinación general de interfaces
     - HUDController: Elementos de interfaz durante el gameplay
     - MenuSystem: Gestión de menús del juego

3. **Sistemas transversales**
   - **Combat System**: Maneja todas las interacciones de combate
     - DamageCalculator: Cálculo de daño y efectos
     - ComboSystem: Sistema de combos de ataque
   - **Physics System**: Controla las físicas del juego
     - CollisionDetector: Detección de colisiones
     - RigidBodyController: Control de cuerpos rígidos
   - **Audio System**: Gestiona todos los aspectos de audio
     - SoundEffectManager: Efectos de sonido
     - MusicManager: Música ambiental y adaptativa
   - **Save System**: Maneja el guardado y cargado de partidas
     - SaveDataHandler: Manejo de datos de guardado
     - PersistenceManager: Persistencia entre sesiones

**Relaciones entre componentes**

El diagrama muestra dos tipos de relaciones:
- Dependencias primarias: Conexiones directas y fundamentales entre sistemas
- Dependencias secundarias: Interacciones menos frecuentes o indirectas

# 5. Herramientas de arte

## 5.1 Software para creación de gráficos 2D

### 5.1.1 Adobe Photoshop
- **Propósito:**
  - Creación de conceptos artísticos
  - Diseño de fondos y elementos del entorno
  - Edición y optimización de texturas
- **Flujo de trabajo:**
  - Creación de capas separadas para facilitar animaciones
  - Exportación en formato PNG con transparencia

### 5.1.2 Piskel
- **Propósito:**
  - Diseño de sprites del juego
- **Flujo de trabajo:**
  - Creación de sprites de manera rápida y eficaz
  - Exportación en formatos PNG

## 5.2 Optimización de assets
- Formato de imágenes: PNG con compresión para sprites con transparencia
- Densidad de píxeles: Consistente entre todos los elementos del juego

## 5.3 Estilo artístico y paleta de colores
- Estilo: Arte 2D de alta definición con efectos dimensionales
- Referencia estética: Fusión de misterio y épica dimensional
- Paleta principal: Tonos oscuros con destellos de energía dimensional
- Consistencia visual: Guidelines establecidas para mantener coherencia

# 6. Objetos 2D, Terreno y Escenas

## 6.1 Estructura de niveles

Elneitor utilizará un sistema de niveles interconectados siguiendo el estilo Metroidvania, con las siguientes consideraciones técnicas:
- **Capas de tiles:**
  - Background (capa de fondo con paralaje)
  - Midground (plataformas y elementos interactivos)
  - Foreground (elementos decorativos en primer plano)
  - Collision (capa invisible para colisiones)

## 6.2 Elementos del mundo

### 6.2.1 Plataformas y terreno
- **Tipos de plataformas:**
  - Estáticas (colisión completa)
  - Móviles (siguiendo patrones predefinidos)
  - Destructibles (responden a ataques específicos)
  - Temporales (aparecen/desaparecen)

### 6.2.2 Elementos interactivos
- Fisuras dimensionales: Efectos visuales con partículas
- Objetos coleccionables: Para desbloquear habilidades
- Puntos de guardado: Sistema de checkpoint y carga
- Zonas de desafío: Áreas con enemigos o puzles específicos

### 6.2.3 Efectos ambientales
- Paralaje: Múltiples capas de fondo a diferentes velocidades
- Partículas ambientales: Para crear atmósfera en cada sección

# 7. Detección de colisiones, físicas e interacciones

## 7.1 Detección de colisiones:
- Los personajes no podrán atravesar objetos sólidos del entorno
- El jugador deberá saltar sobre obstáculos o rodearlos ya que no podrá atravesarlos
- La detección de colisiones será crítica para:
  - Ataques del jugador contra enemigos (hitboxes)
  - Colisiones entre personajes y enemigos
  - Impacto de enemigos contra paredes, plataformas y otros objetos
  - Objetos en caída
  - Interacciones entre habilidades y el entorno
- Para implementar la detección de colisiones:
  - Se utilizarán colliders del sistema Box2D integrado en Unity
  - Se configurará una matriz de capas de colisión para optimizar el rendimiento

## 7.2 Físicas
- Los objetos y personajes deben reaccionar a las entradas del jugador
- Las interacciones deben ser realistas
  - Las plataformas y objetos destructibles se rompen de manera convincente
  - Los enemigos reaccionan a los golpes con retroceso adecuado
- Gravedad y fricción configurables
- El sistema de física será esencial para:
  - Recoger objetos y habilidades
  - Movimiento del personaje (salto, doble salto)
  - Objetos que se rompen o transforman
- Para implementar la física:
  - Unity utilizará Rigidbody2D con configuraciones específicas según el tipo de objeto
  - Se establecerán valores de gravedad en -9.8 en el eje Y (ajustable)

## 7.3 Sistema de interacciones

**Interacción con objetos/elementos:**
- Activación de plataformas especiales
- Recogida de habilidades desbloqueables
- Interacción con fisuras dimensionales
- Activación de mecanismos y puertas
- Puntos de guardado y checkpoints

**Interacción de enemigos:**
- Los enemigos seguirán patrones predefinidos hasta ser activados por la presencia del jugador
- Una vez activados, cambiarán su comportamiento según su tipo y nivel de dificultad

**Para implementar interacciones:**
- Se usará un sistema de triggers en Unity
- Se desarrollará un EffectorSystem personalizado para efectos físicos temporales
- Se implementará un sistema de raycasting para detecciones precisas

# 8. Lógica de juego e inteligencia artificial

## 8.1 Arquitectura de la lógica de juego

### 8.1.1 Sistema de estados
- **GameStateManager**: Controla el estado general del juego
  - MainMenu, InGame, Paused, GameOver, Cinematic
- **PlayerStateManager**: Gestiona estados del jugador
  - Idle, Moving, Jumping, Attacking, Dashing, TakingDamage, Dead
- **EnemyStateManager**: Para comportamientos de enemigos
  - Patrol, Chase, Attack, Retreat, Dead

### 8.1.2 Sistema de eventos
- **EventManager**: Sistema centralizado de suscripción a eventos
- **Eventos clave:**
  - OnPlayerDamaged
  - OnEnemyDefeated
  - OnAbilityUnlocked
  - OnSectionCompleted
  - OnDecisionMade

### 8.1.3 Sistema de guardado
- **Información guardada:**
  - Progreso del jugador (habilidades, secciones completadas)
  - Estado del mundo (enemigos derrotados, objetos recogidos)
  - Decisiones tomadas
- **Implementación**: Serialización JSON con encriptación básica

## 8.2 Inteligencia artificial

### 8.2.1 Sistema de IA para enemigos básicos
- **Comportamiento:**
  - Patrullaje en rutas predefinidas
  - Detección de jugador por proximidad o línea de visión
  - Persecución simple con pathfinding básico
  - Ataques predecibles y directos

### 8.2.2 Sistema de IA para enemigos intermedios
- **Comportamiento:**
  - Patrullaje dinámico con puntos variables
  - Detección avanzada del jugador
  - Persecución con predicción de movimiento
  - Ataques variables con patrones semi-aleatorios
  - Uso de habilidades específicas

### 8.2.3 Sistema de IA para enemigos avanzados
- **Comportamiento:**
  - Estrategias adaptativas según el estilo de juego
  - Patrones de ataque complejos

### 8.2.4 Sistema de IA para jefes
- **Estructura por fases:**
  - Comportamientos específicos según porcentaje de vida
  - Evolución de patrones de ataque
  - Invocación de ayudantes

# 9. Audio y efectos visuales

## 9.1 Sistema de audio

### 9.1.1 Arquitectura de audio
- **Audio Manager**: Sistema centralizado de gestión de sonido
- **Categorías:**
  - SFX (efectos de sonido)
  - Music (música de fondo)
  - Ambient (sonidos ambientales)

### 9.1.2 Tipos de audio
- **Efectos de jugador:**
  - Pasos, saltos, aterrizajes
  - Ataques, impactos, bloqueos
  - Daño recibido, muerte
- **Efectos de enemigos:**
  - Alertas, gruñidos
  - Ataques específicos
  - Muerte
- **Efectos ambientales:**
  - Viento, fisuras dimensionales
  - Elementos interactivos
- **Música:**
  - Temas por sección
  - Variaciones para combate
  - Música para jefes
  - Melodías para eventos narrativos

## 9.2 Sistema de efectos visuales
- **Efectos de jugador:**
  - Rastros de movimiento
  - Impactos de ataques
  - Auras de habilidades
- **Efectos de enemigos:**
  - Indicadores de estado
  - Ataques específicos
  - Muerte y disolución
- **Efectos ambientales:**
  - Partículas flotantes
  - Distorsiones dimensionales
  - Iluminación dinámica

# 10. Plataforma y requerimientos de software

## 10.1 Plataforma objetivo primaria
- Windows PC

## 10.2 Requerimientos de hardware mínimos
- Procesador: Intel Core i3 (6ª generación) o AMD FX-6300
- Memoria RAM: 4 GB
- Tarjeta gráfica: NVIDIA GeForce GTX 660 o AMD Radeon R7 370
- Almacenamiento: 2 GB de espacio disponible
- DirectX: Versión 11
- Resolución mínima: 1280x720

## 10.3 Requerimientos de hardware recomendados
- Procesador: Intel Core i5 (8ª generación) o AMD Ryzen 5 2600
- Memoria RAM: 8 GB
- Tarjeta gráfica: NVIDIA GeForce GTX 1060 o AMD Radeon RX 580
- Almacenamiento: 2 GB de espacio disponible
- DirectX: Versión 11
- Resolución recomendada: 1920x1080

## 10.4 Requerimientos de software
- Sistema operativo: Windows 10/11 (64 bits)
- DirectX: Versión 11
- Plataformas adicionales: .NET Framework 4.7.1

## 10.5 Soporte para controladores
- Teclado y ratón: Control primario optimizado
- Controladores: Soporte completo para Xbox y PlayStation
