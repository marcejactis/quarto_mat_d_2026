# Apunte de Cálculo Numérico – FIQ (UNL)

Este repositorio contiene el apunte de la materia **Cálculo Numérico** de la
Facultad de Ingeniería Química (UNL), desarrollado en **Quarto**.

El apunte combina:
- desarrollo teórico,
- ejemplos,
- y experimentación computacional en **Python**.

---

## 🧰 Requisitos previos

### Python (≥ 3.10 recomendado)

Verificar si está instalado:

```bash
python3 --version
```

Instalar si no está disponible:

```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip python3-full
```

---

### Git

Verificar instalación:

```bash
git --version
```

Instalar si no está disponible:

```bash
sudo apt install git
```

---

### Quarto

Verificar instalación:

```bash
quarto --version
```

Instalar en Ubuntu:

```bash
wget https://quarto.org/download/latest/quarto-linux-amd64.deb
sudo dpkg -i quarto-linux-amd64.deb
```

---

## 📥 Clonar el repositorio

Se recomienda usar **HTTPS** (no requiere claves SSH):

```bash
git clone https://github.com/USUARIO/REPOSITORIO.git
cd REPOSITORIO
```

---

## 🐍 Crear y activar entorno virtual

Crear el entorno (una sola vez):

```bash
python3 -m venv .venv
```

Activar el entorno:

```bash
source .venv/bin/activate
```

---

## 📦 Instalar dependencias del proyecto

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Verificar instalación de `jupyter-cache`:

```bash
python -c "import jupyter_cache; print('jupyter-cache OK')"
```

---

## 📘 Renderizar el apunte

Desde la raíz del proyecto:

```bash
quarto render
```

El resultado se genera en:

```text
_book/index.html
```

---

## 🔁 Flujo típico de trabajo

```bash
source .venv/bin/activate
quarto preview
# editar archivos .qmd
git status
git add .
git commit -m "Mensaje descriptivo"
git push
```

---

## ⚠️ Notas importantes

- ❌ No usar `sudo` con comandos de Quarto
- ❌ No versionar el entorno virtual (`.venv/`)
- ✔️ Activar siempre el entorno virtual antes de trabajar
- ✔️ Editar únicamente archivos `.qmd`

---

## 📂 Estructura general del proyecto

```text
.
├── _quarto.yml
├── index.qmd
├── chapters/
├── figures/
├── data/
├── code/
├── references.bib
├── requirements.txt
└── README.md
```

---

## ☁️ Uso en carpetas sincronizadas (Nextcloud, Drive, etc.)

Es posible trabajar dentro de una carpeta sincronizada, pero se recomienda:

- No editar el mismo archivo en dos equipos a la vez
- Esperar a que la nube termine de sincronizar antes de `git pull` o `git push`
- Resolver conflictos siempre con Git primero

**Git es la fuente de verdad.**
