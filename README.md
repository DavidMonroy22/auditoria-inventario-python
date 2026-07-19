# auditoria-inventario-python
Este proyecto fue desarrollado como solución al Problema 3 del Banco de Problemas de la Fase 5 del curso Fundamentos de Programación de la Universidad Nacional Abierta y a Distancia (UNAD).

El programa permite auditar un inventario utilizando una matriz de datos que contiene el código del artículo, nombre, stock actual y stock mínimo requerido. A través de una función en Python se determina la cantidad exacta de productos que deben solicitarse para reabastecer el inventario.

Tecnologías utilizadas
Python 3
Autor

José David Monroy Pabón

Estudiante de Ingeniería de Sistemas – UNAD

INICIO DE CODIGO PYTHON

# ==========================================
# Fase 5 - Problema 3
# Auditoría de Inventario
# Autor: José David Monroy Pabón
# ==========================================

def calcular_pedido(stock_actual, stock_minimo):
    """
    Calcula la cantidad que debe solicitarse.
    """
    if stock_actual < stock_minimo:
        return stock_minimo - stock_actual
    else:
        return 0


inventario = [
    ["A001", "Cuadernos", 5, 10],
    ["A002", "Lápices", 20, 15],
    ["A003", "Borradores", 3, 8],
    ["A004", "Marcadores", 12, 12],
    ["A005", "Carpetas", 4, 10]
]

print("========================================")
print("REPORTE DE REABASTECIMIENTO")
print("========================================")

for articulo in inventario:

    codigo = articulo[0]
    nombre = articulo[1]
    stock_actual = articulo[2]
    stock_minimo = articulo[3]

    cantidad_pedir = calcular_pedido(
        stock_actual,
        stock_minimo
    )

    print(f"Código: {codigo}")
    print(f"Artículo: {nombre}")
    print(f"Cantidad a solicitar: {cantidad_pedir}")
    print("--------------------------------")
