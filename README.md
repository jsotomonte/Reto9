# Reto9
Escribir funciones pasadas en lambdas 
## Primera función
### Función para determinar el cambio de un mercado o si fue exacto 
````python
Compra = lambda P, M, H, PAN = float(300), LECHE = float(3300), HUEVOS = float(350) : PAN * P + LECHE * M + HUEVOS * H

if __name__ == "__main__":
    P = float(input("Cantidad de panes: "))
    M = float(input("Cantidad de bolsas de leche: "))
    H = float(input("Cantidad de huevos: "))
    B = float(input("Valor del billete con el que se paga: "))

    total = Compra(P, M, H)

    vueltas = lambda B, total: B - total

    deuda = vueltas(B, total)

    if deuda > 0:
        print("Sus vueltas son " + str(deuda) + " COP")
    elif deuda < 0:
        print("Quedó debiendo " + str(abs(deuda)) + " COP")
    else:
        print("El pago fue exacto")

````
## Segunda función
### función para determinar el valor de un prestamo 
````python
Valorprestamo = lambda C, i, n: C * (1 + (i / 100)) ** n

if __name__ == "__main__":
    C = float(input("Valor del préstamo adquirido: "))
    i = float(input("Porcentaje del interés: "))
    n = float(input("Meses a los que se sacó el préstamo: "))
    valorfinal = Valorprestamo(C, i, n)
    valorfinalimit = "{:.2f}".format(valorfinal)

    print("El valor del préstamo es " + str(valorfinalimit))

````
## tercera función 
### Cantidad de carne comprada 
````python
Carnetotal = lambda N, M, K, GALLINAS = float(6), GALLOS = float(7), POLLITOS = float(1) : GALLINAS * N + GALLOS * M + POLLITOS * K

if __name__ == "__main__":
    N = float(input("Cantidad de gallinas: "))
    M = float(input("Cantidad de gallos: "))
    K = float(input("Cantidad de pollos: "))
    pesototal = Carnetotal(N, M, K)

    print("El peso total de las carnes es: " + str(pesototal) + " KG")
````

