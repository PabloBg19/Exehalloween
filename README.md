# 🎃 Gestor Halloween Pro

Aplicación de escritorio desarrollada en **JavaFX** y distribuida profesionalmente para **Windows**
mediante **Maven, Launch4j e Inno Setup**, incluyendo un **JRE embebido** que permite su ejecución
en equipos sin Java instalado.

---

## 📌 Supuesto Práctico

Este proyecto corresponde al supuesto práctico de **“Desarrollo y Distribución de una Aplicación”**.

El objetivo ha sido completar **todo el ciclo real de distribución de software**, simulando un entorno
profesional en el que una empresa debe entregar una aplicación **lista para instalar y usar**
en equipos Windows.

La aplicación final se distribuye mediante un **instalador ejecutable (.exe)** que:

- No requiere Java instalado.
- No muestra consola.
- Permite instalación y desinstalación completa.

---

## 🧰 Tecnologías utilizadas

- **Java 21**
- **JavaFX**
- **Maven**
- **Launch4j**
- **Inno Setup**
- **Windows 10 / 11**

---

## 📁 Estructura del proyecto

```
Exehalloween/
│
├── jre/                      # JRE 21 embebido
├── src/                      # Código fuente JavaFX
├── target/                   # JAR generado por Maven
│
├── LoginHalloween.exe        # Ejecutable generado con Launch4j
├── Instalador_Halloween.exe # Instalador final
├── temp.iss                 # Script de Inno Setup
├── licencia.txt             # Licencia del software
├── pom.xml                  # Configuración Maven
└── README.md                # Documentación
```

---

## 🚀 Fase 1 — Generación del JAR ejecutable (Maven)

Se generó un **JAR ejecutable** utilizando Maven y el plugin **maven-shade-plugin**, creando un
*Fat JAR* con todas las dependencias necesarias, especialmente JavaFX.

Antes de continuar con el proceso de distribución, se comprobó obligatoriamente que el JAR
funcionaba correctamente ejecutándolo desde consola:

```
java -jar target/LoginHalloween.jar
```

### ❌ Problema encontrado

```
JavaFX runtime components are missing
```

### ✅ Solución aplicada — Patrón Launcher

Para resolver este problema se implementó el **patrón Launcher**, creando una clase intermedia
con el método `main` que lanza la aplicación JavaFX real.

Esta clase se configuró como `Main-Class` en el archivo `pom.xml`, permitiendo la correcta
ejecución del JAR.

### 📸 Evidencia: clase Launcher

![Launcher](Captura%20de%20pantalla%202026-01-13%20084053.png)

---

## 🧩 Fase 2 — Creación del ejecutable (.exe) con Launch4j

Una vez validado el JAR, se utilizó **Launch4j** para generar el ejecutable:

**LoginHalloween.exe**

### Configuración principal

- Header type: **GUI**
- JAR de entrada: generado por Maven
- Ejecutable de salida: LoginHalloween.exe
- Ruta del JRE: **jre** (ruta relativa)

### ❌ Problema encontrado

La aplicación no se ejecutaba correctamente en equipos que no tenían Java instalado.

### ✅ Solución aplicada — JRE embebido

Se incluyó un **JRE 21 completo** dentro del proyecto, ubicado en la carpeta `jre`.
Launch4j se configuró para utilizar este JRE mediante una ruta relativa, garantizando
la portabilidad de la aplicación.

### 📸 Evidencia: estructura del JRE

![JRE](Captura%20de%20pantalla%202026-01-13%20084114.png)

---

## 📦 Fase 3 — Instalador para Windows con Inno Setup

Para la distribución final se creó un instalador profesional para Windows:

**Instalador_Halloween.exe**

El instalador fue desarrollado utilizando **Inno Setup**, permitiendo una instalación guiada,
clara y completamente funcional.

### Funciones del instalador

- Copia la aplicación en el sistema.
- Mantiene la estructura completa del JRE embebido.
- Crea accesos directos en el escritorio y menú inicio.
- Permite desinstalación completa sin dejar restos.

### 📸 Evidencia: Script de Inno Setup

![InnoSetup](Captura%20de%20pantalla%202026-01-13%20084146.png)

---

## 🧪 Pruebas realizadas

Antes de la entrega final se realizaron las siguientes pruebas:

- Instalación en un equipo **sin Java instalado**.
- Ejecución correcta desde el acceso directo.
- Funcionamiento correcto de la interfaz JavaFX.
- Desinstalación completa sin dejar archivos residuales.

### 📸 Evidencia: instalación correcta

![Instalación](Captura%20de%20pantalla%202026-01-13%20084224.png)

---

## ✨ Originalidad y cuidado del producto final

Se ha cuidado especialmente la presentación final del producto:

- Nombre comercial personalizado: **Gestor Halloween Pro**
- Iconos propios.
- Instalador con estilo moderno (Windows 11 dark).
- Estructura de carpetas profesional.
- Experiencia de usuario cuidada.

---

## 📤 Publicación y entrega

El proyecto se encuentra publicado en GitHub junto con todas las evidencias del proceso,
incluyendo ejecutable, instalador y documentación.

### 📸 Evidencia: repositorio y release

![GitHub](Captura%20de%20pantalla%202026-01-13%20084320.png)

---

## 🏁 Conclusión

Este proyecto demuestra el proceso completo de **despliegue profesional de una aplicación JavaFX**,
convirtiendo un proyecto de desarrollo en un **producto instalable, portable y autónomo** para
Windows.

Se cumplen todos los requisitos del supuesto práctico y los criterios establecidos en la
rúbrica de evaluación.
