# CRM-SIM — Contexto del Proyecto

## Concepto
Videojuego simulador de una consultora tecnológica especializada en proyectos CRM (sin mencionar marcas reales).
El jugador gestiona la oficina: contrata empleados, acepta proyectos, entrega resultados, expande la empresa.

## Género y estilo visual
- **Género**: Simulador de gestión (estilo Theme Hospital, Two Point Hospital)
- **Vista**: 2D isométrica
- **Estilo**: Pixel art
- **Plataforma objetivo**: Steam (PC/Mac)

## Motor y herramientas
- **Motor**: Godot 4 (renderer: Compatibility)
- **Lenguaje**: GDScript
- **IDE**: VS Code con extensión godot-tools
- **Version control**: Git + GitHub

## Configuración del proyecto Godot
```
Display > Window:
  Viewport Width:  320
  Viewport Height: 180
  Stretch Mode:    canvas_items
  Stretch Aspect:  keep

Rendering > Textures:
  Default Texture Filter: Nearest   ← crítico para pixel art
```

## Estructura de carpetas
```
res://
├── assets/
│   ├── fonts/
│   ├── sprites/
│   │   ├── characters/
│   │   ├── furniture/
│   │   └── tileset/
│   ├── ui/
│   └── audio/
│       ├── sfx/
│       └── music/
├── scenes/
│   ├── world/
│   │   ├── office.tscn
│   │   └── room.tscn
│   ├── entities/
│   │   ├── employee.tscn
│   │   └── desk.tscn
│   ├── ui/
│   │   ├── hud.tscn
│   │   └── panel_hire.tscn
│   └── main.tscn
├── scripts/
│   ├── core/
│   │   ├── game_manager.gd
│   │   ├── economy_manager.gd
│   │   └── time_manager.gd
│   ├── entities/
│   │   ├── employee.gd
│   │   └── project.gd
│   └── ui/
│       └── hud.gd
├── resources/
│   ├── employee_types/
│   │   ├── junior_dev.tres
│   │   └── senior_dev.tres
│   └── project_types/
│       └── crm_migration.tres
└── autoloads/
```

## Arquitectura clave
- **Nodos y Scenes**: todo es un Node, las Scenes son componentes reutilizables
- **Signals**: comunicación entre nodos (patrón Observer)
- **Autoloads (Singletons)**: GameManager, EconomyManager, TimeManager — accesibles globalmente

## Plan de fases

### FASE 0 — Setup & prototipo técnico (en curso)
- [x] Godot instalado
- [x] Proyecto creado con renderer Compatibility
- [ ] Configuración pixel art aplicada (Nearest filter, resolución baja)
- [ ] Estructura de carpetas creada
- [ ] Tutorial básico de TileMap isométrico completado
- [ ] Mapa isométrico con tiles en pantalla
- [ ] Un nodo moviéndose por el mapa

### FASE 1 — POC jugable
- Mapa isométrico con oficina básica (suelo, paredes, escritorios)
- 1 empleado con pathfinding moviéndose por la oficina
- UI simple: dinero, 1 proyecto en curso, barra de progreso
- Loop básico: aceptar proyecto → asignar empleado → esperar → cobrar

### FASE 2 — Core loop completo
- Sistema de roles: Dev Junior, Dev Senior, Project Manager, Architect
- Sistema de proyectos con requerimientos (X devs con Y skill)
- Salas: servidores, reuniones, descanso (con buffs)
- Economía: salarios mensuales, costes, facturación por proyecto
- Expansión de oficina comprando nuevas salas
- Mercado de tecnologías (CRM genérico, ERP, plataforma cloud)

### FASE 3 — Contenido & polish
- Más tipos de proyectos y empleados
- Eventos aleatorios (cliente difícil, bug crítico, empleado que se va)
- Sonido y música
- Menú principal, guardado de partida

### FASE 4 — Steam Early Access / Launch

## Roles de empleados (definidos hasta ahora)
- Junior Developer
- Senior Developer
- Project Manager
- Architect

## Mecánicas principales (definidas hasta ahora)
- Contratar y despedir empleados
- Aceptar proyectos con requerimientos de equipo
- Asignar empleados a proyectos
- Cobrar al entregar
- Pagar salarios periódicamente
- Comprar mobiliario y equipamiento
- Expandir la oficina (más salas, más espacio)

## Assets gratuitos para el POC
- **Kenney.nl** → kenney.nl/assets (pack isométrico)
- **itch.io** → buscar "isometric office pixel art free"
- **OpenGameArt.org** → assets CC

## Novedades / Decisiones tomadas
- No se menciona ninguna marca real de CRM en el juego
- El POC prioriza tener ambos aspectos básicos: visual isométrico + mecánica de gestión
- Sin prisa, se quiere hacer bien desde el principio

## Próximos pasos inmediatos
1. Aplicar configuración de pixel art en Project Settings
2. Crear la estructura de carpetas en el proyecto
3. Descargar un tileset isométrico de Kenney.nl
4. Crear la primera escena con TileMapLayer isométrico
