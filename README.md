# 3D Scenarios

Proyecto de escenarios 3D interactivos construido con [Three.js](https://threejs.org/). Cada escenario demuestra un tipo diferente de control de cámara o interacción con objetos 3D.

---

## Escenarios

| Escenario | Descripción | Controles |
|---|---|---|
| **Minecraft** | Terreno generado con ruido de Perlin y texturas de bloques | WASD + mouse |
| **Map Controls** | Vista aérea de una ciudad de cubos instanciados | Arrastrar, scroll, clic derecho |
| **Orbit Controls** | Caja con controles de órbita clásicos | Arrastrar, scroll |
| **Pointer Lock** | Escena FPS con físicas y colisiones | WASD + mouse capturado + espacio |
| **Transform** | Objeto manipulable con gizmos de posición, rotación y escala | W/E/R + mouse |

---

## Estructura del proyecto

```
3d-scenarios/
├── index.html
├── scenarios/
│   ├── minecraft.html
│   ├── map.html
│   ├── orbit.html
│   ├── pointerlock.html
│   └── transform.html
└── assets/
    ├── css/
    │   └── styles.css
    └── js/
        ├── core/
        │   ├── baseScene.js       # Escena, cámara y renderer base
        │   └── layout.js          # Navbar y footer compartidos
        └── scenarios/
            ├── minecraft.js
            ├── map.js
            ├── orbit.js
            ├── pointerlock.js
            └── transform.js
```

---

## Tecnologías

- [Three.js r167](https://threejs.org/) — motor de renderizado WebGL
- [lil-gui](https://lil-gui.georgealways.com/) — panel de controles
- ES Modules + Import Maps — sin bundler, corre directo en el navegador

---

## Cómo correr el proyecto

Necesitas un servidor local porque los módulos ES no funcionan desde `file://`.

**Con VS Code — Live Server:**
1. Instala la extensión [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
2. Clic derecho sobre `index.html` → **Open with Live Server**

**Con Node.js:**
```bash
npx serve .
```

**Con Python:**
```bash
python -m http.server 5501
```

Luego abre `http://127.0.0.1:5501` en el navegador.

---

## Características

- Navbar y footer persistentes en todos los escenarios
- Navegación entre escenarios sin perder contexto
- Botón para ocultar la UI en escenarios de primera persona
- Física de colisiones AABB en Pointer Lock
- Física de terreno basada en heightmap en Minecraft
- Terreno procedural con ruido de Perlin (128×128)
- 500 cubos instanciados con `InstancedMesh` en Map Controls

---

## Desarrollado por

**Daniel Alonso Esparza Roldán**  
[GitHub](https://github.com/daniel4105) · [l23200831@pachuca.tecnm.mx](mailto:l23200831@pachuca.tecnm.mx)