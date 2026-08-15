# Segmentación de núcleos celulares (MoNuSeg 2018): CNN vs U-Net

Proyecto del seminario de **Deep Learning para Bioimágenes (dlba-pucp)**.

Compara dos arquitecturas de segmentación semántica —una **CNN encoder-decoder simple** y una **U-Net con skip connections**— sobre el dataset público **MoNuSeg 2018** (imágenes de histopatología con máscaras de núcleos celulares), y mide el efecto de aplicar **Data Augmentation** (rotaciones aleatorias) sobre el desempeño de ambos modelos.

## Contenido

- `CNN_SEMINARIO.ipynb` — Notebook principal con todo el flujo.

## Flujo del notebook

1. Configuración y descarga del dataset desde Kaggle.
2. Emparejamiento de imágenes y máscaras.
3. Dataset y DataLoader en PyTorch.
4. Función de pérdida (Dice + BCE) y métrica IoU.
5. Entrenamiento y evaluación: CNN simple vs U-Net (sin augmentation).
6. Data Augmentation (rotaciones aleatorias sincronizadas imagen-máscara).
7. Re-entrenamiento con augmentation y comparación final.

## Requisitos

- **Google Colab** 
- Cuenta de **Kaggle** para descargar el dataset `tuanledinh/monuseg2018`.

### Credenciales de Kaggle

El notebook necesita tus credenciales de la API de Kaggle:

**Archivo `kaggle.json`** se descarga en `Account → Settings → API → Create New Token` y se sube cuando la celda lo solicite.

## Ejecución

1. Abre `CNN_SEMINARIO_completo.ipynb` en Google Colab.
2. Ejecuta las celdas en orden.
3. Cuando la celda de descarga lo solicite, proporciona tus credenciales de Kaggle.
4. Espera el entrenamiento (15 épocas por modelo) y revisa los resultados finales.

## Resultados

El notebook genera un gráfico de barras comparando el **IoU en test** de las 4 configuraciones:

- CNN sin augmentation
- U-Net sin augmentation
- CNN con augmentation
- U-Net con augmentation

## Licencia

Uso académico/educativo. El dataset MoNuSeg 2018 pertenece a sus respectivos autores.
