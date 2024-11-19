## GetNextLine

**Get Next Line** es un proyecto desarrollado en 42 Madrid. Su objetivo principal es crear una función en C que permita leer líneas completas desde un descriptor de archivo (file descriptor) de manera eficiente.

### Descripción del Proyecto

El proyecto consiste en implementar la función `get_next_line`, que devuelve una línea leída de un file descriptor. Esta función es ideal para procesar entradas línea a línea sin necesidad de cargar todo el contenido de un archivo en memoria.

#### Características Principales

- **Lectura línea a línea:** La función devuelve una línea completa cada vez que se llama.
- **Uso eficiente de memoria:** Permite leer archivos grandes con un buffer configurable.
- **Soporte para múltiples descriptores:** La versión bonus admite la gestión simultánea de varios file descriptors.

### Archivos Incluidos

- `get_next_line.c`: Contiene la lógica principal de la función.
- `get_next_line_utils.c`: Funciones auxiliares utilizadas por get_next_line.
- `get_next_line.h`: Prototipos y definiciones necesarias.

En la versión bonus, los archivos correspondientes llevan el sufijo `_bonus`:
- `get_next_line_bonus.c`
- `get_next_line_utils_bonus.c`
- `get_next_line_bonus.h`

### Cómo Usarlo

1. **Compilación:**
   Utiliza el siguiente comando para compilar con un tamaño de buffer especificado (ejemplo con buffer de tamaño 42):
   ```bash
   gcc -Wall -Werror -Wextra -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c
   ```

2. **Uso:**
   Llama a la función `get_next_line` en un bucle para leer cada línea de un descriptor de archivo hasta que devuelva `NULL`:
   ```c
   char *line;
   while ((line = get_next_line(fd)) != NULL) {
       printf("%s", line);
       free(line);
   }
   ```

### Bonus

La parte bonus incluye:
- **Gestión de múltiples file descriptors:** Permite llamar a `get_next_line` alternando entre varios descriptores sin perder el estado de lectura de cada uno.

### Aclaración

Este proyecto sigue los estándares de la Norma de 42.
