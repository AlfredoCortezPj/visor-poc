# visor-poc

Maqueta (prueba de concepto) del **Visor de Campo**: la interfaz web del visor de tiendas, adaptada para funcionar como **widgets de Zoho Creator** con hosting externo.

## Archivos

Cada archivo es un widget que se muestra en su propia página de la app en Creator:

| Archivo | Página en Creator | Para quién |
|---|---|---|
| `resumen.html` | Resumen | Todos los roles |
| `tiendas.html` | Tiendas | Todos los roles |
| `visitas.html` | Visitas | Todos los roles |
| `usuarios.html` | Usuarios | Maestro y supervisores |
| `campos.html` | Campos | Solo maestro |

## Cómo actualizar

1. Los cinco archivos se generan juntos desde la misma fuente y solo se diferencian en el módulo con el que arrancan. **Siempre sube los cinco a la vez**, aunque el cambio parezca de un solo módulo.
2. Súbelos con *Add file → Upload files → Commit changes* (reemplazan a los anteriores).
3. Espera a que GitHub Pages publique (pestaña *Actions*, proceso en verde; 1 a 3 minutos).
4. En Creator, recarga la página con **Ctrl + F5**.

## Requisitos en Creator

- Un widget por archivo, con hosting **Externo**, cuyo archivo de índice es la URL de GitHub Pages de ese archivo.
- Las páginas deben llamarse exactamente **Resumen, Tiendas, Visitas, Usuarios y Campos**: el salto de "Ver como" abre la página Resumen por su nombre interno.
- Los datos viven en los formularios `VC_` de la app y se actualizan con una carga diaria automática. Los formularios no se muestran en el menú.

## Cómo funciona por dentro

- Los widgets solo funcionan **dentro de Creator**: usan el SDK de widgets de Creator y la sesión del usuario logueado. Abiertos directamente en el navegador muestran un aviso y no cargan datos.
- Las tiendas del día se guardan en el navegador para que el cambio entre páginas sea rápido; se vuelven a leer solas cuando llega una carga nueva.
- En Campos, los cambios sin guardar se conservan como borrador en el navegador y se ofrece recuperarlos al volver.

## Seguridad

- Este repositorio es **público**. Los archivos no contienen datos ni credenciales: los datos se leen en el momento, con la sesión del usuario dentro de Creator.
- **Nunca subas aquí** exportaciones de datos, tokens, claves ni archivos de configuración con información interna.
- Para producción, el plan es pasar a **hosting interno** en Creator, de modo que el código no quede público.

## Estado

Maqueta en evaluación. No es la versión productiva.
