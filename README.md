Parcial 1 - Sistema de Cuentas Bancarias

Proyecto en Java que simula la gestión básica de cuentas bancarias (Ahorro y Corriente), con operaciones de creación, consulta, retiro y depósito de dinero a través de un menú de consola.

Estructura del proyecto
src/
├── App.java                     # Punto de entrada, menú de consola
├── domain/
│   ├── Cuenta.java              # Clase base: numeroCuenta, dniCliente, saldoActual
│   ├── Ahorro.java              # Extiende Cuenta, agrega fechaCreacion
│   └── Corriente.java           # Extiende Cuenta, agrega impuesto sobre retiros
└── service/
    ├── IServiceCuenta.java      # Contrato del servicio de cuentas
    └── ServiceCuenta.java       # Implementación en memoria (ArrayList)
Funcionalidades
Listar cuentas: muestra todas las cuentas registradas (ahorro y corriente).
Buscar cuenta: busca una cuenta por su número.
Crear cuenta: registra una nueva cuenta de ahorro o corriente, validando que el número no esté repetido.
Retirar dinero: descuenta saldo validando monto positivo y saldo suficiente. En cuentas corrientes, aplica un impuesto adicional sobre el monto retirado.
Ingresar dinero: agrega saldo validando que el monto sea positivo.
Modelo de dominio
Cuenta: clase base con la lógica común de retirar() y depositar().
Ahorro: cuenta sin impuesto sobre retiros, incluye fecha de creación.
Corriente: sobreescribe retirar() para cobrar un impuesto (proporción, ej. 0.004 = 0.4%) sobre cada retiro.
Cómo compilar y ejecutar

Desde la raíz del proyecto:

bash
javac -d bin src/App.java src/domain/*.java src/service/*.java
java -cp bin App

También puede ejecutarse directamente desde VS Code con la extensión de Java, usando App.java como clase principal.

Requisitos
JDK 14 o superior (se usa switch con expresiones de flecha -> en el menú).
Autor

Jose Fernando Godoy Quiroz
