# Configuración Técnica Final: studioMac (Squarespace)

Este archivo contiene los datos técnicos y códigos optimizados generados durante la sesión del 15 de enero de 2026 para mejorar la velocidad del sitio y asegurar el seguimiento de campañas sin usar Google Tag Manager.

## 1. Identificadores (IDs)
- **Google Analytics 4:** `G-9QCYNDWXX8`
- **Google Ads:** `AW-17772824477`

---

## 2. Inyección de Código (Squarespace)

### HEADER (Configuración > Avanzado > Inyección de código > Header)
```html
<!-- Google tag (gtag.js) - studioMac Direct Tracking -->
<link rel="preconnect" href="https://www.googletagmanager.com">
<script async src="https://www.googletagmanager.com/gtag/js?id=G-9QCYNDWXX8"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  // Conexión directa a Analytics y Ads
  gtag('config', 'G-9QCYNDWXX8');
  gtag('config', 'AW-17772824477', { 'send_page_view': true });

  // Función para medir clics de WhatsApp
  function trackWhatsAppLead() {
    gtag('event', 'conversion', {
      'send_to': 'AW-17772824477'
    });
    gtag('event', 'generate_lead', {
      'event_label': 'WhatsApp Click'
    });
  }
</script>
```

### FOOTER (Configuración > Avanzado > Inyección de código > Footer)
```html
<!-- Botón WhatsApp y herramientas - studioMac -->
<a href="https://wa.me/525670504203?text=Hola%20vengo%20del%20sitio%20de%20StudioMac%20y%20tengo%20una%20pregunta"
   class="whatsapp-float" target="_blank" onclick="trackWhatsAppLead()" aria-label="WhatsApp">
  <svg xmlns="http://www.w3.org/2000/svg" width="35" height="35" viewBox="0,0,256,256" fill="white">
    <path d="M191.53,161.05c-6.1-3-35.93-17.75-41.5-19.79s-9.61-3.04-13.62,3s-15.54,19.78-19.05,23.82-7.1,4.52-13.2,1.52A164.55,164.55,0,0,1,64.29,127.1,181.24,181.24,0,0,1,41.93,100c-3.15-5.59-.3-8.58,2.78-11.58.58-.58,1.21-1.39,1.83-2.2s1.42-1.84,2-2.77a16.63,16.63,0,0,0,2.69-5.18,9,9,0,0,0-.46-8.5c-1.52-3-13.62-33-18.66-45.21s-10.27-10.22-14.1-10.42c-3.55-.21-7.61-.22-11.66-.22s-10.65,1.52-16.22,7.6c-5.58,6.08-21.31,20.81-21.31,50.75s21.81,58.85,24.85,63.15,42.92,66,104,92.51c14.53,6.31,25.88,10.08,34.73,12.92,14.59,4.64,27.88,4,38.38,2.4,11.71-1.75,35.93-14.7,40.92-28.84S201.17,1 192,161.12Z"></path>
  </svg>
</a>

<!-- Scripts adicionales con carga diferida -->
<script defer src="https://cdn.userway.org/widget.js" data-account="Zg9MqIt1jZ"></script>
<script type="text/javascript" id="hs-script-loader" async defer src="//js.hs-scripts.com/50761822.js"></script>

<script>
  window.addEventListener('load', function() {
    // Configuración de placeholders
    const searchInputs = document.querySelectorAll('input[type="search"], .search-input');
    searchInputs.forEach(input => input.setAttribute('placeholder', '¿Qué quieres crear hoy?'));
  });
</script>
```

---

## 3. CSS Personalizado (Diseño > CSS personalizado)
```css
/* studioMac - Estilos del Botón de WhatsApp */
.whatsapp-float {
  position: fixed;
  width: 50px;
  height: 50px;
  bottom: 20px;
  left: 20px;
  z-index: 99999;
  background: #ff4e17;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 12px rgba(0,0,0,0.3);
  transition: transform 0.3s ease;
  animation: haloPulse 2.4s infinite;
}

.whatsapp-float:hover {
  transform: scale(1.1);
}

@keyframes haloPulse {
  0% { box-shadow: 0 0 0 0 rgba(255, 78, 23, 0.5); }
  70% { box-shadow: 0 0 0 15px rgba(255, 78, 23, 0); }
  100% { box-shadow: 0 0 0 0 rgba(255, 78, 23, 0); }
}
```

---

## 4. Checklist de Configuración en Google Ads
1. **Etiquetado Automático:** Activar en *Administrador > Configuración de la cuenta*.
2. **Vinculación GA4:** Asegurar que las cuentas estén conectadas en el panel de Ads y GA4.
3. **Conversión Mejorada:** Activar si Google lo solicita para aumentar la precisión en Safari/iOS.
