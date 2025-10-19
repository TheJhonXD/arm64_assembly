# Compilar ARM64 Assembly en Windows con Docker

Este proyecto permite compilar y ejecutar código ensamblador ARM64 en Windows usando Docker con emulación QEMU.

## Requisitos

- Docker Desktop para Windows
- Make para Windows

## Uso

**Primera vez, construir imagen docker:**

```bash
make build
```

**Después, cada vez que se edite el archivo `codigo.s` ejecutar:**

```bash
make run
```

O simplemente:

```bash
make
```

## Comandos disponibles

- `make` o `make run` - Compila y ejecuta el programa
- `make build` - Construye la imagen Docker (solo se hace la primera vez o después de `make clean`)
- `make compile-only` - Solo compila sin ejecutar
- `make clean` - Limpia archivos e imágenes generadas
- `make help` - Muestra la ayuda

## Edición de código

Simplemente se edita el archivo `codigo.s` con el código ensamblador ARM64 y ejecutar `make`.

## Cómo Funciona

1. Docker crea un contenedor con Ubuntu ARM64 (emulado con QEMU)
2. Se instalan las herramientas de compilación (assembler `as` y libc)
3. Se compila `codigo.s` a un objeto `codigo.o`
4. Se enlaza para crear el ejecutable `codigo`
5. Se ejecuta y muestra la salida

## Recursos

- [Referencia ARM64 Instruction Set](https://developer.arm.com/documentation/)
- [Linux System Calls ARM64](https://arm64.syscall.sh/)
