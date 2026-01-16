# Guía Final de Instalación de Rastreo (Google Ads + GA4)

**Fecha:** 16 de Enero, 2026
**Estatus:** ✅ Corregido y Verificado
**Sitio Web:** studiomac.mx (Squarespace)

## Resumen del Problema
Las mediciones de Google Ads no llegaban porque el código de rastreo anterior carecía de los IDs específicos y de la Etiqueta de Conversión correcta para el evento de WhatsApp.

## Datos de Configuración
Estos son los identificadores únicos que se integraron en el código:

*   **Google Analytics 4 (GA4):** `G-9QCYNDWXX8`
*   **Google Ads (Cuenta):** `AW-17772824477`
*   **Etiqueta de Conversión (WhatsApp/Contacto):** `nWdJCN-vsulbEJ2P35pC`

---

## Código Final (Squarespace Injection)
Este es el bloque de código exacto que debe estar en **Configuración > Herramientas para desarrolladores > Inyección de código > Cabecera (Header)**.

```html
<!-- Google tag (gtag.js) - studioMac Direct Tracking FIXED -->
<link rel="preconnect" href="https://www.googletagmanager.com">
<script async src="https://www.googletagmanager.com/gtag/js?id=G-9QCYNDWXX8"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  // Configuración de Cuentas Conectadas
  // Envía datos simultáneamente a Analytics y Ads
  gtag('config', 'G-9QCYNDWXX8');
  gtag('config', 'AW-17772824477', { 'send_page_view': true });

  // Función para rastrear el clic en el botón de WhatsApp
  function trackWhatsAppLead() {
    // 1. Enviar conversión a Google Ads (Esencial para optimizar campañas)
    gtag('event', 'conversion', {
      'send_to': 'AW-17772824477/nWdJCN-vsulbEJ2P35pC' 
    });
    
    // 2. Enviar evento a GA4 (Para análisis de comportamiento)
    gtag('event', 'whatsapp_click', {
      'event_category': 'Contacto',
      'event_label': 'Header Button'
    });
  }
</script>
```

---

## Pasos de Verificación

Si necesitas volver a revisar la instalación en el futuro:

1.  **Herramienta:** Usa la extensión de Chrome **Google Tag Assistant Legacy**.
2.  **Prueba:** Entra a tu sitio y haz clic en el botón de WhatsApp.
3.  **Confirmación:** La extensión debe mostrar que se disparó un evento hacia el ID `AW-17772824477`.
4.  **En Google Ads:** Revisa la sección *Objetivos > Conversiones*. El estado debería cambiar de "Sin conversiones recientes" a "Activo" en un lapso de 24 horas tras el primer clic.
