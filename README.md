# ingesta_pkm

# Ingesta de Datos Pokémon (ingesta_pkm)

Proyecto de **ingesta incremental de datos** desde la [PokeAPI](https://pokeapi.co/) utilizando Python.

Este repositorio demuestra una ingesta básica de datos de Pokémon, guardando la información en formato CSV y manteniendo un control de los lotes procesados para evitar duplicados.

---

## 🚀 Objetivo del Proyecto

Automatizar la extracción de datos de Pokémon (ID, nombre, tipos, estadísticas básicas, etc.) y almacenarlos de forma organizada en la capa **Raw** de una arquitectura de datos.

---

## Estructura del Proyecto

```bash
proyecto_ingesta/
├── data/
│   ├── raw/                  # Archivos CSV crudos
│   │   └── pokemon_ids_1_20.csv
│   └── control/              # Control de ingesta (evita duplicados)
│       └── control.json
├── ingesta_pkm_py.py         # Script principal de ingesta
└── README.md

Características

Ingesta incremental mediante control de lotes procesados
Extracción de datos desde PokeAPI
Parseo de estadísticas y tipos de Pokémon
Guardado en archivos CSV por rangos de IDs
Registro de control en JSON
Creación automática de carpetas necesarias


Tecnologías Utilizadas

Python 3
requests → para consumir la API
pandas → para manejar y guardar los datos
json → para el archivo de control
os → manejo de directorios


Cómo Usar
1. Clonar el repositorio
Bashgit clone https://github.com/SebastianAVi/ingesta_pkm.git
cd ingesta_pkm
2. Instalar dependencias
Bashpip install requests pandas
3. Ejecutar el script
Bashpython ingesta_pkm_py.py
El script descargará por defecto los primeros 20 Pokémon (IDs 1 al 20). Puedes modificar la función ingestar_rango(inicio, fin) para descargar más.

Ejemplo de Salida
Se generarán archivos como:

data/raw/pokemon_ids_1_20.csv
data/control/control.json


Próximas Mejoras (Ideas)

Convertir en script parametrizable con argumentos (argparse)
Agregar logging profesional
Soporte para ingesta completa (hasta 1025+ Pokémon)
Scheduling con Airflow, Prefect o cron
Limpieza y validación de datos (capa Silver)
Dockerización
