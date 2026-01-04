# Guía de Instalación: Entorno de Desarrollo - Procesamiento Streaming

Esta guía detalla los pasos necesarios para configurar tu entorno de desarrollo para el curso de Procesamiento Streaming. Sigue las instrucciones cuidadosamente según tu sistema operativo.

---

## 1. Configuración de Winutils (Solo para Windows)

Hadoop requiere binarios nativos para funcionar correctamente en sistemas Windows.

1. **Descarga:** Accede al repositorio de [winutils hadoop-3.1.0](https://github.com/cdarlint/winutils/tree/master/hadoop-3.1.0/bin).
2. **Preparación:**
   * Crea una carpeta en tu raíz, por ejemplo: `C:\hadoop`.
   * Dentro de esa carpeta, crea otra llamada `bin`.
   * Descarga todos los archivos del enlace anterior (especialmente `winutils.exe` y `hadoop.dll`) y colócalos dentro de `C:\hadoop\bin`.
3. **Variables de Entorno:**
   * En el buscador de Windows escribe: **"Editar las variables de entorno del sistema"**.
   * Haz clic en el botón **Variables de entorno**.
   * En **Variables del sistema**, pulsa **Nueva**:
     * Nombre: `HADOOP_HOME`
     * Valor: `C:\hadoop`
   * Busca la variable **Path**, selecciónala y pulsa **Editar**.
   * Haz clic en **Nuevo** y añade: `%HADOOP_HOME%\bin`.
4. **Reinicio:** Reinicia cualquier terminal abierta o VS Code para que reconozca los cambios.

---

## 2. Visual Studio Code

1. Descarga el instalador desde [code.visualstudio.com](https://code.visualstudio.com/).
2. Instala la aplicación siguiendo los pasos del asistente.
3. **Tip:** Asegúrate de marcar la casilla "Agregar al PATH" durante la instalación.

---

## 3. Extensión Metals para Scala

Metals es el Language Server que proporciona soporte inteligente para Scala en VS Code.

1. Abre Visual Studio Code.
2. Ve a la vista de **Extensiones** (icono de cuadrados en la barra lateral izquierda o `Ctrl+Shift+X`).
3. Busca **"Metals"**.
4. Instala la extensión oficial **Scala (Metals)**.

---

## 4. Instalación de sbt (Scala Build Tool)

### En Windows (Método recomendado)
1. Descarga el instalador **MSI** desde la [página oficial de sbt](https://www.scala-sbt.org/download.html).
2. Ejecuta el instalador y sigue las instrucciones.

### En macOS (Método recomendado)
1. Utiliza **Homebrew** desde la terminal:
   ```bash
   brew install sbt


## 5. Instalar OpenJDK 17 (Temurin)

El curso utiliza Java 17. Es crucial usar esta versión para evitar problemas de compatibilidad.

1.  **Descarga:** Ve a [Adoptium (Temurin) JDK 17](https://adoptium.net/temurin/releases/?version=17).
2.  **Instalación:**
    * Descarga el instalador adecuado para tu sistema (`.msi` para Windows, `.pkg` para macOS).
    * Ejecútalo e instala con las opciones por defecto.
3.  **Verificación:**
    * Abre una nueva terminal (PowerShell, CMD o Terminal).
    * Ejecuta el comando:
        ```bash
        java -version
        ```
    * **Resultado esperado:** Debes ver una salida que comience por `openjdk version "17.0.x"`.
    * *Nota:* Si ves una versión antigua (como 1.8 o 11), deberás ajustar tu variable de entorno `JAVA_HOME` o desinstalar las versiones anteriores.

---

## 6. Configuración del Repositorio (Fork y Clonar)

1.  **Hacer Fork:**
    * Entra en el repositorio oficial: [https://github.com/universidadcomillas/procesamiento-streaming-2026.git](https://github.com/universidadcomillas/procesamiento-streaming-2026.git).
    * Haz clic en el botón **Fork** (arriba a la derecha) para crear una copia del proyecto en tu cuenta personal de GitHub.
2.  **Obtener URL:**
    * Ve a **tu** repositorio forkeado (asegúrate de que en la URL aparezca tu nombre de usuario).
    * Haz clic en el botón verde **Code** y copia la URL (HTTPS).
3.  **Clonar en Visual Studio Code:**
    * Abre VS Code.
    * Abre la paleta de comandos con `Ctrl+Shift+P` (o `Cmd+Shift+P` en Mac).
    * Escribe y selecciona: `Git: Clone`.
    * Pega la URL que copiaste y presiona Enter.
    * Selecciona una carpeta en tu ordenador para descargar el proyecto.
4.  **Importar Build (Metals):**
    * Cuando VS Code abra la carpeta descargada, la extensión **Metals** detectará el archivo de configuración.
    * Verás una notificación abajo a la derecha: *"New Scala workspace detected..."*.
    * Haz clic en **Import** para que se descarguen las dependencias y se configure el entorno.