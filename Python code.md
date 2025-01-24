# Calculadora-funcional-Python
#"Jhouran Del Toro"

import math

def mostrar_menu():
    print("\n--- Calculadora Científica ---")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicación")
    print("4. División")
    print("5. Seno (en grados)")
    print("6. Coseno (en grados)")
    print("7. Tangente (en grados)")
    print("8. Logaritmo base 10")
    print("9. Logaritmo natural (ln)")
    print("10. Exponencial (e^x)")
    print("11. Raíz cuadrada")
    print("12. Salir")
    print("-" * 30)

def obtener_numero(mensaje):
    while True:
        try:
            return float(input(mensaje))
        except ValueError:
            print("Entrada inválida. Por favor, ingrese un número.")

def calculadora():
    while True:
        mostrar_menu()
        opcion = input("Seleccione una opción (1-12): ")

        if opcion == "12":
            print("Saliendo de la calculadora. ¡Adiós!")
            break

        if opcion in {"1", "2", "3", "4"}:
            num1 = obtener_numero("Ingrese el primer número: ")
            num2 = obtener_numero("Ingrese el segundo número: ")

            if opcion == "1":
                print(f"Resultado: {num1 + num2}")
            elif opcion == "2":
                print(f"Resultado: {num1 - num2}")
            elif opcion == "3":
                print(f"Resultado: {num1 * num2}")
            elif opcion == "4":
                if num2 == 0:
                    print("Error: No se puede dividir por cero.")
                else:
                    print(f"Resultado: {num1 / num2}")

        elif opcion in {"5", "6", "7", "8", "9", "10", "11"}:
            num = obtener_numero("Ingrese un número: ")

            if opcion == "5":
                print(f"Seno({num}) = {math.sin(math.radians(num))}")
            elif opcion == "6":
                print(f"Coseno({num}) = {math.cos(math.radians(num))}")
            elif opcion == "7":
                print(f"Tangente({num}) = {math.tan(math.radians(num))}")
            elif opcion == "8":
                if num <= 0:
                    print("Error: El logaritmo base 10 no está definido para números menores o iguales a cero.")
                else:
                    print(f"Logaritmo base 10 de {num} = {math.log10(num)}")
            elif opcion == "9":
                if num <= 0:
                    print("Error: El logaritmo natural no está definido para números menores o iguales a cero.")
                else:
                    print(f"Logaritmo natural (ln) de {num} = {math.log(num)}")
            elif opcion == "10":
                print(f"Exponencial (e^{num}) = {math.exp(num)}")
            elif opcion == "11":
                if num < 0:
                    print("Error: La raíz cuadrada no está definida para números negativos.")
                else:
                    print(f"Raíz cuadrada de {num} = {math.sqrt(num)}")
        else:
            print("Opción inválida. Por favor, elija una opción del 1 al 12.")

# Inicia la calculadora
if __name__ == "__main__":
    calculadora()
