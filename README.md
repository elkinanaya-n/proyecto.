# proyecto.

<img width="921" height="501" alt="image" src="https://github.com/user-attachments/assets/67d8c193-8248-4700-8e54-a80bf476a356" />

import java.util.ArrayList;

public class Main {

    public static void buscarRecurso(int id ) {
        
        System.out.println(" codigo numerico: " + id);
    }

    public static void buscarRecurso(String nombre) {
    System.out.println("  titulo: " + nombre);

}

public static void main(String[] args) {

    ArrayList<RecursoDigital> inventario = new ArrayList<>();

    inventario.add(new Libro("L-003", " La Voragine", "jose eustacio rivera" , 350 ));
    inventario.add(new Libro("L-001", "cien años de soledad", "gabriel garcia marquez", 496));
    inventario.add(new Revista("R-502", "national geographic", 2025));


    System.out.println("SISTEMA DE GESTION BIBLIOTECARIA ELKIN ANAYA");
    System.out.println("listado de recursos actuales:\n");


    for (RecursoDigital r : inventario) {
        r.mostrarDetalles();

    }

    System.out.println("\n---desmostracion de sobrecarga de metodos---");
    buscarRecurso("la Voragine");
    buscarRecurso(001);




    }
    
    
}


public abstract class RecursoDigital {
    protected String idUnico ;
    protected String titulo;
    public String id;

    public RecursoDigital(String id, String titulo) {
        this.idUnico = id;
        this.titulo = titulo;
        
    }
    public abstract void mostrarDetalles();
    protected abstract void emitirFicha();


}

public class Revista extends RecursoDigital {
    private int edicion;

    public Revista(String id, String titulo, int edicion) {
        super(id, titulo);
        this.edicion = edicion;

    }

    @Override
    public void mostrarDetalles() {
        System.out.println("[TIPO: Revista]");
        System.out.println("ID: " + idUnico + " | Titulo: " + titulo);
        System.out.println("Edicion N°: " + edicion);
        System.out.println("---------------------------------------");
        
    }

    public void setEdicion(int edicion) {
        this.edicion = edicion;
    }

    @Override
    public void emitirFicha() {
            @SuppressWarnings("unused")
            String String = (" Revista  'emitirficha'");
    }

}

public class  Libro extends RecursoDigital {
    private String autor;
    private int numpaginas;

    public Libro(String id, String titulo, String autor, int numpaginas) {
        super(id, titulo);
        this.autor = autor;
        this.numpaginas = numpaginas;
    }

    @Override
    public void emitirFicha() {
        System.out.println("[TIPO: Libro]");
        System.out.println(" ID: " + idUnico + " | Titulo: " + titulo);
        System.out.println("Autor: " + autor + " | paginas: " + numpaginas);
        System.out.println("--------------------------------------------");
        

    }



    @Override
    public void mostrarDetalles(){
        
    }
}
// Clase Persona
public class Persona {
    private String nombre;
    private int edad;

    // Constructor
    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    // Métodos públicos
    public String getNombre() {
        return nombre;
    }

    public int getEdad() {
        return edad;
    }

    public void mostrarInfo() {
        System.out.println("Nombre: " + nombre + ", Edad: " + edad);
    }
}

// Clase CuentaBancaria
public class CuentaBancaria {
    private double saldo;
    private Persona titular;

    // Constructor
    public CuentaBancaria(Persona titular, double saldoInicial) {
        this.titular = titular;
        this.saldo = saldoInicial;
    }

    // Métodos
    public void depositar(double monto) {
        saldo += monto;
    }

    public boolean retirar(double monto) {
        if (monto <= saldo) {
            saldo -= monto;
            return true;
        }
        return false;
    }

    public double consultarSaldo() {
        return saldo;
    }
}

public class Main {
    public static void main(String[] args) {
        Persona p1 = new Persona("Ana", 25);
        CuentaBancaria cuenta = new CuentaBancaria(p1, 1000);

        p1.mostrarInfo();
        cuenta.depositar(500);
        cuenta.retirar(200);

        System.out.println("Saldo actual: " + cuenta.consultarSaldo());
    }
}



