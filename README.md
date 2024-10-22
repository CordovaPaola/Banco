# Banco
El objetivo del proyecto es realizar algunas acciones básicas de un cajero electrónico.
#Start code here
#Cordova Ortiz Paola # your own code
#3ADM # your own code
#Ciencia de Datos e Información # your own code
#Proyecto sobre Caja de Banco # your own code
#Uso del modulo time para manejar el tiempo en segundos. # your own code
import time
#Declaración de variables # your own code
#Variables constantes de nombres. # your own code
nom1 = "Paola Cordova"
nom2 = "Erika Garcia"
nom3 = "Marimar Palacios"
nom4 = "Alan Ortiz"
#Variables constantes de NIP. # your own code
NIP1 = 1329
NIP2 = 1622
NIP3 = 4249
NIP4 = 3454
#Variables constantes de numeros de tarjetas. # your own code
numTarjeta1 = 12345614
numTarjeta2 = 13283423
numTarjeta3 = 13292832
numTarjeta4 = 22164241
#Variables constantes de saldos disponibles. # your own code
saldo1 = 29,444
saldo2 = 13,444
saldo3 = 28,888
saldo4 = 22,166
separador = ("---")*7
#Inicio de programa.  # your own code
#Menú de Principal.  # your own code
print("\t", "            BIENVENIDO", "\t")
#Uso del while para que en caso de elejir  *nueva operacion*  se regresara al menu principal. # your own code
otraOperacion = input("Pulse cualquier letra para continuar o 'n' para cerrar.")
while otraOperacion != "n":
  print("              1)MOVIMIENTO EN EFECTIVO\n              2)MOVIMIENTO CON TARJETA\n")
  #Entrada de el movimiento que desea realizar el usuario. # your own code
  movimiento = int(input("           ¿Que movimiento desea realizar?"))
  print("")
  #Acciones a realizar si se desea hacer un Movimiento en efectivo.. # your own code
  if movimiento == 1:
    print("\t", "", "     ACTIVIDADES EN EFECTIVO")
    print("                 A)PAGO DE SERVICIOS\n             B)PAGO DE TARJETA DE CREDITO")
    actividadEfec = input("        Ingrese la actividad que desea realizar: ")
    if actividadEfec == "A" :
      print("\t", "\t", "      SERVICIOS")
      print("1)AGUA\n2)LUZ\n3)TELEFONO\n4)OTRO")
      sevicio = int(input("¿Que servicio desea pagar?"))
      if sevicio == 1:
        nomServicio = "Agua"
      elif sevicio == 2:
        nomServicio = "Luz"
      elif sevicio == 3:
        nomServicio = "Telefono"
      elif sevicio == 4:
        nomServicio = input("Ingrese el nombre del servicio: ")
      else:
        print("Ha ingresado un servicio invalido.")
      convenio = int(input("Ingrese el número de convenio :"))
      monto = float(input("Ingrese el monto a pagar : "))
      if monto > 0:
        efectivo = float(input("Ingrese efectivo: "))
        if efectivo >= monto:
          if efectivo > monto:
            cambio = efectivo - monto
            print("Usted adquiere un cambio de:", cambio)
            for i in range(3):
              time.sleep(1)
              print("...")
          else:
            cambio = "No adquiere cambio,ingreso una cantidad exacta"
          print("Favor de ingresar las siguientes opciones para contestar.")
          print("1)Si\n2)No\n")
          comprobante = int(input("¿Desea imprimir su comprobante?"))
          print("")
          if comprobante == 1:
            print(separador, "COMPROBANTE", separador)
            print("SERVICIO PAGADO:", nomServicio)
            print("NUMERO DE CONVENIO INGRESADO :", convenio)
            print("TOTAL PAGADO:", monto)
            print("EFECTIVO INGRESADO : ", efectivo)
            print("CAMBIO : ", cambio)
            print("---------------------------------------------------------")
          else:
            print("De avuerdo, gracias.")
        else:
          print("Tiene dinero insuficiente para pagar el servicio.")
        otraOperacion = input("¿Desea realizar alguna otra operación? (s-Si / n-No):")
        if otraOperacion == "N" or "n":
          print("        Muchas gracias por elegir nuestra sucursal.")
          print("                     !Vuelva pronto!")
          print("************************************************************\n")
    elif actividadEfec == "B" :
      print("\n", "\t", "\t", "  DATOS A INGRESAR", "\t")
      numTarjeta = int(input("Ingresa el número de tarjeta (8 numeros enteros):"))
      if numTarjeta>=10000000 and numTarjeta<100000000:
        totPagar = float(input("Ingrese el total a pagar:"))
        if totPagar > 0:
          efect = float(input("Ingrese efectivo:"))
          if efect >= totPagar:
            if efect > totPagar:
              camb = efect - totPagar
              print("Usted adquiere un cambio de:", camb)
              for i in range(3):
                time.sleep(1)
                print("...")
            else:
              camb = "No adquiere cambio,ingreso una cantidad exacta"
            print("Favor de ingresar las siguientes opciones para contestar.")
            print("1)Si\n2)No\n")
            comproTarjeta = int(input("¿Desea imprimir su comprobante?"))
            print("")
            if comproTarjeta == 1:
              print(separador, "COMPROBANTE", separador)
              print("\t", "             PAGO EXITOSO", "\t", "")
              print("NUMERO DE TARJETA:", numTarjeta)
              print("TOTAL PAGADO:", totPagar)
              print("CAMBIO : ", camb)
              print("---------------------------------------------------------")
            else:
              print("De acuerdo, gracias.")
          else:
            print("\t\t    TARJETA NO PAGADA\n")
          otraOperacion = input("¿Desea realizar alguna otra operación? (s-Si / n-No):")
          if otraOperacion == "N" or "n":
            print("        Muchas gracias por elegir nuestra sucursal.")
            print("                     !Vuelva pronto!")
            print("************************************************************\n")
        else:
          print("Cantidad no valida.")
      else:
        print("Ha ingresado un número de tarjeta invalido.\n")
    else:
      print("No se encuentra esta opción.")
  elif movimiento == 2:
    nTarjeta = int(input("Ingrese el número de tarjeta (8 números emteros) :"))
    if nTarjeta == numTarjeta1:
      print("Ha ingresado un número de tarjeta valido")
      nip = int(input("Ingrese su NIP (4 números):"))
      if nip == NIP1:
        print("Ha ingresado un número de tarjeta valido")
        print("\n", "\t", "       ACTIVIDADES CON TARJETA")
        print("\t\t  a) CONSULTAR SALDO\n\t\t  b) RETIRAR EFECTIVO\n\t\t  c) PAGO DE SERVICIOS\n")
        actividadTarj = input("        Ingrese la actividad que desea realizar: ")
        if actividadTarj == "a":
          nipSaldo = int(input("Ingrese su NIP (4 números):"))
          if nipSaldo >= 1000 and nipSaldo <= 10000:
            print("SALDO DISPONIBLE: $", saldo1)
            print("Favor de ingresar las siguientes opciones para contestar.")
            print("1)Si\n2)No\n")
            comprobanteSaldo = int(input("¿Desea imprimir su comprobante?"))
            if True:
              print(separador, "COMPROBANTE", separador)
              print("SALDO DISPONIBLE: $", saldo1)
              print("-_-_"*10)
              print("")
            else:
              print("De acuerdo, gracias.")
            otraOperacion = input("¿Desea realizar alguna otra operación? (s-Si / n-No):")
            if otraOperacion == "N" or "n":
              print("        Muchas gracias por elegir nuestra sucursal.")
              print("                     !Vuelva pronto!")
              print("************************************************************\n")
          else:
            print("Ha ingresado un NIP invalido.")
        elif actividadTarj == "b":
          print("")
          print("Bienvenid@", nom1)
          retirar = float(input("¿Cuanto desea retirar? "))
          if retirar < saldo1:
            print("Se esta preparando su efectivo ...")
            for i in range(3):
              time.sleep(1)
              print("...")
            print("Se ha acompletado su requesito\n")
            print("Retire efectivo")
            for i in range(3):
              time.sleep(1)
              print("...")
            print("Favor de ingresar las siguientes opciones para contestar.")
            print("1)Si\n2)No\n")
            comprobanteRetirar = int(input("¿Desea imprimir su comprobante?"))
            if comprobanteRetirar == 1:
              print(separador, "COMPROBANTE", separador)
              print("SU SALDO ES:", saldo1)
              print("USTED HA RETIRADO:", retirar)
              print("---------------------------------------------------------")
              print("")
            else:
              print("De acuerdo, gracias.")
            otraOperacion = input("¿Desea realizar alguna otra operación? (s-Si / n-No):")
            if otraOperacion == "N" or "n":
              print("        Muchas gracias por elegir nuestra sucursal.")
              print("                     !Vuelva pronto!")
              print("************************************************************\n")
          else:
            print("La cantidad ingresada no puede ser retirada por falta de fondos.")
        elif actividadTarj == "c":
          print("\n", "Bienvenid@", nom1)
          print("SALDO QUE DISPONE:", saldo1)
          print("\t", "\t", "       SERVICIOS")
          print("1)AGUA\n2)LUZ\n3)TELEFONO\n4)OTRO")
          servicioPagar = int(input("¿Que servicio desea pagar?"))
          if servicioPagar == 1:
            servicioN = "Agua"
          elif servicioPagar == 2:
            servicioN = "Luz"
          elif servicioPagar == 3:
            servicioN = "Telefono"
          elif servicioPagar == 4:
            servicioN = input("Ingrese el nombre del servicio: ")
          else:
            print("Ha ingresado un servicio invalido.")
          numConvenio = int(input("Ingrese el número de convenio :"))
          montoPago = int(input("Ingrese el monto a pagar : "))
          if montoPago > 0:
            pago = input("¿Desea realizar el pago [s-Si / n-No] ? ")
            if pago == "s":
              if montoPago <= saldo1:
                restoSaldo = 29444 - montoPago
                print("Ha quedado un saldo de:", restoSaldo)
              else:
                restoSaldo = "No hay saldo suficiente"
              print("Favor de ingresar las siguientes opciones para contestar.")
              print("1)Si\n2)No\n")
              comprobanteSer = int(input("¿Desea imprimir su comprobante?"))
              print("")
              if comprobanteSer == 1:
                print(separador, "COMPROBANTE", separador)
                print("SERVICIO PAGADO:", servicioN)
                print("NUMERO DE CONVENIO INGRESADO :", numConvenio)
                print("TOTAL PAGADO:", montoPago)
                print("RESTO DE SALDO : ", restoSaldo)
                print("---------------------------------------------------------")
              else:
                print("De acuerdo, gracias.")
            else:
              print("De acuerdo, gracias.")
            otraOperacion = input("¿Desea realizar alguna otra operación? (s-Si / n-No):")
            if otraOperacion == "N" or "n":
              print("        Muchas gracias por elegir nuestra sucursal.")
              print("                     !Vuelva pronto!")
              print("************************************************************\n")
        else:
          print("Ha ingresado una opcion que no corresponde al menu.")
      else:
        print("Ha ingresado un número de tarjeta invalido.")
    else:
      print("Ha ingresado un número de tarjeta invalido.")
  else:
    print("El movimiento a elegir es invalido.")