# Parte 2. 
Escoger otras tres funciones y escribirlas con argumentos no definidos 
## Primera función  
### Operaciones de 5 terminos (promedio, mediana, mayor, menor, oden ascendente y descendente)
````python
def Promedio(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    prom = sum(args) / 5
    return prom

def Mediana(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    medi = list(args)
    return sorted(medi)[2]

def PromedioMultiplicativo(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    promultiplicativo = (args[0] * args[1] * args[2] * args[3] * args[4]) ** (1/5)
    return promultiplicativo

def Ordenascendente(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    ascen = list(args)
    return sorted(ascen)

def Ordendescendente(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    descen = list(args)
    return sorted(descen, reverse=True)

def Mayor(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    may = list(args)
    return max(may)

def Menor(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    men = list(args)
    return min(men)

def Potmayorxmenor(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    pot = list(args)
    return max(pot) ** min(pot)

def Raizcubicamenor(*args):
    if len(args) != 5:
        raise ValueError("error, ingrese los valores requeridos")
    
    cub = list(args)
    return min(cub) ** (1/3)

if __name__ == "__main__":
    v = float(input("Valor v: "))
    w = float(input("Valor w: "))
    x = float(input("Valor x: "))
    y = float(input("Valor y: "))
    z = float(input("Valor z: "))
    
    promedio = Promedio(v, w, x, y, z)
    mediana = Mediana(v, w, x, y, z)
    promedio_multiplicativo = PromedioMultiplicativo(v, w, x, y, z)
    orden_ascendente = Ordenascendente(v, w, x, y, z)
    orden_descendente = Ordendescendente(v, w, x, y, z)
    mayor_valor = Mayor(v, w, x, y, z)
    menor_valor = Menor(v, w, x, y, z)
    potencia_mayor_x_menor = Potmayorxmenor(v, w, x, y, z)
    raiz_cubica_menor = Raizcubicamenor(v, w, x, y, z)

    print("Promedio: " + str(promedio))
    print("Mediana: " + str(mediana))
    print("Promedio Multiplicativo: " + str(promedio_multiplicativo))
    print("Orden Ascendente: " + str(orden_ascendente))
    print("Orden Descendente: " + str(orden_descendente))
    print("Mayor Valor: " + str(mayor_valor))
    print("Menor Valor: " + str(menor_valor))
    print("Potencia Mayor x Menor: " + str(potencia_mayor_x_menor))
    print("Raíz Cúbica del Menor Valor: " + str(raiz_cubica_menor))

````
## Segunda función  
### Función de contagiados através del tiempo  
````python
def Contagios(*args):
    if len(args) != 2:
        raise ValueError("La función Contagios requiere exactamente 2 argumentos.")
    
    C, D = args
    nuevosContagios = C * (2 ** (D - 1))
    return nuevosContagios

if __name__ == "__main__":
    C = float(input("Numero de contagiados actuales: "))
    D = float(input("Dias transcurridos: "))
    contagiosfinal = Contagios(C, D)

    print("El número de contagiados en " + str(D) + " días es de " + str(contagiosfinal))

````
## Tercera función  
### Volumen de solidos y sumatoria total 
````python
import math

def Volumenesfera(*args):
    if len(args) != 1:
        raise ValueError("error intente de nuevo")
    
    r1 = args[0]
    volesfera = (4/3) * math.pi * (r1 ** 3)
    return volesfera

def Areaesfera(*args):
    if len(args) != 1:
        raise ValueError("error intente de nuevo")
    
    r1 = args[0]
    aresfera = 4 * math.pi * (r1 ** 2)
    return aresfera

def Volumencono(*args):
    if len(args) != 2:
        raise ValueError("error intente de nuevo")
    
    r2, h = args
    volcono = (math.pi * (r2 ** 2) * h) / 3
    return volcono

def Areacono(*args):
    if len(args) != 2:
        raise ValueError("error intente de nuevo")
    
    r2, h = args
    arcono = (math.pi * r2) * (math.sqrt(h ** 2 + r2 ** 2)) + math.pi * (r2 ** 2)
    return arcono

def Volumentotal(*args):
    if len(args) != 3:
        raise ValueError("error intente de nuevo")
    
    r1, r2, h = args
    voltotal = ((4/3) * math.pi * (r1 ** 3)) + ((math.pi * (r2 ** 2) * h) / 3)
    return voltotal

def Areatotal(*args):
    if len(args) != 3:
        raise ValueError("error intente de nuevo")
    
    r1, r2, h = args
    artotal = ((math.pi * r2) * (math.sqrt(h ** 2 + r2 ** 2)) + math.pi * (r2 ** 2)) + 4 * math.pi * (r1 ** 2)
    return artotal

if __name__ == "__main__":
    r1 = float(input("Radio de la esfera: "))
    r2 = float(input("Radio del cono: "))
    h = float(input("Altura del cono: "))
    volumenE = Volumenesfera(r1)
    areaE = Areaesfera(r1)
    volumenC = Volumencono(r2, h)
    areaC = Areacono(r2, h)
    volumenT = Volumentotal(r1, r2, h)
    areaT = Areatotal(r1, r2, h)

    print("El volumen de la esfera es: " + str(volumenE))
    print("El área de la esfera es: " + str(areaE))
    print("El volumen del cono es: " + str(volumenC))
    print("El área del cono es: " + str(areaC))
    print("El volumen del cono y la esfera juntos es: " + str(volumenT))
    print("El área del cono y la esfera juntos es: " + str(areaT))

````

# Parte 3 

Escriba una función recursiva para calcular la operación de la potencia.

````python
def potencia(base, exponente):
  if exponente == 0:
    return 1
  elif exponente > 0:
    return base * potencia(base, exponente - 1)
  else:
    return 1 / (base * potencia(base, -exponente))

base = float(input("Ingrese la base: "))
exponente = int(input("Ingrese el exponente: "))

resultado = potencia(base, exponente)
print(f"{base} ^ {exponente} = {resultado}")
````
# Parte 4
Realice pruebas para calcular fibonacci con iteración o con recursión. Determine desde que número de la serie la diferencia de tiempo se vuelve significativa.

````python
import time

start_time = time.time()

def fib(n):
    if n <= 0:
        return 0
    elif n == 1:
        return 0
    elif n == 2:
        return 1
    else:
        a, b = 0, 1
        max = 1
        for _ in range(2, n):
            a, b = b, a + b
            if b > max:
                max = b
        return max

n = int(input("ingrese el digito de la secuencia: "))

while True:
  if time.time() - start_time < 5:

    ultimo = fib(n)
    print(f"El número de Fibonacci en {n} es {ultimo}")
    break
  print("el tiempo se exedio")
  break

end_time = time.time()

timer = end_time - start_time
print(f"se demoro {timer:.2f} segundos")
````
## Stackoverflow 
![image](https://github.com/jsotomonte/Reto9/assets/141857089/c11e9358-2fd4-4a7c-ba46-534323af76f8)

## Linkedin 
![image](https://github.com/jsotomonte/Reto9/assets/141857089/99e37395-5cff-4c6d-a217-e4e4ea69f2ac)
