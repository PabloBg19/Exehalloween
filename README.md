# 🎃 Gestor Halloween Pro

Aplicación de escritorio desarrollada en **JavaFX** y distribuida profesionalmente para **Windows**
mediante **Maven, Launch4j e Inno Setup**, incluyendo un **JRE embebido** para su ejecución en equipos
sin Java instalado.

---

## 📌 Supuesto Práctico

Este proyecto corresponde al supuesto práctico de **“Desarrollo y Distribución de una Aplicación”**.

El objetivo ha sido completar **todo el ciclo real de distribución de software**, simulando un
entorno profesional en el que una empresa debe entregar una aplicación **lista para instalar y usar**
en equipos Windows.

---

## 🧰 Tecnologías utilizadas

- Java 21  
- JavaFX  
- Maven  
- Launch4j  
- Inno Setup  

---

## 📁 Evidencias del proceso

### 🔹 Patrón Launcher (solución JavaFX)

![Launcher](Captura%20de%20pantalla%202026-01-13%20084053.png)

El uso de una clase Launcher permite ejecutar correctamente la aplicación JavaFX desde un JAR
ejecutable, evitando el error *JavaFX runtime components are missing*.

---

### 🔹 JRE embebido

![JRE](Captura%20de%20pantalla%202026-01-13%20084114.png)

Se incluye un JRE completo dentro del proyecto para garantizar la ejecución en equipos sin Java
instalado.

---

### 🔹 Script de Inno Setup

![Inno Setup Script](Captura%20de%20pantalla%202026-01-13%20084146.png)

Configuración del instalador con copia correcta del ejecutable, documentación y JRE.

---

### 🔹 Instalación completada

![Instalación](Captura%20de%20pantalla%202026-01-13%20084224.png)

La aplicación se instala correctamente y genera los archivos de desinstalación.

---

### 🔹 Publicación en GitHub

![GitHub Release](Captura%20de%20pantalla%202026-01-13%20084320.png)

Repositorio con evidencias y archivos finales listos para distribución.

---

## 🏁 Conclusión

El proyecto demuestra un proceso completo y profesional de despliegue de una aplicación JavaFX,
incluyendo generación de JAR, creación de ejecutable, instalador Windows y pruebas finales,
cumpliendo todos los criterios de la rúbrica de evaluación.
