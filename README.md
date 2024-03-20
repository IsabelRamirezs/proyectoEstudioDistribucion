Experimentación ST vs MT

Estructura de Archivos
    calculadora: contiene la definición de la estructura Operacion y sus métodos asociados para realizar operaciones.

    gestorArchivos: responsable de cargar operaciones desde archivos y listar archivos en un directorio.

    main: Punto de entrada principal del programa para ejecutar las cuatro versiones de la aplicación de calculadora.

Ejecución:
    Ubicarse en el archivo main.go
    Para la ejecución de cada una de las versiones se debe
    comentar lineas de código relacionada con las versiones.

    Ejemplo: 
    //Versión SingleThreaded
	fmt.Println("-> Ejecutando versión de un solo hilo")
	coleccionOperaciones := gestorArchivos.CargarArchivo(instancia)
	tiempoInicial := time.Now()
	for i := 0; i < len(coleccionOperaciones); i++ {
	 	coleccionOperaciones[i].Operar()
	 }

	var suma float32
	suma = 0
	for i := 0; i < len(coleccionOperaciones); i++ {
		suma += coleccionOperaciones[i].Resultado
	}
	fmt.Println("Resultado: ", suma)

	tiempoFinal := time.Since(tiempoInicial)
	fmt.Println("Tiempo transcurrido: ", tiempoFinal)

    Para cambiar las intancias de concurrencia
    modificar ---> instancia := "./InstanciasConcurrencia/01_5.input"
    Por una de las siguientes opciones:
    
	// instancia := "./InstanciasConcurrencia/02_20.input"
	// instancia := "./InstanciasConcurrencia/03_40.input"
	// instancia := "./InstanciasConcurrencia/04_100.input"
	// instancia := "./InstanciasConcurrencia/05_200.input"
	// instancia := "./InstanciasConcurrencia/06_500.input"
	// instancia := "./InstanciasConcurrencia/07_1000.input"
	// instancia := "./InstanciasConcurrencia/08_2500.input"
	// instancia := "./InstanciasConcurrencia/09_10000.input"
