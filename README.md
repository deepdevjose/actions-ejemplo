# 🎓 Ejercicio OOP: Implementar Person con __str__

Este proyecto es un ejercicio interactivo de Programación Orientada a Objetos que utiliza GitHub Actions y Cloudflare Pages para validar automáticamente tu código y mostrar los resultados en tiempo real.

## 📋 Objetivo del Ejercicio

Implementar una clase `Person` que maneje correctamente el método especial `__str__` para mostrar nombres en formato capitalizado.

## 🏗️ Estructura del Proyecto

```
proyecto/
├── .github/
│   └── workflows/
│       └── deploy.yml          # Workflow de GitHub Actions
├── src/
│   └── person.py               # ⭐ TU IMPLEMENTACIÓN AQUÍ
├── tests/
│   └── test_person.py          # Tests automáticos
├── index.html                  # Página de resultados (no modificar)
└── README.md                   # Este archivo
```

## ✅ Requisitos

Crea la clase `Person` en `src/person.py` con:

1. **Atributos:**
   - `first_name` (nombre)
   - `last_name` (apellido)

2. **Método `__str__`:**
   - Debe retornar el nombre completo en formato capitalizado
   - Formato esperado: `"Juan Perez"`
   - Debe manejar nombres en minúsculas, MAYÚSCULAS y MiXtAs

## 📝 Ejemplo de Uso Esperado

```python
# Crear personas
p1 = Person("juan", "perez")
p2 = Person("MARIA", "LOPEZ")
p3 = Person("carlos", "gonzalez")

# Al imprimir, __str__ se ejecuta automáticamente
print(p1)   # Juan Perez
print(p2)   # Maria Lopez
print(p3)   # Carlos Gonzalez
```

## 🚀 Cómo Trabajar en el Ejercicio

### 1. Clonar el repositorio
```bash
git clone <tu-repositorio>
cd <tu-repositorio>
```

### 2. Crear tu implementación

Edita el archivo `src/person.py` e implementa la clase Person:

```python
class Person:
    def __init__(self, first_name, last_name):
        # Tu código aquí
        pass
    
    def __str__(self):
        # Tu código aquí
        pass
```

### 3. Probar localmente (opcional)

```bash
# Instalar pytest si no lo tienes
pip install pytest

# Ejecutar tests
python -m pytest tests/test_person.py -v
```

### 4. Subir tu solución

```bash
git add src/person.py
git commit -m "Implementar clase Person con __str__"
git push origin master
```

### 5. Ver resultados

1. GitHub Actions ejecutará los tests automáticamente
2. Si los tests pasan ✅:
   - Tu nombre aparecerá en la página web desplegada
   - Verás el timestamp y número de intento
   - La página mostrará "TESTS PASADOS"

3. Si los tests fallan ❌:
   - La página mostrará el estado de error
   - Podrás descargar un reporte detallado desde "Artifacts" en GitHub Actions
   - El reporte incluye exactamente qué tests fallaron y por qué

## 🧪 Tests Incluidos

El sistema ejecuta 8 tests automáticos:

1. ✓ Verifica que la clase Person existe
2. ✓ Verifica que implementaste `__str__`
3. ✓ Prueba con nombres en minúsculas
4. ✓ Prueba con nombres en MAYÚSCULAS
5. ✓ Prueba con nombres MiXtOs
6. ✓ Prueba con nombres compuestos (ej: "juan carlos")
7. ✓ Verifica que existen los atributos correctos
8. ✓ Verifica que los atributos se asignan bien

## 💡 Tips y Ayuda

### Tip 1: Método .title()
Python tiene un método built-in perfecto para este ejercicio:
```python
texto = "juan perez"
print(texto.title())  # "Juan Perez"
```

### Tip 2: Formato del __str__
El método debe retornar UN STRING, no imprimir:
```python
def __str__(self):
    return "algo"  # ✅ Correcto
    
def __str__(self):
    print("algo")  # ❌ Incorrecto
```

### Tip 3: Combinar strings
```python
nombre_completo = f"{self.first_name} {self.last_name}"
# o también:
nombre_completo = self.first_name + " " + self.last_name
```


## 🎯 Criterios de Evaluación

- ✅ La clase debe llamarse exactamente `Person`
- ✅ Debe estar en el archivo `src/person.py`
- ✅ Debe tener un método `__init__` que acepte `first_name` y `last_name`
- ✅ Debe tener atributos `self.first_name` y `self.last_name`
- ✅ Debe implementar el método `__str__`
- ✅ El `__str__` debe retornar un string (no imprimir)
- ✅ El formato debe ser capitalizado: primera letra de cada palabra en mayúscula
- ✅ Debe funcionar con nombres en cualquier formato (minúsculas, MAYÚSCULAS, MiXtAs)

## 📊 Visualización de Resultados

Cada vez que hagas push, la página web mostrará:

- 👤 **Tu nombre** (del commit de Git)
- 📧 **Tu email**
- 🕐 **Timestamp** de cuándo pasaste los tests
- 💬 **Mensaje del commit**
- 📈 **Número de intento** (total de commits)
- ✅ **Tests pasados** vs total
- 🎯 **Estado**: Success o Failed

## 🔍 Debugging: Si los Tests Fallan

### Paso 1: Ve a GitHub Actions
1. Entra a tu repositorio en GitHub
2. Click en la pestaña "Actions"
3. Click en el workflow más reciente

### Paso 2: Descarga el Reporte de Errores
1. Scroll hasta abajo en el workflow
2. Busca la sección "Artifacts"
3. Descarga `error-report-XXX.txt`
4. El archivo contiene:
   - Qué tests fallaron exactamente
   - El mensaje de error completo
   - Sugerencias para solucionar

### Paso 3: Errores Comunes

**Error: "No se pudo importar Person"**
- Verifica que el archivo esté en `src/person.py`
- Verifica que la clase se llame exactamente `Person` (con P mayúscula)

**Error: "debe tener un método __str__"**
- Asegúrate de escribir `__str__` con doble guion bajo antes y después

**Error: "Esperado 'Juan Perez', pero obtuve..."**
- Verifica que uses `.title()` en el string completo
- Asegúrate de incluir un espacio entre nombre y apellido

## 🎉 ¿Qué pasa cuando pasas todos los tests?

1. 🎊 La página web mostrará tu nombre en grande
2. ✅ Badge verde de "TODOS LOS TESTS PASARON"
3. 📈 Se registrará tu intento exitoso
4. 🌐 La página estará disponible públicamente en Cloudflare

## 📚 Recursos Adicionales

- [Documentación oficial de Python: __str__](https://docs.python.org/3/reference/datamodel.html#object.__str__)
- [Python String Methods](https://docs.python.org/3/library/stdtypes.html#string-methods)
- [OOP en Python](https://docs.python.org/3/tutorial/classes.html)

## 🤝 Soporte

Si tienes dudas:
1. Revisa el reporte de errores en Artifacts
2. Lee los mensajes de error cuidadosamente
3. Consulta los Tips en este README
4. Revisa el ejemplo de uso esperado

---

**¡Buena suerte! 🚀** Recuerda: el objetivo es aprender, así que no te preocupes si no lo logras al primer intento. Cada error es una oportunidad de aprender.