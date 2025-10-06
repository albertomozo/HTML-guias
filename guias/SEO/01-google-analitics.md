# 📊 Guía rápida de Google Analytics 4 (GA4)

### 1️⃣ Conceptos básicos

* **Propiedad (Property)** → El sitio web o app que analizas.
* **Flujo de datos (Data Stream)** → Conexión entre tu web/app y GA4 (ej. un flujo web con la URL de tu página).
* **Eventos (Events)** → Cualquier acción que ocurre en tu web (clics, visitas, descargas).
* **Conversiones** → Eventos importantes que marcan éxito (compras, formularios enviados).

👉 En GA4 todo gira alrededor de **eventos**, no de páginas vistas como antes en Universal Analytics.

---

### 2️⃣ Cómo empezar

1. **Crear propiedad GA4** en [Google Analytics](https://analytics.google.com).
2. **Añadir flujo de datos web** → pega la URL de tu web.
3. **Instalar el tag** con Google Tag Manager o copiando el código en el `<head>`.

---

### 3️⃣ Métricas clave que deberías mirar

* **Usuarios** → Personas que visitan tu web.
* **Sesiones** → Conjunto de interacciones en una visita.
* **Tasa de interacción** → Sesiones con más de 10s, 2+ páginas vistas o conversión.
* **Eventos** → Qué hacen los usuarios (scroll, clic en botón, reproducir vídeo…).
* **Conversiones** → Objetivos de negocio (ej. envío de formulario).

---

### 4️⃣ Informes principales

* **Inicio** → Vista general (usuarios, fuentes de tráfico).
* **Tiempo real** → Qué está pasando ahora mismo.
* **Adquisición** → De dónde vienen tus visitantes (Google, redes sociales, email).
* **Compromiso** → Qué hacen dentro de tu web (páginas vistas, eventos, conversiones).
* **Monetización** (si tienes e-commerce) → ingresos, productos vendidos.
* **Retención** → Usuarios que vuelven a tu web con el tiempo.

---

### 5️⃣ Conversiones (muy importante)

1. Ve a **Configuración > Eventos**.
2. Marca como conversión los eventos clave:

   * `form_submit` (formulario enviado).
   * `purchase` (compra).
   * `generate_lead` (solicitud de información).
     👉 Esto conecta tus objetivos de negocio con la analítica.

---

### 6️⃣ Segmentación

* Puedes crear **audiencias personalizadas** (ej. “usuarios que visitaron la página de precios pero no compraron”).
* Esto es muy útil para **remarketing** en Google Ads.

---

### 7️⃣ Consejos prácticos para marketing

* Configura **Google Search Console** y conéctalo a GA4 para ver datos SEO.
* Usa **Exploraciones** (Analysis Hub) para crear informes más visuales.
* Mira la **fuente de tráfico**: te dice qué canal realmente convierte (SEO, Ads, redes…).
* Revisa una vez por semana → no te pierdas en los datos diarios.

---

📌 **Checklist rápido para GA4**:

* [ ] Tengo instalado el código de seguimiento.
* [ ] He definido mis conversiones (formulario, compra, lead).
* [ ] Sé de dónde viene mi tráfico (Adquisición).
* [ ] Sé qué hacen en mi web (Compromiso).
* [ ] Sé si cumplen mis objetivos (Conversiones).

---


