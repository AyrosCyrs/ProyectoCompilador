# Proyecto de Compiladores

Compilador construido desde cero en Java, como proyecto de la materia de Compiladores (Facultad de Ciencias, UNAM). El proyecto abarca las dos grandes etapas de un compilador: análisis léxico y análisis sintáctico.

## ¿Qué hace?

### Análisis léxico (Lexer)
- Convierte expresiones regulares en autómatas finitos no deterministas (NFA)
- Convierte los NFA en autómatas finitos deterministas (DFA)
- Minimiza los DFA para hacerlos más eficientes
- Reconoce y separa el código fuente en tokens (palabras, números, símbolos, etc.)

### Análisis sintáctico (Parser)
- Define gramáticas formales para el lenguaje
- Implementa un parser **LL(1)** (analiza de izquierda a derecha)
- Implementa un parser **LALR(1)** (más potente, usado en compiladores reales)
- Incluye un analizador estático para validar la estructura del código

## Tecnologías utilizadas

- **Java** — lenguaje principal del proyecto
- **Maven** — gestor de dependencias y construcción del proyecto
- **Docker** — para poder ejecutar el proyecto en cualquier máquina sin instalar nada extra
- **JUnit** — pruebas automatizadas para verificar que cada parte funcione correctamente

## Cómo ejecutarlo

### Opción 1: Con Maven
```bash
mvn clean install
mvn exec:java -Dexec.mainClass="com.compiler.Main"
```

### Opción 2: Con Docker
```bash
docker build -t proyecto-compilador .
docker run proyecto-compilador
```

## Pruebas

El proyecto incluye pruebas automatizadas para verificar el correcto funcionamiento del lexer y del parser:
```bash
mvn test
```

## Contexto

Este proyecto se desarrolló de forma incremental a lo largo del semestre, agregando cada semana una nueva parte del compilador (expresiones regulares, autómatas, parsers), hasta lograr un compilador funcional completo desde cero.
