# perm1B_grupo_3
#Se le da un valor a "saldo"
saldo = 10000
#Creamos una lista
L = [20, 50, 100, 150, 500]
salir = True
#Definimos  "menu"
def menu():
#Son las opciones que va a tener el menú
    print()
    print("MENU:")
    print("1. Ver Saldo")
    print("2. Retirar")
    print("3. Salir")
    print()  # Sirve para poder dejar un espacio entre las lineas.
    accion = int(input("Elija accion a realizar: "))
    #La acción que va a realizar la acción 1 será la ejecución de la línea 55
    if accion == 1:
        verSaldo()
        input("Presione entrer para continuar")
        menu()
    if accion == 2:
        retiro()
        menu()
    if accion == 3:
        Salir()
        salir = False

def retiro():
    global saldo
    print()
    print("MONTOS PERMITIDOS PARA RETIRAR E INGRESAR DINERO:")
    print("1. S/20")
    print("2. S/50")
    print("3. S/100")
    print("4. S/150")
    print("5. S/500")
    opcion2 = int(input("Ingrese monto a retirar: "))
    retiro = int(opcion2)

    if retiro == 0:
        print("Solo puede retirar las cantidades permitidas")
        input("Presione enter para volver al menú")
   

    elif retiro > saldo:
        print("No tiene sufiente saldo para retirar esa cantidad")
        input("Presione enter para volver al menú")

    for i in L:
        if retiro == i:
            saldo -= retiro
            print(f"Dinero total de la cuenta: {saldo}")
            input("Presione enter para volver al menú")

def verSaldo():

    print("Su saldo actual es de: ", saldo)

def Salir():

    print("Gracias por su preferencia, nos vemos pronto")

    while salir == False:
        break

clave = input("Ingrese la clave: ")
while clave != "1313":
    clave = input("Ingresa la contraseña correcta: ")
else:
    menu()
