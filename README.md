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


