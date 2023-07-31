# SISTEMA DE ELECCIONES

## Integrantes:

- Sergio Sebastian Santos Mena Quispe
- Diego Francisco Apaza Andaluz
- Jesus Bruno Chancayauri Soncco
- Christian Pardavé Espinoza
- Saul Arturo Condori Machaca

### ESTILOS DE PROGRAMACIÓN

Los estilos de programación que utilice en la implementacion que estuvo bajo mi responsabilidad, son los siguientes:
- Programación orientada a objetos:

  - Clases: La clase Votante es una representación de un objeto de tipo "Votante" con sus atributos y métodos. Se utiliza el concepto de clases y objetos para modelar la entidad del dominio que estamos trabajando.
    ```
    class Votante extends Usuario {
      private fechaNacimiento: string;
      private genero: string;
      private ocupacion: string;
    
      constructor(
        nombre: string,
        correo: string,
        rol: string,
        dni: string,
        fechaNacimiento: string = "",
        genero: string = "",
        ocupacion: string = ""
      ) {
        super(nombre, correo, rol, dni); // Llamada al constructor de la clase base Usuario
        this.fechaNacimiento = fechaNacimiento;
        this.genero = genero;
        this.ocupacion = ocupacion;
      }
      /*others functions...*/
    }
    ```
  
  - Encapsulación: Los atributos de la clase Votante (fechaNacimiento, genero y ocupacion) están definidos como privados, lo que significa que solo se pueden acceder y modificar desde dentro de la propia clase. Esto ayuda a proteger los datos y mantener la integridad de los objetos.
    ```
      private fechaNacimiento: string;
      private genero: string;
      private ocupacion: string;
    ```
  
  - Herencia: La clase Votante hereda de la clase Usuario, lo que significa que Votante es una subclase de Usuario. La herencia permite reutilizar código y establecer una relación entre las clases, donde Votante hereda los atributos y métodos de Usuario.
  
    `class Votante extends Usuario`
  
  - Polimorfismo: Aunque no se muestra en el código proporcionado, el polimorfismo permite que objetos de distintas clases que heredan de Usuario se utilicen de manera intercambiable. Por ejemplo, si tenemos una función que acepta un objeto Usuario, también podemos pasarle un objeto Votante, ya que Votante es una subclase de Usuario.
- Programación funcional

  - Funciones puras: Las funciones getFechaNacimiento(), getGenero() y getOcupacion() son funciones puras, ya que no tienen efectos secundarios y su resultado depende únicamente de los valores de entrada. No modifican ningún estado y siempre devuelven el mismo resultado para los mismos argumentos.
     ```
      // Getter methods (funciones puras)
      getFechaNacimiento(): string {
        return this.fechaNacimiento;
      }
    
      getGenero(): string {
        return this.genero;
      }
    
      getOcupacion(): string {
        return this.ocupacion;
      }
     ```
  
  - Funciones de orden superior: Las funciones cambiarFechaNacimiento(), cambiarGenero() y cambiarOcupacion() son funciones de orden superior, ya que toman una función como argumento (por ejemplo, fechaNacimiento en cambiarFechaNacimiento()) y devuelven otra función. Esto permite realizar operaciones más abstractas y genéricas.
  
  - Inmutabilidad: En las funciones de actualización (cambiarFechaNacimiento(), cambiarGenero() y cambiarOcupacion()), en lugar de modificar directamente los atributos de la instancia actual, se crea una nueva instancia de Votante con el atributo actualizado. Esto asegura que el objeto original no se modifique y favorece el estilo funcional, donde los datos son inmutables siempre que sea posible.
     ```
    // Función para actualizar el atributo fechaNacimiento (estilo funcional)
    cambiarFechaNacimiento(fechaNacimiento: string): Votante {
      return Object.assign(new Votante(this.nombre, this.correo, this.rol, this.dni, fechaNacimiento, this.genero, this.ocupacion), this);
    }
  
    // Función para actualizar el atributo genero (estilo funcional)
    cambiarGenero(genero: string): Votante {
      return Object.assign(new Votante(this.nombre, this.correo, this.rol, this.dni, this.fechaNacimiento, genero, this.ocupacion), this);
    }
  
    // Función para actualizar el atributo ocupacion (estilo funcional)
    cambiarOcupacion(ocupacion: string): Votante {
      return Object.assign(new Votante(this.nombre, this.correo, this.rol, this.dni, this.fechaNacimiento, this.genero, ocupacion), this);
    }
     ```
  
