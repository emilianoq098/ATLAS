[README.md](https://github.com/user-attachments/files/34170509/README.md)
# ATLAS · Asistente de entrenamiento

Prototipo mobile-first para recorrer bienvenida, acceso simulado, onboarding por cinco partes, resumen personalizado y panel principal. Está construido con HTML, CSS y módulos JavaScript nativos; no requiere instalación ni compilación y no incluye un script `npm run dev`.

## Ejecutar

Los módulos ES funcionan de forma confiable bajo un servidor HTTP local:

```bash
python -m http.server 8000
```

Abre [http://localhost:8000](http://localhost:8000). También puedes usar cualquier servidor estático sencillo.

## Diseño y funcionamiento

- Interfaz centrada de hasta 480 px, con controles táctiles amplios, tipografía Barlow Condensed para títulos e Inter para lectura.
- Paleta grafito y azul eléctrico; la hoja local de estilos define los componentes y los estados de foco, selección y movimiento reducido.
- El onboarding guarda el avance por pantalla en `localStorage`; la edad, altura y peso se conservan al retroceder o recargar.
- Las herramientas de Atlas se presentan en tarjetas deslizables; el tipo corporal y las zonas de interés usan la ilustración local con un SVG accesible de respaldo.
- La cinta vertical de altura y la regla horizontal de peso admiten arrastre, rueda y teclado.
- Prueba manual de las reglas: abre Altura y Peso y comprueba, en ventanas de 360×640 y 430×900 px, que los números se ven al entrar y se desplazan con las marcas al arrastrar, usar la rueda o las flechas. Repite en modo claro y oscuro; Altura debe etiquetar cada 10 cm y Peso cada 1 kg, incluidos los extremos del rango.
- Las estimaciones usan Mifflin–St Jeor, un factor de actividad aproximado y macros orientativos. No sustituyen una evaluación profesional.
- Las preferencias de notificación se guardan en el dispositivo. La entrega de notificaciones requiere integración adicional.
- Los datos personales se asignan con `textContent` o se validan antes de guardarse; los estados persistidos están aislados por versión.

## Próximas mejoras

- Incorporar un backend con almacenamiento cifrado, consentimiento y sincronización entre dispositivos.
- Sustituir el acceso simulado por autenticación real con proveedores y gestión segura de sesiones.
- Conectar Atlas a un servicio de asistencia virtual con límites, controles de privacidad y manejo de errores.
- Añadir análisis de imágenes para alimentos, con estimaciones transparentes y revisión manual.
- Implementar notificaciones push mediante Service Worker y Push API.
- Probar en dispositivos físicos, auditar accesibilidad con tecnologías de asistencia y optimizar métricas web antes de producción.
