# TDL-Pokemones

## Set de Datos

https://www.kaggle.com/competitions/histopathologic-cancer-detection/overview

## Cómo instalar Julia en Jupiter Notebook

https://datatofish.com/add-julia-to-jupyter/

### Problemas conocidos en el proceso.

Si se estuvieron creando Environments o trabajando con ellos. Al momento de realizar el tutorial de arriba y ejecutar `Pkg.add("IJulia")` este comando instalará IJulia localmente el environment, haciéndolo "invisible" para el anaconda navigator y por ende, al jupyter notebook. Verificar que esta instalación sea global, accediendo a Julia desde fuera de un environmente o configurar Jupyter notebook y/o Conda para que levante el kernel desde el environmente que tiene IJulia instalado.

Una pista de dónde se realizó la instalación es que al hacer `Pkg.add("IJulia")` se actualizarán el Manifiest.toml del ambiente.
Por ejemplo:

```
julia> Pkg.add("IJulia")
   Resolving package versions...
   Installed Conda ─────────── v1.7.0
   Installed VersionParsing ── v1.3.0
   Installed ZMQ ───────────── v1.2.1
   Installed Preferences ───── v1.3.0
   Installed JSON ──────────── v0.21.3
   Installed Parsers ───────── v2.4.2
   Installed JLLWrappers ───── v1.4.1
   Installed SoftGlobalScope ─ v1.1.0
   Installed ZeroMQ_jll ────── v4.3.4+0
   Installed libsodium_jll ─── v1.0.20+0
  Downloaded artifact: ZeroMQ
  Downloaded artifact: libsodium
    Updating `~/Documents/workspace/julia/TDL-Pokemones/environment/Project.toml`
  [7073ff75] + IJulia v1.23.3
    Updating `~/Documents/workspace/julia/TDL-Pokemones/environment/Manifest.toml`
```

Instaló en el ambiente en la ubicación `~/Documents/workspace/julia/TDL-Pokemones/environment`

En cambio:
```
julia> import Pkg; Pkg.add("IJulia")
    Updating registry at `~/.julia/registries/General.toml`
   Resolving package versions...
    Updating `~/.julia/environments/v1.8/Project.toml`
  [7073ff75] + IJulia v1.23.3
    Updating `~/.julia/environments/v1.8/Manifest.toml`
```
Lo instaló en `~/.julia/environments/v1.8/`. Una ubicación global.

#### Failed to load module "canberra-gtk-module"

Hay que instalar la librería.

`sudo apt-get install libcanberra-gtk-module libcanberra-gtk0`


# Proyecto Baseline en Python

## Requerimientos previos
- Python 3.8 (importante para Keras).
- Placa de Video Nvidia (sino la instalación de Keras tendrá que ser personalizada)

## Creación de ambiente virtual para el proyecto
Con virtualenv. (Se pueden usar otras como el asistente de Pycharm o cualquier otro)
```
virtualenv venv -p /usr/bin/python3.8
```

## Preparación del ambiente
```
pip install -r requirements.txt
```

## Ubicación de los archivos.
Para que el notebook funcione las imágentes deben estar dentro de una carpeta llamada
histopathologic-cancer-detection dentro de input un nivel arriba del proyecto. 
Estructura
```
├── input
│   ├── histopathologic-cancer-detection
│   │   ├── test
│   │   ├── train
│   │   ├── sample_submission.csv
│   │   ├── train_labels.csv
├── TDL-Pokemones
│   ├── README.md
│   ├── *.ipnyb

```
