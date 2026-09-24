# Constitución de GoSync Web

> Documento en elaboración conjunta. Las reglas acordadas guían la web; las decisiones aún abiertas se indican al final.

## Base del proyecto

- **Propósito:** presentar GoSync, una herramienta gratuita y de código abierto para sincronizar directorios en uno o ambos sentidos y realizar copias de seguridad comprimidas. También admite sincronización mediante FTP/SFTP.
- **Público:** desarrolladores que buscan una herramienta sencilla; destacar especialmente el uso de copias de seguridad periódicas de un directorio.
- **Objetivo de la web:** facilitar la descarga de la aplicación como acción principal y ofrecer acceso al repositorio del programa como acción secundaria.
- **Idiomas:** inglés como idioma predeterminado en `/` y español en `/es/`, con el mismo contenido funcional en ambos.
- **Tipo de sitio:** página de presentación del producto; la web no es la aplicación de sincronización.
- **Tecnología actual:** Astro, HTML, CSS y JavaScript; configuración TypeScript estricta disponible. Node.js >= 22.12.0 y npm.
- **Estado actual:** plantilla mínima de Astro; la identidad visual acordada aún no está implementada y todavía no hay contenido definitivo ni componentes propios.
- **Fuente de verdad:** las capacidades y promesas publicadas deben corresponder a funcionalidades confirmadas del producto. Esta constitución sirve de referencia para las propuestas y el desarrollo de la web.

## Principios de contenido y experiencia

- Explicar primero para qué sirve GoSync y dar protagonismo a las copias de seguridad periódicas; después mostrar la sincronización unidireccional y bidireccional, la compresión y FTP/SFTP.
- Escribir para desarrolladores con un tono directo y claro: usar términos técnicos cuando aporten precisión y explicar los que puedan resultar ambiguos. Destacar que la herramienta es gratuita y de código abierto.
- El botón principal debe conducir a la descarga y destacar visualmente. El enlace al repositorio debe ser visible, pero tener menor peso. Hasta disponer de destinos reales, usar exclusivamente las URL provisionales señaladas abajo; no inventar formatos de descarga, plataformas compatibles ni modalidades de programación de copias.
- **Destinos provisionales — TODO: sustituir antes de publicar:** descarga `https://example.com/gosync/download` y repositorio `https://example.com/gosync/source`. Son marcadores de posición, no enlaces funcionales; mantenerlos identificados como tales también en la implementación.
- Mantener el contenido equivalente y actualizado en español e inglés. Cada versión debe declarar su idioma en `lang`, ofrecer cambio de idioma visible y enlazar a su versión alternativa cuando exista.
- Orden sugerido para la página: propuesta de valor y descarga, ejemplo de copia de seguridad, otras capacidades, acceso al código y llamada final a la descarga. Ajustar este orden si las pruebas con contenido real lo justifican.

## Guía visual

- Dirección acordada: interfaz simple, enfocada en legibilidad y facilidad de uso. Tres colores de marca: **verde, morado y negro**; no añadir otros colores de acento. Usar blanco como fondo neutro y para texto sobre botones oscuros cuando sea necesario para el contraste.
- **Primario — verde `#15803d`:** acción de descarga y elementos que deban atraer primero la atención.
- **Secundario — morado `#6d28d9`:** acceso al repositorio, enlaces o detalles de apoyo; debe tener menor protagonismo que la descarga.
- **Terciario — negro `#111111`:** texto principal, encabezados y superficies oscuras; actúa como base neutra, no como otro color de llamada a la acción. Mantener estos roles en ambos idiomas.
- Para la interfaz inicial, usar un botón de descarga verde con texto blanco y un enlace al repositorio morado de estilo secundario (por ejemplo, contorno en lugar de relleno). El texto general será negro sobre blanco. Diferenciar también por texto, forma y foco, no solo por color.
- No existe logotipo todavía. Usar el nombre «GoSync» como marca tipográfica provisional, sin presentar un icono genérico como logotipo oficial.
- Usar una tipografía legible, jerarquía clara de títulos y espacio suficiente entre secciones; evitar efectos decorativos que compitan con el botón de descarga. **Propuesta:** empezar con fuentes del sistema y una escala de espaciado basada en 8 px antes de añadir recursos externos.
- Repetir los mismos patrones de botones, enlaces, tarjetas e iconos. Definir los colores como variables CSS semánticas `--color-primary`, `--color-secondary`, `--color-text` y `--color-background`; compartir también las variables de tipografía y espaciado cuando se construya la interfaz.
- Comprobar contraste y legibilidad, estados de foco y navegación por teclado. No depender solo del color para transmitir significado; respetar la preferencia de movimiento reducido si se incorporan animaciones.

## Convenciones técnicas propuestas

- Mantener las rutas en `src/pages/`; extraer piezas reutilizables a `src/components/` cuando exista una necesidad real de reutilización o claridad. Los archivos estáticos que deban conservar una URL fija van en `public/`.
- Preferir componentes `.astro` y HTML semántico. Añadir JavaScript en el navegador únicamente cuando una interacción lo necesite; valorar nuevas dependencias por su coste y utilidad.
- Usar CSS propio y estilos locales de Astro para cada componente. Compartir en una hoja global solo los fundamentos de diseño (variables de color, tipografía, espaciado y estilos base) cuando se definan.
- Usar encabezados ordenados, enlaces descriptivos y texto alternativo para imágenes informativas. Diseñar primero para pantallas pequeñas y comprobar también escritorio.
- Apoyarse en las rutas localizadas de Astro: inglés en `/` y español en `/es/`. Mantener compartidos los componentes y separar las traducciones del marcado cuando haya contenido repetido. Enlazar las versiones equivalentes y declarar el idioma correspondiente en el HTML.
- Antes de dar por terminado un cambio en la web, ejecutar `npm run build` y comprobar visualmente las vistas afectadas en móvil y escritorio. Si se inicia el servidor de desarrollo, usar `astro dev --background` y gestionarlo con `astro dev status`, `astro dev logs` y `astro dev stop`.

## Decisiones por acordar

1. **Datos para publicar:** sustituir los dos enlaces provisionales por destinos reales; confirmar plataformas soportadas, formatos de descarga y cómo se configuran las copias periódicas antes de publicar instrucciones específicas.
2. **Alcance de las convenciones:** decidir si fijamos ahora nombres y formato del código y valores detallados de diseño (tamaños, tokens, componentes) o los concretamos durante la primera implementación.

Al resolver cada punto, sustituir las preguntas por reglas concretas y ejemplos verificables.
