# Fase 2 · Viabilidad legal y cumplimiento · Futlobby

## Introducción

Este documento esta creado con la intención de extender con las tareas del modulo de proyecto.

## 1. Protección de datos - RGPD

Nuestra plataforma recoge datos personales de usuarios europeos. Por eso debemos cumplir con el Reglamento General de Protección de Datos. Las normas son claras:

- **Consentimiento explícito:** Los usuarios tendrán que marcar un checkbox al registrarse. Este checkbox servirá para que acepten la recogida de sus datos y las políticas de la plataforma.

- **Información transparente:** Habrá una página con la política de privacidad. Esta página estará en la ruta /legal/privacidad.

- **Derechos de los usuarios:** Se crearán funciones en el sistema para que los usuarios puedan acceder, corregir, mover o eliminar sus datos.

- **Seguridad de los datos:** Las contraseñas se guardarán de forma segura con el programa bcrypt. Todas las comunicaciones se harán con el protocolo HTTPS.

- **Delegado de Protección de Datos:** No es necesario tener un delegado en esta fase. El proyecto es un prototipo sin muchos datos y no se manejan categorías especiales.

## 2. Política de cookies

Usamos cookies para gestionar sesiones y autorizar acceso con JWT. También podrían usarse cookies analíticas en el futuro. Por eso:

- **Banner de cookies:** Al entrar por primera vez, los usuarios verán un aviso que informa sobre el uso de cookies y pide su consentimiento.

- **Clasificación de cookies:** Las cookies se dividirán en técnicas, que son necesarias para el funcionamiento, y otras, como las analíticas o de terceros.

- **Gestión de preferencias:** Los usuarios tendrán una sección donde puedan elegir qué cookies aceptar o rechazar.

- **Implementación técnica:** Se creará una página en /legal/cookies y un aviso flotante para pedir el consentimiento.

## 3. Condiciones de uso y términos de servicio

Se elaborará un documento legal disponible en /legal/terminos. Este documento incluirá:

- Las normas de comportamiento que deben seguir los usuarios. Por ejemplo, no hacer reservas falsas ni maltratar a otros jugadores.

- Las limitaciones de responsabilidad de los creadores ante situaciones como cancelaciones o problemas en los campos.

- La propiedad del contenido que los usuarios generen dentro de la plataforma.

- Las causas por las que se pueden suspender o bloquear cuentas.

## 4. Accesibilidad web

La aplicación debe ser usada por cualquier persona. Por eso se seguirán los principios de WCAG 2.1:

- Se usará un contraste adecuado entre el texto y el fondo. Se utilizará Tailwind CSS para esto.

- La navegación con el teclado debe funcionar bien.

- Todas las imágenes y avatares tendrán etiquetas alt descriptivas.

- El HTML5 tendrá una estructura semántica correcta para facilitar la lectura con programas de voz.

## 5. Propiedad intelectual y recursos de terceros

- **Recursos visuales y de diseño:** Se usarán iconos gratuitos y componentes con licencias abiertas.

- **APIs externas:** Se revisarán los términos de servicio de servicios como Stripe y Resend.

## 6. Normativa específica del sector

Al permitir que los usuarios creen partidos y se interactúen, se establecerán normas de moderación. Los usuarios podrán reportar contenido inapropiado o conductas negativas. Los administradores serán responsables de revisar y gestionar estos casos.

## 7. Permisos y autorizaciones

No se necesitan permisos especiales porque no se trata de un servicio educativo ni de salud. Tampoco se requieren licencias de pago porque se usa una pasarela externa como Stripe.

## 8. Implementación técnica de cumplimiento legal

- **Páginas legales:** Se crearán las rutas /legal/privacidad, /legal/cookies y /legal/terminos.

- **Checkbox de aceptación:** Se incluirá en el formulario de registro. Es obligatorio.

- **Endpoints de gestión de datos:**

- Se permitirá la exportación de datos en formato JSON.

- Se creará un endpoint para borrar cuentas y eliminar todos los datos de los usuarios.