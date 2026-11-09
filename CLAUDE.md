# Web de Zaba (pública): normas del repositorio

Este repositorio es el **escaparate**: solo contiene la web ya generada de Zaba (fotografía de surf y buceo) y es el que publica GitHub Pages con el dominio.

## Qué hay aquí y qué no
- **Sí:** el resultado de `python motor/build.py` del repositorio **rosazaba/zaba-web** (el contenido de su carpeta `docs/`), copiado tal cual a `docs/` de este repositorio.
- En la raíz solo van `CLAUDE.md` y `README.md`, que no se publican en la web.
- **No:** código, plantillas, textos fuente, scripts, `originales/` ni `vista-previa/`. Todo eso vive en `zaba-web`.
- **Regla de oro:** este repositorio es público y las fotos se venden. Aquí solo entran imágenes en baja resolución o con marca de agua (las de Encuentra tus fotos siempre con `con_marca()`: 960 px, logo en diagonal y código). Nunca originales ni fotos en alta resolución. Si una imagen no cumple esto, no se sube.

## Cómo se actualiza
- No se edita nada a mano. Cualquier cambio (fotos, textos, idiomas, diseño) se hace en `zaba-web`, se genera con `build.py` (solo con 0 errores) y la salida se copia aquí, sustituyendo lo anterior.
- Claude hace el commit y el push con la app de Claude para GitHub. La usuaria no usa cliente de git.

## GitHub Pages y dominio
- Pages publica desde la rama `main`, carpeta `/docs`. Solo lo que hay en `docs/` sale en la web. Lo activa la usuaria (Settings → Pages); la app de Claude no tiene permiso de administración.
- Dominio: **rosazaba.com**. En `zaba-web`, `textos/general.yml` lleva `dominio: "https://rosazaba.com"` y `publicar_dominio: true`, para que el build genere siempre `CNAME` y llegue a `docs/CNAME`. Si se pierde ese archivo, el dominio se desengancha.
- Modo prueba (`modo_prueba: true` en `zaba-web`): la web lleva `noindex` y `robots.txt` con `Disallow: /`, para enseñarla sin que Google la indexe. Se pone en `false` el día del lanzamiento.
- Dominio .com:
  1. En `zaba-web`, poner `dominio` y `publicar_dominio: true` en `textos/general.yml`. El build crea `CNAME`, que llega a `docs/` con el resto de la web.
  2. En el DNS del dominio, registros A del dominio raíz a `185.199.108.153`, `185.199.109.153`, `185.199.110.153` y `185.199.111.153`, y CNAME de `www` a `rosazaba.github.io`.
  3. Verificar el dominio en la cuenta (GitHub → Settings → Pages → Verified domains, con un registro TXT) para evitar que otros lo usen.
  4. Activar "Enforce HTTPS" en la configuración de Pages de este repositorio.
- `dominio` también se usa para canonical, hreflang, sitemap y og:image. Tiene que coincidir con la dirección real de publicación.
