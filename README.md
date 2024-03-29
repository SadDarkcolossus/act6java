public class Participante {
    private String nombre;
    private int[] calificaciones = new int[5];

    // Constructor
    public Participante(String nombre, int[] calificaciones) {
        this.nombre = nombre;
        this.calificaciones = calificaciones;
    }

    // Método para calcular el promedio de las calificaciones
    public double calcularPromedio() {
        double suma = 0;
        for (int calificacion : calificaciones) {
            suma += calificacion;
        }
        return suma / calificaciones.length;
    }

    // Método para obtener la calificación final del participante
    public char obtenerCalificacionFinal(double promedio) {
        if (promedio <= 50) {
            return 'F';
        } else if (promedio <= 60) {
            return 'E';
        } else if (promedio <= 70) {
            return 'D';
        } else if (promedio <= 80) {
            return 'C';
        } else if (promedio <= 90) {
            return 'B';
        } else {
            return 'A';
        }
    }

    // Método para imprimir los resultados del programa
    public void imprimirResultados() {
        System.out.println("Nombre del estudiante: " + nombre);
        for (int i = 0; i < calificaciones.length; i++) {
            System.out.println("Calificación " + (i + 1) + ": " + calificaciones[i]);
        }
        double promedio = calcularPromedio();
        System.out.println("Promedio: " + promedio);
        char calificacionFinal = obtenerCalificacionFinal(promedio);
        System.out.println("Calificación: " + calificacionFinal);
    }

    public static void main(String[] args) {
        int[] calificaciones = {75, 82, 67, 90, 88};
        Participante participante = new Participante("Juan", calificaciones);
        participante.imprimirResultados();
    }
}
