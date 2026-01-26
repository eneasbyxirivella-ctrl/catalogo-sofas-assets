# Estructura de Imágenes del Catálogo

## Organización de Carpetas

```
catalog/
├── afos-x-sofa/
│   ├── logo.png              # Logo de la marca
│   ├── antares/
│   │   ├── cover.jpg         # Imagen de portada del modelo
│   │   ├── ambiente/         # Fotos del sofá en ambientes reales
│   │   └── estudio/          # Fotos del sofá en estudio
│   ├── berlin-plus/
│   │   ├── cover.jpg
│   │   ├── ambiente/
│   │   └── estudio/
│   └── ... (resto de modelos)
│
└── eneas-by-xirivella/
    ├── logo.png
    ├── aero/
    │   ├── cover.jpg
    │   ├── ambiente/
    │   └── estudio/
    └── ... (resto de modelos)
```

## Cómo Añadir Imágenes

### 1. Logos de Marca
- Coloca el logo en: `catalog/{marca}/logo.png`
- Formato recomendado: PNG con fondo transparente
- Tamaño recomendado: 400x400px o superior

### 2. Portadas de Modelo
- Coloca la imagen en: `catalog/{marca}/{modelo}/cover.jpg`
- Esta imagen se muestra en las tarjetas de la lista de modelos
- Formato: JPG o PNG
- Tamaño recomendado: 800x600px

### 3. Galerías
#### Ambiente (sofás en contexto real)
- Coloca las imágenes en: `catalog/{marca}/{modelo}/ambiente/`
- Nombre: cualquier nombre descriptivo (ej: salon-01.jpg, living-room.jpg)
- Formatos aceptados: .jpg, .jpeg, .png, .webp

#### Estudio (sofás en fondo neutro)
- Coloca las imágenes en: `catalog/{marca}/{modelo}/estudio/`
- Nombre: cualquier nombre descriptivo
- Formatos aceptados: .jpg, .jpeg, .png, .webp

## Notas Importantes
- NO es necesario modificar el código después de añadir imágenes
- La app detecta automáticamente todas las imágenes en las carpetas
- Si una carpeta está vacía, la app muestra "Sin imágenes disponibles"
- Si una imagen falla al cargar, se muestra un placeholder gris
- Las imágenes se cargan con lazy loading para mejor rendimiento

## Ejemplo de Cómo Añadir un Nuevo Modelo

1. Abre catalog.json y añade el modelo:
```json
{
  "id": "nuevo-modelo",
  "name": "Nuevo Modelo",
  "cover": "catalog/afos-x-sofa/nuevo-modelo/cover.jpg",
  "galleries": {
    "ambiente": [],
    "estudio": []
  }
}
```

2. Crea las carpetas:
```
mkdir -p catalog/afos-x-sofa/nuevo-modelo/{ambiente,estudio}
```

3. Añade las imágenes en las carpetas correspondientes

4. ¡Listo! La app reflejará automáticamente el nuevo modelo
