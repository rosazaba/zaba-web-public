# Web pública de Zaba

Escaparate de la web de Zaba (fotografía de surf y buceo). GitHub Pages publica `docs/` de `main` en **rosazaba.com**.

## Reglas
- **Solo fotos en baja resolución o con marca de agua.** El repositorio es público y las fotos se venden: nunca originales ni alta resolución. Las de "Encuentra tus fotos", siempre con `con_marca()`. Si una imagen no cumple, no se sube.
- **No se edita nada a mano.** `docs/` es la salida de `python motor/build.py` en **rosazaba/zaba-web** (solo con 0 errores), copiada tal cual sustituyendo lo anterior. Código, plantillas, textos y originales viven allí.
- **Nada sensible en commits** (ni en archivos ni en mensajes): claves, tokens, contraseñas, rutas locales (`/home/...`, `C:\...`), emails personales ni datos de clientes. Revisar el diff antes de cada commit; si algo se cuela, avisar antes de hacer push.
- En la raíz solo van `CLAUDE.md` y `README.md`.
- **`docs/CNAME` tiene que existir**; sin él se pierde el dominio. Lo genera el build (`publicar_dominio: true` en `textos/general.yml` de `zaba-web`).
- Claude hace commit y push; la usuaria no usa git.
