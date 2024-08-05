Productos = {1: 'Pantalones:\t', 2: 'Camisas: \t', 3: 'Corbatas:\t', 4: 'Casacas:\t'}
Precios = {1:200.00, 2: 120.00, 3: 50.00, 4: 350.00}
Stock = {1: 50, 2: 45, 3: 30, 4: 15}

def mostrar_productos():
  print("=============================================================================")
  print("Lista de Productos:  ")
  print("=============================================================================")
  for clave, producto in Productos.items():
    print(f"{clave}\t{producto}\t\t{Precios[clave]:.2f} \t\t{Stock[clave]}")
  print("=============================================================================")

def agregar_producto():
  nuevo_producto = input("Ingrese el nombre del nuevo producto: ")
  nuevo_precio = float(input("Ingrese el precio del nuevo producto: "))
  nuevo_stock = int(input("Ingrese el stock del nuevo producto: "))
  nueva_clave = max(Productos.keys()) + 1
  Productos[nueva_clave] = nuevo_producto
  Precios[nueva_clave] = nuevo_precio
  Stock[nueva_clave] = nuevo_stock
  print("Producto agregado exitosamente.")

def eliminar_producto():
  clave_eliminar = int(input("Ingrese el código del producto a eliminar: "))
  if clave_eliminar in Productos:
    del Productos[clave_eliminar]
    del Precios[clave_eliminar]
    del Stock[clave_eliminar]
    print("Producto eliminado exitosamente.")
  else:
    print("El producto no existe.")

def actualizar_producto():
  clave_actualizar = int(input("Ingrese el código del producto a actualizar: "))
  if clave_actualizar in Productos:
    nuevo_precio = float(input("Ingrese el nuevo precio: "))
    nuevo_stock = int(input("Ingrese el nuevo stock: "))
    Precios[clave_actualizar] = nuevo_precio
    Stock[clave_actualizar] = nuevo_stock
    print("Producto actualizado exitosamente.")
  else:
    print("El producto no existe.")

while True:
  mostrar_productos()
  opcion = input("\nElija opción: \n\n[1] Agregar \n[2] Eliminar \n[3] Actualizar \n[4] Salir \n\n¿Cuál elige?\n ")
  if opcion == '1':
    agregar_producto()
  elif opcion == '2':
    eliminar_producto()
  elif opcion == '3':
    actualizar_producto()
  elif opcion == '4':
    break
  else:
    print("Opción inválida.")
