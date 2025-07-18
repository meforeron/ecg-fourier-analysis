# Análisis y Filtrado de Señales ECG mediante Transformada de Fourier

## Descripción
Este proyecto implementa técnicas de procesamiento de señales electrocardiográficas (ECG) utilizando la Transformada de Fourier para la identificación de ritmos anómalos.

## Autores
- Maria Paula Carvajal Martinez
- Melissa Forero Narvaez  
- Daniel Alberto Garzón Fraile

## Características
- Lectura de señales ECG de la base de datos PTB-XL
- Análisis de Fourier para caracterización espectral
- Eliminación de línea de base (0.1-1.5 Hz)
- Filtrado de altas frecuencias (>40 Hz)
- Detección automática de ritmos anómalos

## Estructura del Proyecto
```
ecg-project/
├── Proyecto-ECG.ipynb          # Notebook principal
├── data/                       # Datos de ECG (PTB-XL)
├── requirements.txt            # Dependencias
├── README.md                   # Este archivo
└── .gitignore                  # Archivos a ignorar
```

## Instalación y Uso

### Requisitos
```bash
pip install -r requirements.txt
```

O instalar manualmente:
```bash
pip install numpy pandas matplotlib wfdb scipy jupyter
```
### Obtener los Datos PTB-XL

Los datos ECG no están incluidos en el repositorio por su tamaño. Descárgalos siguiendo estos pasos:

#### Opción A: Descarga Automática
```bash
# Crear directorio de datos
mkdir -p data/ptb-xl

# Descargar dataset PTB-XL (esto puede tomar tiempo)
wget -P data/ptb-xl https://physionet.org/static/published-projects/ptb-xl/ptb-xl-a-large-12-lead-electrocardiogram-database-1.0.3.zip

# Descomprimir
cd data/ptb-xl
unzip ptb-xl-a-large-12-lead-electrocardiogram-database-1.0.3.zip
```

#### Opción B: Descarga Manual
1. Ve a [PhysioNet PTB-XL](https://physionet.org/content/ptb-xl/1.0.3/)
2. Descarga el archivo ZIP
3. Extrae en `data/ptb-xl/`
4. Asegúrate de tener esta estructura:
```
data/
└── ptb-xl/
    ├── records100/
    │   └── 00000/
    │       ├── 00004_lr.dat
    │       └── 00004_lr.hea
    └── records500/
        └── 00000/
            ├── 00004_hr.dat
            └── 00004_hr.hea
```

### Ejecución
1. Clonar el repositorio
2. Instalar dependencias
3. Ejecutar `Proyecto-ECG.ipynb` en Jupyter

## Metodología
1. **Lectura de Señales**: Utilización de wfdb para cargar registros ECG
2. **Análisis de Fourier**: Transformación al dominio frecuencial
3. **Filtrado**: Eliminación de ruido y artefactos
4. **Detección**: Identificación de patrones anómalos

## Resultados
- Filtrado efectivo de señales ECG
- Detección automática de taquicardia, bradicardia y arritmias
- Visualización clara de intervalos RR

## Licencia
MIT License
