# 🚦 Simulador de Tráfico

Simulador de tráfico en **Java** con interfaz gráfica **Swing** y arquitectura **MVC**.


## 🎯 Objetivo

Diseñar e implementar un simulador de tráfico basado en eventos que aplique la **programación orientada a objetos (POO)** y una **interfaz gráfica con el patrón MVC**.

La simulación avanza por *ticks*: se ejecutan los eventos programados (crear cruces, carreteras y vehículos, cambiar el clima o la contaminación) y se actualizan carreteras, vehículos y semáforos. Puede ejecutarse en **modo gráfico** (por defecto) o en **modo consola**, que genera un informe JSON.

## 🧱 Programación orientada a objetos (POO)

- **Herencia y polimorfismo:** `SimulatedObject` es la base de `Junction`, `Road` y `Vehicle`. `Road` es abstracta, con `CityRoad` e `InterCityRoad`, que calculan de forma distinta la contaminación y la velocidad.
- **Strategy:** los cruces usan estrategias intercambiables para los semáforos (`RoundRobin`, `MostCrowded`) y las colas (`MoveFirst`, `MoveAll`).
- **Factory y Builder genéricos:** crean eventos y estrategias a partir de JSON.
- **Observer:** el simulador notifica a las vistas sin conocerlas.

## 🖥️ Interfaz gráfica con MVC

- **Modelo** (`simulator.model`): lógica de la simulación, sin Swing.
- **Vista** (`simulator.view`): ventana, barra de herramientas, tablas de eventos, vehículos, carreteras y cruces, y mapas. Todos los componentes son observadores y se actualizan solos.
- **Controlador** (`simulator.control`): `Controller` es el único punto de acceso de la vista al modelo.

<img width="1917" height="1016" alt="image" src="https://github.com/user-attachments/assets/4c3dad18-7e5b-4ecf-8003-fe63c6f5d24f" />

## ✅ Pruebas

Tests JUnit 5 en `tests/` y `extra.testing.TestExamples`, que compara con los `*.expout.json` de ejemplo.

---

**Autores:** Bruno Lozano Clemente y José Baute Fariña

> ⚠️ **Warning:** Este es un proyecto universitario, publicado con el objetivo de mostrar nuestro trabajo. **No se recomienda a otros estudiantes copiarlo.** Copiarlo impide que aprendas lo que la práctica pretende enseñar.


