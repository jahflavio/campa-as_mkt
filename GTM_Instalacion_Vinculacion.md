# Guía: Instalación de GTM y Vinculación de Conversiones

Esta guía detalla los pasos críticos para instalar Google Tag Manager (GTM) y configurar la etiqueta de **Vinculación de Conversiones**, fundamental para medir correctamente el éxito de tus campañas de Google Ads.

---

## 1. Instalación de Google Tag Manager (GTM)

Para que GTM funcione, debes insertar dos fragmentos de código en todas las páginas de tu sitio web.

### Paso A: Obtener los códigos
1. Entra a tu cuenta de [Google Tag Manager](https://tagmanager.google.com/).
2. Haz clic en el ID de tu contenedor (formato `GTM-XXXXXX`) en la parte superior derecha.
3. Se abrirá una ventana con dos bloques de código.

### Paso B: Implementación en el sitio
1. **Código Superior (`<head>`):** Pega el primer bloque de código lo más arriba posible dentro de la etiqueta `<head>` de tu sitio web.
2. **Código Inferior (`<body>`):** Pega el segundo bloque de código inmediatamente después de la etiqueta de apertura `<body>`.

> [!IMPORTANT]
> Si usas WordPress, Shopify o Wix, existen plugins o secciones específicas donde solo debes pegar tu ID (`GTM-XXXXXX`) sin necesidad de tocar el código manualmente.

---

## 2. Configuración Detallada de "Vinculación de Conversiones" (Conversion Linker)

Esta etiqueta es el puente entre el clic del usuario en el anuncio y la conversión en tu web. Su función es leer el parámetro `gclid` (Google Click ID) de la URL y guardarlo en una **cookie de origen**, evitando bloqueos de navegadores como Safari o Firefox.

### Pasos específicos de configuración:
1. En el panel de GTM, ve a **Etiquetas** > **Nueva**.
2. Selecciona el tipo: **Vinculación de conversiones**.
3. **Configuración Avanzada (Crucial):**
   - **Vincular en todas las URLs de las páginas:** Asegúrate de que esté **siempre activado**. Esto garantiza que si el usuario navega por varias páginas antes de comprar, el ID de clic no se pierda.
   - **Habilitar vinculación entre dominios:** *Solo si tu proceso de pago o registro ocurre en un dominio diferente* (ej: de `tusitio.com` a `pagos.com`). Si lo activas, añade los dominios separados por comas.
   - **Decorar formularios:** Actívalo si el usuario debe completar un formulario que lo redirige a otro dominio. Esto pasa el ID de clic a través del formulario.

4. **Activación (Triggering) - Selección de "Initialization":**
   - No selecciones "All Pages" (Vista de página). Selecciona **Initialization - All Pages** (Inicialización).
   - **¿Por qué?** La etiqueta debe ejecutarse *antes* que cualquier otra etiqueta de conversión. Si se ejecuta después, la conversión podría dispararse sin haber leído primero el ID del clic, resultando en datos perdidos.

5. Nombre sugerido: `Vinculación de Conversiones - GLOBAL` y haz clic en **Guardar**.

> [!IMPORTANT]
> Sin esta etiqueta configurada con el disparador de **Inicialización**, puedes perder hasta un 40% de la atribución de tus conversiones en dispositivos móviles Apple.

---

## 3. Configuración Detallada de Conversiones de Google Ads

> [!IMPORTANT]
> **¿Qué cuenta usar?** Debes realizar estos pasos **en la misma cuenta de Google Ads desde la cual vas a pagar y lanzar la campaña**. Cada cuenta tiene un ID de conversión único; si usas otra cuenta, los datos de conversión no se mostrarán en tus reportes de campaña.

Una vez instalado GTM y el Vinculador de Conversiones, debes crear la etiqueta específica para cada acción que quieras medir (ej: envío de formulario, clic en WhatsApp).

### Paso A: Crear la conversión en Google Ads
1. En tu cuenta de Google Ads, ve a **Objetivos** > **Conversiones** > **Resumen**.
2. Haz clic en **+ Nueva acción de conversión**.
3. Selecciona **Sitio web**. Introduce tu URL y haz clic en **Analizar**.
4. Desplázate hasta "Añadir una acción de conversión manualmente mediante código" y haz clic en **+ Añadir una acción de conversión manualmente**.
5. Configura el nombre (ej: `Lead Formulario`) y el valor. Haz clic en **Hecho** y luego en **Guardar y continuar**.

### Paso B: Obtener ID y Etiqueta de Conversión
1. En la siguiente pantalla ("Instalar la etiqueta"), selecciona la opción **Utilizar Google Tag Manager**.
2. Verás dos valores fundamentales:
   - **ID de conversión** (Conversion ID): Un número (ej: `123456789`).
   - **Etiqueta de conversión** (Conversion Label): Una serie de letras y números (ej: `AbC-D1e2F3g4H5i6J`).

### Paso C: Crear la etiqueta en GTM
1. En GTM, ve a **Etiquetas** > **Nueva**.
2. **Configuración de la etiqueta:** Selecciona **Seguimiento de conversiones de Google Ads**.
3. Pega los valores que obtuviste en el Paso B:
   - **ID de conversión:** Pega el número.
   - **Etiqueta de conversión:** Pega el código de letras/números.
4. **Activación (Triggering):** Aquí decides CUÁNDO se cuenta la conversión.
   - *Opción 1 (Página de Gracias):* Crea un activador de tipo "Vista de página" donde la URL contenga `/gracias`.
   - *Opción 2 (Botón de WhatsApp):* Crea un activador de tipo "Solo enlaces" donde "Click URL" contenga `wa.me`.

5. Haz clic en **Guardar**.

---

## 4. Verificación y Publicación

Nada de lo que hagas funcionará si no lo publicas.

1. **Vista Previa:** Haz clic en el botón **Vista previa** (Preview) en la esquina superior derecha de GTM.
2. **Tag Assistant:** Introduce la URL de tu sitio. Realiza la acción (ej: rellena el formulario) y verifica que en la ventana de Tag Assistant la etiqueta pase de "Tags Not Fired" a **"Tags Fired"**.
3. **Publicar:** Si funciona, vuelve a GTM y haz clic en **Enviar** > **Publicar**.

> [!TIP]
> Si la etiqueta de "Vinculación de Conversiones" aparece como "Fired" en todas las páginas, tu configuración de Google Ads funcionará mucho mejor.
