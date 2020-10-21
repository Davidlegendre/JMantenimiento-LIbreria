# JMantenimiento-LIbreria
Documentación
Librería para manipular datos en tablas de la base de datos

Uso
Para usar la librería es necesario importarla a nuestro proyecto en java
 

Luego instanciamos la clase MantenimientoNivel1
 

En el constructor colocaremos
 
Donde TbDataCargo es el nombre de la tabla que tenemos en nuestro diseño.

Luego le colocamos las dos columnas para mostrarlo en la ejecución del formulario
 
Podemos colocar cualquier nombre para las dos columnas del formulario

Requisitos:
Tener una tabla para los registros en el diseño con dos columnas
Tener las clases instanciadas de java.sql en el código del formulario:
Connection, ResultSet y Statement





Componentes:
Metodo	parametros	descripcion
setNombresColumnas()	Titulos : List<String>	Asigna los nombres de las columnas a la tabla descrita en la instancia de la clase
Nuevo()	Textbox[] : Arreglo de JTextField
TextoSelecion : JtextField	Limpia los JtextField indicados en el arreglo y coloca el foco al JtextField TextoSelecion
Cancelar()	Frame : JFrame	Realiza comprobación y cerrado del formulario indicado
SeleccionarEnTabla()	Nom : JTextField
Cod : JTextField
JTable : TablaDeDatos	Coloca los datos seleccionado de la tabla indicada a los JTextField de código y nombre indicados
Guardar()	Nom : JTextField
ProcedimientoAlmacenado : String
conexion : Connection
statement : Statement	Guarda el nombre indicado con el procedimiento indicado, además se tiene que indicar la conexión de tipo Connection de la base de datos y el Statement para procedimientos almacenados.

El procedimiento tiene esta sintaxis:
“{call procedimiento(?,?,?,…)}”
Modificar()	Nom : JTextField
Cod : JTextField
TablaDeDatos : JTable
ProcedimientoAlamcenado : String
conexion : Connection
statement : Statement	Modifica un registro en la base de datos indicando el nombre a actualizar y el código (id), además se tiene que pasar la tabla de datos del formulario (colocando el nombre).

Al igual que el anterior, requiere del procedimiento almacenado, de la conexión de tipo Connection y el Statement para procedimientos alamacenados.
BorrarTabla()	Ninguno	No accesible (solo para uso interno)
ActualizarDatos()	conexion : Connection
RetornoRs : ResultSet
numCampos : int	Obtiene y muestra los datos de la base de datos, indicando la conexión de tipo Connection y un resultset encargado de hacer la consulta, es necesario contar con la tabla en el formulario.

numCampos indica cuantos campos se quieren ver, según los campos de la base de datos o la consula.

Buscar()	conexion : Connection
rx : ResultSet
numCampos : int	Busca un dato en la tabla de la base de datos, indicando la conexión de tipo connection y el resultset encargado de realizar la búsqueda, es necesario contar con la tabla en el formulario.

numCampos indica cuantos campos se quieren ver, según los campos de la base de datos o la consula.


Nota: La librería no se encarga de realizar directamente las búsquedas y las actualizaciones de los datos, más bien ya se debería contar con los métodos con retorno ResultSet para las consultas.
Además en los métodos:
ActualizarDatos, guardar, modificar y buscar, es necesario llamarlos dentro de un try-catch, es un requisito indispensable para registrar excepciones, si no se coloca dentro del try, no funcionara.
