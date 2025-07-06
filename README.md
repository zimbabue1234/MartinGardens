# MartinGardens

Sitio web profesional para servicios de jardinería en Jávea y alrededores.

## Configuración del envío de correos

Para que el formulario de contacto envíe correos automáticamente a martingardens@hotmail.com, necesitas configurar el servicio de email:

### Paso 1: Configurar Supabase
1. Ve a [Supabase](https://supabase.com) y crea una cuenta gratuita
2. Crea un nuevo proyecto
3. En el proyecto, ve a "Edge Functions" en el menú lateral

### Paso 2: Configurar Resend (Servicio de Email)
1. Ve a [Resend](https://resend.com) y crea una cuenta gratuita
2. Verifica tu dominio o usa el dominio de prueba
3. Obtén tu API key desde el dashboard
4. En Supabase, ve a "Settings" > "Environment Variables"
5. Añade una nueva variable:
   - Nombre: `RESEND_API_KEY`
   - Valor: tu API key de Resend

### Paso 3: Desplegar la función
La función de envío de correos se encuentra en `supabase/functions/send-email/index.ts` y se desplegará automáticamente cuando conectes tu proyecto a Supabase.

### Características del formulario:
- ✅ Validación de campos obligatorios
- ✅ Validación de formato de email
- ✅ Envío automático a martingardens@hotmail.com
- ✅ Respuesta automática con los datos del cliente
- ✅ Notificaciones de éxito/error
- ✅ Estados de carga durante el envío

### Alternativa simple (sin backend):
Si prefieres una solución más simple sin configurar servicios, puedes usar `mailto:` que abrirá el cliente de correo del usuario:

```javascript
// En lugar de la función fetch, usar:
window.location.href = `mailto:martingardens@hotmail.com?subject=Contacto desde web - ${data.service}&body=Nombre: ${data.name}%0AEmail: ${data.email}%0ATeléfono: ${data.phone}%0AServicio: ${data.service}%0AMensaje: ${data.message}`;
```

[Edit in StackBlitz next generation editor ⚡️](https://stackblitz.com/~/github.com/zimbabue1234/MartinGardens)