<div align="center">

<img src="images/logo.png" alt="Logo de Imora" height="140" />

# Imora Mail — Roundcube Skin

**Skin de Imora para Roundcube Webmail.**
Modo oscuro nativo, paleta de marca y logos propios, listo para producción.

[![License: CC BY-SA 3.0](https://img.shields.io/badge/License-CC%20BY--SA%203.0-1e3a5f?style=flat-square)](http://creativecommons.org/licenses/by-sa/3.0/)
[![Roundcube](https://img.shields.io/badge/Roundcube-1.6%2B-0f2440?style=flat-square)](https://roundcube.net/)
[![Based on Elastic](https://img.shields.io/badge/Based%20on-Elastic%20Skin-a8d93a?style=flat-square)](https://github.com/roundcube/roundcubemail/tree/master/skins/elastic)

</div>

---

## Características

- **Paleta de Imora**: azul marino `#1e3a5f` de la marca, acento lima `#a8d93a` del punto del logo y menú lateral en marino profundo.
- **Modo oscuro nativo** (`dark_mode_support: true`): fondos `#0f0f0f` / `#1c1c1f` y primario aclarado `#3b6ea5` para mantener el contraste.
- **Logos por modo**: logo completo claro/oscuro para el login y versión reducida para el menú lateral.
- **Sin gradientes**: diseño plano y limpio.
- **Scrollbars, foco y selección** con los colores de la marca en ambos modos.
- **Responsive**: escritorio, tableta y móvil (widescreen).
- **Construido sobre Elastic**, el skin oficial de Roundcube, a partir del tema de [NextAura](https://github.com/TheIsmael12/nextaura-roundcube).

---

## Identidad de marca

| Rol                              | Color     | Vista |
|----------------------------------|-----------|-------|
| Primario (azul marino)           | `#1e3a5f` | ![](https://placehold.co/14x14/1e3a5f/1e3a5f.png) |
| Primario hover                   | `#2a4d78` | ![](https://placehold.co/14x14/2a4d78/2a4d78.png) |
| Primario active                  | `#0f2440` | ![](https://placehold.co/14x14/0f2440/0f2440.png) |
| Acento lima (punto del logo)     | `#a8d93a` | ![](https://placehold.co/14x14/a8d93a/a8d93a.png) |
| Acento suave                     | `#dde6f0` | ![](https://placehold.co/14x14/dde6f0/dde6f0.png) |
| Primario en modo oscuro          | `#3b6ea5` | ![](https://placehold.co/14x14/3b6ea5/3b6ea5.png) |
| Fondo oscuro                     | `#0f0f0f` | ![](https://placehold.co/14x14/0f0f0f/0f0f0f.png) |
| Superficie oscura                | `#1c1c1f` | ![](https://placehold.co/14x14/1c1c1f/1c1c1f.png) |

Toda la marca está en las variables `@br-*` al principio de `styles/_styles.less` y en las `@color-*` de `styles/colors.less`.

---

## Estructura

```
imora-roundcube/
├── images/               # Logos y assets gráficos
│   ├── logo.png          # Logo principal (login, modo claro)
│   ├── logo-dark.png     # Logo para modo oscuro y menú lateral
│   ├── logo-small.png    # Logo reducido (modo claro)
│   ├── logo-small-dark.png
│   └── favicon.ico
├── styles/
│   ├── _styles.less      # ★ Overrides de marca (variables @br-*)
│   ├── _variables.less   # Variables del tema base
│   ├── colors.less       # Paleta de colores de Elastic
│   ├── styles.less       # Punto de entrada principal
│   └── styles.min.css    # CSS compilado y minificado
├── templates/            # Plantillas HTML de Roundcube
├── fonts/                # Roboto + FontAwesome 5
├── deps/                 # Bootstrap 4 bundle
└── meta.json             # Metadatos del skin
```

Logos: Generados a partir de los logos de `imora-intranet/public/images` (icono «IM.» y texto «IMORA» apilados) y del favicon de `imora-app-vecinos`.

---

## Instalación

### 1. Copiar el skin

```bash
git clone https://github.com/TheIsmael12/imora-roundcube.git /var/www/roundcube/skins/imora
```

### 2. Activar en Roundcube

```php
// config/config.inc.php
$config['skin'] = 'imora';
```

### 3. Limpiar caché de assets (opcional)

```bash
cd /var/www/roundcube
bin/updatecss.sh --dir skins/imora
```

---

## Compilar estilos

Los estilos están en **LESS**. Tras tocar `_styles.less`, `_variables.less` o `colors.less`:

```bash
npm install -g less clean-css-cli
lessc styles/styles.less | cleancss -O1 -o styles/styles.min.css
lessc styles/print.less  | cleancss -O1 -o styles/print.min.css
lessc styles/embed.less  | cleancss -O1 -o styles/embed.min.css
```

> `less-plugin-clean-css` falla con las versiones actuales de Node (`util.isRegExp is not a function`); por eso se minifica aparte con `clean-css-cli`.

---

## Créditos

Construido sobre el tema **Elastic** del equipo de Roundcube.

- Tema base: [Elastic Skin](https://github.com/roundcube/roundcubemail/tree/master/skins/elastic) — Aleksander Machniak
- Personalización de marca: [NextAura](https://nextaura.es) para Imora

| Librería         | Licencia   |
|------------------|------------|
| Bootstrap 4      | MIT        |
| FontAwesome 5    | CC BY 4.0  |
| Roboto (Google)  | Apache 2.0 |

---

## Licencia

**Creative Commons Attribution-ShareAlike 3.0**, heredada del skin Elastic.
Puedes copiar, distribuir, modificar y adaptar este trabajo siempre que mantengas los créditos al autor original (**Aleksander Machniak**) en este `README.md`.

[Ver licencia completa](http://creativecommons.org/licenses/by-sa/3.0/)
