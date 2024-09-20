
# Integración de Google Meet con Contenido Adicional en la Misma Página

Este proyecto es una prueba de concepto para integrar una videollamada de Google Meet en una página web, junto con contenido adicional que se muestra en la misma pantalla.

## Descripción del Proyecto

El propósito es mostrar cómo dividir la pantalla en dos mitades:
- **Mitad izquierda**: Botón para unirse a una videollamada de Google Meet.
- **Mitad derecha**: Contenido adicional que puede incluir información relevante mientras se lleva a cabo la videollamada.

Debido a las restricciones de seguridad que Google Meet aplica (como `X-Frame-Options` y las políticas de seguridad de contenido), no es posible incrustar Google Meet directamente en un iframe en nuestra página. Como alternativa, el usuario puede hacer clic en un botón que abrirá la videollamada en una nueva pestaña o ventana.

### Funcionalidad
1. **Botón de videollamada**: Al hacer clic en el botón "Unirse a la videollamada", se abre la URL de Google Meet en una nueva pestaña o ventana del navegador.
2. **Contenido adicional**: Se muestra en la mitad derecha de la pantalla, lo que podría incluir cualquier información útil para el usuario.

### Limitaciones

- No es posible mostrar la videollamada en la misma página utilizando un iframe debido a las restricciones de Google Meet.
- Al abrir la videollamada en una nueva pestaña o ventana, se pierde el control de la interfaz de la videollamada desde la página principal.

### Código

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Google Meet y Contenido Adicional</title>
    <style>
        body {
          display: flex;
          height: 100vh;
          margin: 0;
        }

        #video-call {
          width: 50%; /* Ocupa la mitad izquierda */
          border-right: 2px solid #ccc;
          display: flex;
          align-items: center;
          justify-content: center;
        }

        #extra-info {
          width: 50%; /* Ocupa la mitad derecha */
          padding: 20px;
        }

        button {
          padding: 10px 20px;
          font-size: 16px;
          cursor: pointer;
        }
    </style>
</head>
<body>
<!-- Contenedor para la videollamada -->
<div id="video-call">
    <!-- Botón para unirse a la videollamada -->
    <button onclick="window.open('https://meet.google.com/jrw-ensy-qex', '_blank')">Unirse a la videollamada</button>
</div>

<!-- Contenedor para información adicional -->
<div id="extra-info">
    <h1>Información adicional</h1>
    <p>Aca estaria el resto de lo q se podria mostrar si la videollamada estuviese en la misma pantalla</p>
    <p>Cuando toquen el boton se ve como se abre otra pantalla y se pierde el resto. Ademas se pierde el control</p>
    <!-- Más contenido -->
</div>
</body>
</html>
```

### Cómo Usar el Código

1. Crea un archivo `.html` con el contenido del código anterior.
2. Abre el archivo en cualquier navegador moderno.
3. Haz clic en el botón **Unirse a la videollamada** para abrir Google Meet en una nueva pestaña.
4. La mitad derecha de la página muestra contenido adicional.

### Futuras Mejoras

- **Integración de otras plataformas de videollamadas**: Se podría explorar el uso de otras plataformas como **Jitsi Meet**, que permiten incrustar videollamadas dentro de la página utilizando sus APIs o SDKs.
- **Control de la videollamada**: Investigar formas de controlar aspectos de la videollamada (como el muteo o finalizar la llamada) desde la misma página.

---

