
# Guía de Instalación: Node.js, Angular CLI y MongoDB (para VS Code)

Esta guía te llevará paso a paso en la instalación del entorno necesario para desarrollar con el **Stack MEAN (MongoDB, Express, Angular, Node.js)**, usando **Visual Studio Code** como editor principal.

---

## 1. Requisitos previos

- Tener instalado **Visual Studio Code**:  
  👉 [Descargar VS Code](https://code.visualstudio.com/)

- Conexión a internet estable.

---

## 2. Instalación de Node.js y npm

### Paso 1: Descargar Node.js
1. Visita el sitio oficial: [https://nodejs.org](https://nodejs.org)
2. Descarga la versión **LTS (Long Term Support)** recomendada para tu sistema operativo (Windows, macOS o Linux).
3. Ejecuta el instalador y deja las opciones por defecto.
4. Asegúrate de marcar la casilla **"Automatically install the necessary tools"** si aparece.

###  Paso 2: Verificar instalación
Abre **VS Code**, abre una terminal (`Ctrl + ñ`) y escribe:

```bash
node -v
npm -v
```

Si ves algo como `v22.x.x` y `10.x.x`, la instalación fue exitosa.

###  Paso 3: Configurar variable de entorno (si Node no se reconoce)
En algunos casos, debes agregar la ruta de Node.js al **PATH** de Windows.

1. Abre el menú inicio y busca “Editar las variables de entorno del sistema”.
2. En la ventana que aparece, selecciona **Variables de entorno**.
3. En **Variables del sistema**, busca y edita la variable `Path`.
4. Agrega una nueva ruta (normalmente):  
   `C:\Program Files\nodejs\`
5. Guarda y reinicia VS Code.

---

## 3. Instalación de Angular CLI

La CLI (Command Line Interface) de Angular permite crear y administrar proyectos fácilmente.

###  Paso 1: Instalar globalmente

```bash
npm install -g @angular/cli
```

###  Paso 2: Verificar versión

```bash
ng version
```

Deberías ver información de Angular y Node.js.

### Alternativa (sin instalación global)
Si prefieres evitar instalaciones globales, puedes usar `npx`:

```bash
npx -p @angular/cli ng new mi-app
```

---

##  4. Instalación de MongoDB Community Server

###  Opción 1: Instalar localmente (recomendado)

#### 🪟 Windows
1. Ir a: [https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)
2. Descargar el instalador **MSI**.
3. Durante la instalación:
   - Selecciona **Complete**.
   - Marca **Run service as Network Service user**.
   - Activa la opción **Install MongoDB as a Service**.
4. Finaliza la instalación.

#### 🍎 macOS (con Homebrew)
```bash
brew tap mongodb/brew
brew install mongodb-community@8.0
brew services start mongodb-community@8.0
```

#### 🐧 Linux (Ubuntu/Debian)
```bash
curl -fsSL https://pgp.mongodb.com/server-8.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-8.0.gpg --dearmor

echo "deb [ signed-by=/usr/share/keyrings/mongodb-server-8.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/8.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-8.0.list

sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl start mongod
sudo systemctl enable mongod
```

### Paso 2: Verificar instalación
En la terminal:

```bash
mongosh
```

Si abre la consola de MongoDB, todo está correcto.

### Paso 3: (Opcional) Instalar MongoDB Compass
MongoDB Compass es una herramienta visual para explorar tus bases de datos.

👉 [Descargar MongoDB Compass](https://www.mongodb.com/try/download/compass)

---

## 5. Verificación completa del entorno

Abre VS Code y en la terminal ejecuta:

```bash
node -v
npm -v
ng version
mongosh --version
```

Todos deben responder con una versión válida.

---

##  6. Prueba rápida del entorno

### Crear un proyecto Angular de prueba

```bash
ng new demo-app
cd demo-app
ng serve --open
```

Esto abrirá la app en `http://localhost:4200`

### Verificar MongoDB en ejecución

```bash
mongosh
show dbs
```

---

## ¡Listo!
Tu entorno está preparado para comenzar el desarrollo con el **Stack MEAN** usando **Visual Studio Code**.


