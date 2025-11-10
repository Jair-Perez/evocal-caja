# 💼 eVocal Caja

**Sistema de control de caja y ventas para eVocal Studio**

eVocal Caja es una aplicación web ligera desarrollada en **HTML, CSS y JavaScript**, conectada a **Firebase Firestore**, diseñada para gestionar los movimientos de efectivo, cierres de turno y ventas dentro del estudio.  
Su interfaz profesional está optimizada para impresión térmica de **72mm**, ideal para puntos de venta o recepción.

---

## 🚀 Características principales

- 🔐 **Inicio de sesión por PIN**  
  Cada usuario ingresa con su PIN asignado.  
  No se muestran permisos ni datos administrativos visibles.

- 🕓 **Gestión automática de turnos**  
  - Turno matutino: 9:00 a 15:00  
  - Turno vespertino: 15:00 a 21:00  
  El sistema determina el turno activo según la hora actual.

- 💰 **Control de movimientos**  
  - Ingresos y egresos visualmente diferenciados  
  - Cierre de caja con ticket detallado  
  - Historial guardado tanto en **Firestore** como en **localStorage**  

- 🧾 **Ventas**  
  - Registro de ventas en efectivo o tarjeta  
  - Generación automática de ticket de venta  
  - Desglose con venta neta, descuento, IVA (16%) y total  
  - Datos del alumno (nombre, matrícula, etc.)  
  - Ticket profesional con declaración fiscal  

- 📊 **Reportes**  
  - Cierre diario, mensual y anual (23 de diciembre)  
  - Reportes guardados en Firestore y disponibles en PDF  
  - Resumen de horas abiertas por turno  

- 🔄 **Respaldo inteligente**  
  Si no hay conexión, los datos se guardan en localStorage y se sincronizan al reconectarse.

---

## 🧩 Tecnologías utilizadas

- HTML5 / CSS3 / JavaScript (Vanilla)
- Firebase Firestore (Cloud Database)
- LocalStorage (respaldo offline)
- Impresión térmica 72mm

---

## 🧠 Estructura en Firestore

El sistema utiliza tres colecciones separadas:

```
movimientos/
ventas/
cierres/
```

Cada documento incluye metadatos (fecha, hora, usuario, turno, tipo de operación, monto, etc.)  
Los registros se mantienen organizados por fecha para reportes y auditorías.

---

## ⚙️ Configuración

1. Crea un proyecto en [Firebase Console](https://console.firebase.google.com/)
2. Activa **Firestore Database** (modo de prueba)
3. Copia tus credenciales Firebase en el bloque de inicialización dentro del HTML:
   ```js
   const firebaseConfig = {
     apiKey: "TU_API_KEY",
     authDomain: "TU_AUTH_DOMAIN",
     projectId: "TU_PROJECT_ID",
     storageBucket: "TU_STORAGE_BUCKET",
     messagingSenderId: "TU_SENDER_ID",
     appId: "TU_APP_ID"
   };
   ```

4. Sube el archivo HTML a tu servidor o GitHub Pages.

---

## 🖨️ Impresión

- Formato optimizado para **impresoras térmicas de 72 mm**
- Tipografía clara y espaciada
- Tickets incluyen:
  - Encabezado con logo eVocal Studio
  - Detalles del turno y movimientos
  - Firmas con declaración de responsabilidad
  - Información legal en letras pequeñas

---

## 🧾 Declaración de responsabilidad (en ticket)

> **Declaración de Responsabilidad y Confidencialidad**  
> Al firmar este comprobante, confirmo que he recibido la caja correspondiente al turno asignado, verificando que los montos entregados y registrados coinciden con el efectivo físico en resguardo.  
> Me comprometo a manejar los recursos bajo mi responsabilidad con total transparencia, honestidad y apego a las políticas internas de eVocal Studio.  
> Reconozco que cualquier diferencia o irregularidad deberá ser reportada inmediatamente a la Dirección para su revisión.  
> Uso exclusivo de eVocal Studio.

---

## 🛠️ Funcionalidades adicionales

- Botón **Reset (PIN maestro 1417)** para reiniciar registros sin borrar usuarios  
- Control horario en tiempo real  
- Transiciones suaves y diseño adaptable  
- Código limpio, sin dependencias externas

---

## 📦 Despliegue en GitHub Pages

1. Sube tu archivo HTML y este `README.md` a un repositorio nuevo.
2. Ve a **Settings → Pages**
3. En *Source*, selecciona la rama `main` y la carpeta raíz `/ (root)`.
4. Guarda los cambios.
5. Tu aplicación estará disponible en:  
   `https://tuusuario.github.io/evocal-caja`

---

## 📧 Contacto

Proyecto interno de **eVocal Studio**  
Para dudas o soporte técnico: [info@evocalstudio.com](mailto:info@evocalstudio.com)

---

© 2025 eVocal Studio — Todos los derechos reservados.
