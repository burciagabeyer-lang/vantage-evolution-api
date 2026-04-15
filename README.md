# VANTAGE Evolution API

Evolution API deployment para VANTAGE Services WhatsApp bot.

## Deploy en Railway

1. **Crear nuevo proyecto en Railway**
   - New Project → Deploy from GitHub repo
   - Selecciona `burciagabeyer-lang/vantage-evolution-api`

2. **Agregar PostgreSQL**
   - Add → Database → PostgreSQL
   - Railway automáticamente proveerá `DATABASE_URL`

3. **Configurar variables de entorno en el servicio Evolution API**
   - Ve a tu servicio → Variables
   - Agrega:
     ```
     EVOLUTION_API_KEY=<genera con: openssl rand -hex 32>
     ```

4. **Generar dominio público**
   - Settings → Networking → Generate Domain
   - Copia la URL (ej: `https://tu-proyecto.railway.app`)
   - Esta URL se usará como `EVOLUTION_API_URL` en Vercel

5. **Verificar deployment**
   - Espera a que el build termine (2-3 minutos)
   - Verifica: `curl https://tu-dominio.railway.app/health -H "apikey: tu_api_key"`
   - Debe responder: `{"status":"ok"}`

## Variables que Railway provee automáticamente

- `DATABASE_URL` - PostgreSQL connection string
- `RAILWAY_PUBLIC_DOMAIN` - Dominio público del servicio

## Endpoints

- Health: `https://tu-dominio.railway.app/health`
- Manager: `https://tu-dominio.railway.app/manager`
- API Docs: `https://tu-dominio.railway.app/docs`

## Conectar a Vercel

Agregar estas variables en Vercel:

```env
EVOLUTION_API_URL=https://tu-dominio.railway.app
EVOLUTION_API_KEY=<tu_api_key>
EVOLUTION_INSTANCE=vantage-principal
```
