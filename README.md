# gum gum pistol

Minimal example to create a pypi package using poetry

![image](https://user-images.githubusercontent.com/26511618/216767867-50a63a7f-bb39-4020-9227-e6672c454c9a.png)
(Screen cap from <https://onepiece.fandom.com/wiki/Gomu_Gomu_no_Mi/Techniques>)

Pypi: <https://pypi.org/project/ray-chunkit-chung-gum-gum-pistol/>

Github: <https://github.com/ray-chunkit-chung/essential-poetry>

## How to use

Install gum-gum-pistol

```bash
pip install ray-chunkit-chung-gum-gum-pistol
```

This gum-gum-pistol has two functions

```bash
gum load
gum shoot
```

That's it!

## Use typer to create gum-gum-pistol

<https://typer.tiangolo.com/tutorial/package/>

### Step 1 Install python

```bash
python -m venv .venv
# .venv\Scripts\activate
source .venv/bin/activate
python -m pip install --upgrade pip
pip install --upgrade -r requirements.txt
```

### Step 2 Init project and dependencies

```bash
poetry new ray-chunkit-chung-gum-gum-pistol
cd ray-chunkit-chung-gum-gum-pistol
poetry add typer[all]
poetry add pytest[all]
```

### Step 3 Define app

Define app path

```toml
[tool.poetry.scripts]
gum = "ray_chunkit_chung_gum_gum_pistol.main:app"
```

Install local for test

```bash
poetry install
```

Test app local

```bash
gum --help
gum load
gum shoot
```

### Step 4 Distribute app

Build wheel file

```bash
poetry build
```

Test by changing to a new venv and install from local dist

```bash
pip install ray-chunkit-chung-gum-gum-pistol\dist\ray_chunkit_chung_gum_gum_pistol-0.1.0-py3-none-any.whl
```

### Step 5 Upload to pypi

Create PYPI_TOKEN and export to env. Then config pypi-token in poetry. Then publish to pypi

```bash
poetry config pypi-token.pypi $PYPI_TOKEN
poetry publish --build
```

Test by changing to a new venv and install from pypi

```bash
pip install ray-chunkit-chung-gum-gum-pistol
gum --help
```
