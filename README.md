# 🎃 Gestor Halloween Pro

Aplicación de escritorio desarrollada en **JavaFX** y distribuida profesionalmente para **Windows**
mediante **Maven, Launch4j e Inno Setup**, incluyendo un **JRE embebido** que permite su ejecución
en equipos sin Java instalado.

---

## 📌 Supuesto Práctico

Este proyecto corresponde al supuesto práctico de **“Desarrollo y Distribución de una Aplicación”**.

El objetivo ha sido completar **todo el ciclo real de distribución de software**, simulando un
entorno profesional en el que una empresa debe entregar una aplicación **lista para instalar y
usar** en equipos Windows.

La aplicación final se distribuye mediante un **instalador ejecutable (.exe)** que:
- No requiere Java instalado.
- No muestra consola.
- Permite instalación y desinstalación completa.

---

## 🧰 Tecnologías utilizadas

- Java 21  
- JavaFX  
- Maven  
- Launch4j  
- Inno Setup  
- Windows 10 / 11  

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
├── licencia.txt             # Licencia
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

### ✅ Solución aplicada

Se utilizó el **patrón Launcher**, creando una clase intermedia con el método `main` que lanza la
aplicación JavaFX real. Esta clase se configuró como `Main-Class` en el `pom.xml`.

📸 Espacio para imagen: ejecución correcta del JAR desde consola

---

## 🧩 Fase 2 — Creación del ejecutable (.exe) con Launch4j

El JAR se convirtió en el ejecutable `LoginHalloween.exe` usando Launch4j.

Configuración principal:
- Header type: **GUI**
- JAR de entrada: generado por Maven
- Ruta del JRE: **jre** (ruta relativa)

### ❌ Problema encontrado

La aplicación no se ejecutaba en equipos sin Java instalado.

### ✅ Solución aplicada

Se incluyó un **JRE 21 completo** dentro de la carpeta `jre`, garantizando que el ejecutable sea
portable y funcional en cualquier equipo Windows.

📸 Espacio para imágenes: configuración de Launch4j y carpeta jre

---

## 📦 Fase 3 — Instalador para Windows con Inno Setup

Se creó un instalador profesional para Windows llamado `Instalador_Halloween.exe`.

Funciones del instalador:
- Copia la aplicación en el sistema.
- Mantiene la estructura completa del JRE embebido.
- Crea accesos directos.
- Permite desinstalación completa.

El instalador fue personalizado con iconos propios, idioma español y estilo moderno.

📸 Espacio para imágenes: asistente de instalación y aplicación instalada

---

## 🧪 Pruebas realizadas

- Instalación en un equipo sin Java instalado.
- Ejecución correcta desde accesos directos.
- Funcionamiento correcto de la interfaz JavaFX.
- Desinstalación completa sin dejar archivos residuales.

Todas las pruebas fueron satisfactorias.

---

## ✨ Originalidad y cuidado del producto final

- Nombre comercial personalizado: **Gestor Halloween Pro**
- Iconos propios.
- Instalador moderno integrado en Windows.
- Estructura de carpetas profesional.
- Experiencia de usuario cuidada.

---

## 🏁 Conclusión

Este proyecto demuestra el proceso completo de **despliegue profesional de una aplicación JavaFX**,
convirtiendo un proyecto de desarrollo en un **producto instalable, portable y autónomo** para
Windows, cumpliendo todos los requisitos del supuesto práctico y la rúbrica de evaluación.
