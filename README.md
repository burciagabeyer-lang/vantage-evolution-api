# VANTAGE Evolution API

Evolution API deployment para VANTAGE Services WhatsApp bot.

## Deploy en Railway

1. **Crear nuevo proyecto en Railway**
   - Conecta este repositorio desde GitHub

2. **Agregar PostgreSQL**
   - Add service → Database → PostgreSQL
   - Railway automáticamente proveerá `DATABASE_URL`

3. **Configurar variables de entorno**
   ```
   EVOLUTION_API_KEY=<genera un API key seguro con: openssl rand -hex 32>
   ```

4. **Generar dominio público**
   - Settings → Generate Domain
   - Copia la URL para configurar en Vercel

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
