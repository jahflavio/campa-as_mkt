# Guía Maestra de Ejecución: Estrategia studioMac (Fases 1, 2 y 3)

Esta guía consolida todos los planes (`plan-fase-1.md`, `plan-fase-2.md`, etc.) y la documentación técnica de Google Ads en una sola lista de tareas ejecutable paso a paso.

**Fecha de Inicio:** Lunes 12 de Enero, 2026.

---

## 🏗️ Fase 1: Cimientos y Reconocimiento Local
**Objetivo:** Aparecer en el mapa cuando los vecinos busquen clases.
**Duración:** 12 Ene - 23 Ene
**Estrategia de Puja:** [Maximizar Clics](https://support.google.com/google-ads/answer/2472725) (Para generar tráfico inicial y datos).

### Semana 1: Infraestructura y Medición (12 - 16 Ene)

#### 🗓️ Lunes 12: El Cerebro Digital (GTM + GA4)
**CRÍTICO:** Antes de gastar un peso, necesitamos medir.
1.  **Google Tag Manager (GTM):**
    *   Crea cuenta en [tagmanager.google.com](https://tagmanager.google.com/).
    *   Instala el contenedor en el `index.html`.
    *   **Tag "Vinculación de Conversiones":** Crea esta etiqueta y actívala en "All Pages". (Vital para iPhones).
2.  **Google Analytics 4 (GA4):**
    *   Crea propiedad y conéctala a GTM.
    *   **Eventos Clave:** Configura un evento `contacto_studiomac` cuando alguien haga clic en el botón de WhatsApp (`wa.me`).
3.  **Google Maps:** Reclama y verifica tu dirección en Google Business Profile.

#### 🗓️ Martes 13: Conexión de "Cables Invisibles"
1.  **Importar Conversiones:**
    *   En Google Ads > Herramientas > Conversiones.
    *   Importa el evento `contacto_studiomac` desde GA4.
2.  **HubSpot CRM:**
    *   Instala el código de seguimiento de HubSpot en el sitio web (vía GTM o directo en HTML).
    *   Verifica que los formularios envíen datos al CRM.

#### 🗓️ Miércoles 14: Definición de Protección (Palabras Negativas)
**No tires dinero.** Crea una "Lista de Palabras Clave Negativas" en la biblioteca compartida de Ads.
*   **Añade estas palabras inmediatamente:**
    *   `gratis`, `free`, `beca`, `apoyo gobierno`, `barato`, `economico`.
    *   `online`, `en linea`, `zoom`, `remoto`, `virtual`, `distancia`.
    *   `descargar`, `pdf`, `crack`, `full`, `mega`, `serial`.
    *   `empleo`, `trabajo`, `bolsa de trabajo`, `vacantes`.
    *   `ninos`, `primaria`, `secundaria`.

#### 🗓️ Jueves 15: Configuración de Campaña Local
1.  **Crear Campaña de Búsqueda:**
    *   **Ubicación:** Búsqueda Avanzada > **Radio** > `Colonia del Valle` > **5 km**.
    *   **Exclusión:** Excluye tu propia dirección IP para no gastar clics probando tus propios anuncios.
2.  **Palabras Clave (Concordancia de Frase):**
    *   `"clases presenciales en del valle"`
    *   `"curso de diseño grafico presencial"`
    *   `"escuela de computacion cerca de mi"`
    *   `"curso photoshop cdmx presencial"`

#### 🗓️ Viernes 16: Creativos y Extensiones
1.  **Redactar Anuncios (RSA):**
    *   *Títulos:* "Clases en Del Valle", "Aprende con iMacs Pro", "100% Presencial".
    *   *Descripciones:* "Evita distracciones en casa. Ven a studioMac."
2.  **Extensiones (Aditamentos):**
    *   **Ubicación:** Vincula tu cuenta de Google Maps para que salga la dirección.
    *   **Llamada:** Pon el teléfono del negocio.
    *   **Imagen:** Sube una foto real de alumnos usando las Macs. (Sube el CTR drásticamente).

### Semana 2: Lanzamiento y Calibración (19 - 23 Ene)

#### 🗓️ Lunes 19: 🚀 LANZAMIENTO
1.  **Acción:** Publicar Campaña.
2.  **Presupuesto:** Asignar presupuesto diario.
3.  **Puja Agresiva Móvil:** Aumenta la puja +10% en Dispositivos Móviles (la gente busca direcciones en el celular).

#### 🗓️ Martes 20 - Viernes 23: Limpieza Diaria
1.  **Revisión de Términos:** Entra diario a "Términos de Búsqueda".
2.  **Acción:** Si alguien buscó "curso de excel para niños" -> Agrega "niños" a negativas.

---

## 🎨 Fase 2: Expansión Visual (Performance Max)
**Objetivo:** Impacto visual y persecución en YouTube/Gmail.
**Duración:** 26 Ene - 06 Feb
**Tipo de Campaña:** [Performance Max (PMax)](https://support.google.com/google-ads/answer/10724817)

### Semana 3: Creativos (26 - 30 Ene)
1.  **Generación IA:** Crear imágenes futuristas (Ver guía de prompts en `campana-ads.md`).
2.  **Video:** Crear video corto de 15s.
3.  **Señales de Audiencia:**
    *   Segmento "Competencia": Gente que visita webs de escuelas de diseño rivales.
    *   Segmento "Intereses": Usuarios de Mac, Diseñadores, Arquitectos.

---

## 🛠️ Fase 3: Optimización y Mantenimiento
**Objetivo:** Rentabilidad (bajar costo por lead).
**Inicio:** 09 Feb en adelante.

#### 🔄 Rutina Semanal
1.  **Palabras Negativas:** Bloqueo continuo de términos basura.
2.  **Análisis de Horarios:** Si ves que nadie convierte a las 3 AM, baja la puja a esa hora.

#### 🔄 Rutina Mensual
1.  **Smart Bidding (CPA Objetivo):**
    *   Al llegar a **30 conversiones/mes**, cambia de "Maximizar Clics" a "CPA Objetivo".
    *   Dile a Google: "Pagaré máximo $150 por lead".
2.  **Remarketing:** Activa campaña para perseguir a los que visitaron pero no compraron.

---

### Links de Referencia (Google Support)
*   [Determinar estrategia de puja](https://support.google.com/google-ads/answer/2472725)
*   [Acerca de Performance Max](https://support.google.com/google-ads/answer/10724817)
*   [Conversiones Mejoradas](https://support.google.com/google-ads/answer/9888656)
