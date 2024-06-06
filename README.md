#Leer dos números enteros y si la diferencia entre los dos números es par mostrar en pantalla la suma de los dígitos de los números, si dicha diferencia es un número primo menor que 10 entonces mostrar en pantalla el producto de los dos números y si la diferencia entre ellos terminar en 4 mostrar en pantalla todos los dígitos por separado.


print("Ingrese el primer número: ")
num1 = int(input())

print("Ingrese el segundo número: ")
num2 = int(input())
diferencia = num1 - num2

def es_primo(num):
  if num < 2:
      return False
  for i in range(2, int(num**0.5) + 1):
      if num % i == 0:
          return False
  return True

def suma_digitos(num):
  suma = 0
  while num > 0:
      suma += num % 10
      num //= 10
  return suma

def mostrar_digitos(num):
  digitos = []
  while num > 0:
      digitos.append(num % 10)
      num //= 10
  return digitos[::-1]
if diferencia % 2 == 0:
  suma_numero1 = suma_digitos(num1)
  suma_numero2 = suma_digitos(num2)
  print(f"Suma de los dígitos del primer número: {suma_numero1}")
  print(f"Suma de los dígitos del segundo número: {suma_numero2}")


if diferencia < 10 and es_primo(diferencia):
  producto = num1 * num2
  print(f"Producto de los dos números: {producto}")

if diferencia % 10 == 4:
  digitos_numero1 = mostrar_digitos(num1)
  digitos_numero2 = mostrar_digitos(num2)
  print("Dígitos del primer número por separado:", digitos_numero1)
  print("Dígitos del segundo número por separado:", digitos_numero2)
else:
    print("operación no valida")

print("Fin del programa (✿◡‿◡)")


