# 3 Métodos de ordenación en python
# Imports para VSC:
    import random

    from datetime import datetime

# Las funciones las podemos hacer en otro archivo:
  # Metodo funcion:
    def burbuja(bur):
      intercambio = True
      while intercambio:
          intercambio = False
          for i in range (len(bur) - 1):
              if bur[i] > bur[i + 1]:
                  bur[i], bur[i + 1] = bur[i+1], bur[i]
                  intercambio = True

  # Metodo seleccion:
    def seleccion(sel):
      for a in range (len(sel)):
          valor_menor = a
          for b in range (a + 1, len(sel)):
              if sel[b] < sel[valor_menor]:
                  valor_menor = b
          sel[a], sel[valor_menor] = valor_menor, sel[a]

  # Metodo insercion:
    def insercion(inser):
      for u in range (1, len(inser)):
          items = inser[u]
          o = u - 1
          while (o >= 0 and inser[o] > items):
              inser[o + 1] = inser[o]
              o -= 1
          inser[o + 1] = items
# Fin de las funciones
# Ahora vamos con el codigo principal:

    # Lista y revisiones:
    print("De que tamaño deseas la array? (sola numeros)")
    tamano = input()

    print("Cuantas revisiones quieres hacer?")
    revision = input()

    lista = []
    contador_rondas = 0

    numero_random = random.randint(1, 1000000)

    # Se repite hasta que el tamaño de la lista no llegue a tamano:
    while contador_rondas < int(tamano): 
        numero_random = random.randint(1, 1000000)
        if numero_random in lista:
            pass
        else:
            lista.append(numero_random)
            contador_rondas = contador_rondas + 1

    # Funcionamiento revisiones:
    z = 0
    while z < int(revision):
        z = z + 1
        print()
        print("Revisión numero:", z)

        # Metodo burbuja
        time_start1 = datetime.now()

        funciones.burbuja(lista.copy())

        time_stop1 = datetime.now()
        burbuja_temp = time_stop1 - time_start1
        print("Ha tardado ", burbuja_temp, "en ordenarlo con el metodo burbuja.")


        # Metodo seleccion
        time_start2 = datetime.now()

        funciones.seleccion(lista.copy())

        time_stop2 = datetime.now()
        seleccion_temp = time_stop2 - time_start2
        print("Ha tardado ", seleccion_temp, "en ordenarlo con el metodo seleccion.")


        # Metodo insercion
        time_start3 = datetime.now()

        funciones.insercion(lista.copy())

        time_stop3 = datetime.now()
        insercion_temp = time_stop3 - time_start3
        print("Ha tardado ", insercion_temp, "en ordenarlo con el metodo inserción.")
