import java.util.Scanner;
import java.util.Random;
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */

/**
 *
 * @author Claudia Vivar
 */
public class Practica1 {
    public class SistemaDeEstacionamiento {
        //CONSTANTES
        static final double Tarifa=10.0;
        static final int Tablero=10; // (10x10)
        static final int Maxvehiculos=64; // (8x8)
        
        //Datos Estacionamiento 
        static char[][] Tablero=new char[TABLERO][TABLERO];
        
        static int Entradafila, Entradacolum;
        static int Salidafila, Salidacolum;
        
        //RECORRIDO (Perimetro) 36 posiciones
        
        static int[]periFilas=new int[36];
        static int[]periColums=new int[36];
        
        //Vehiculos 
        
        
        
        
        //Ingresos
        static int vehiculosCobrados=0;
        static double totalCobrado=0.0;
        
        static Scanner sc=new Scanner(System.in);
        
        
        //Main
        public static void main(String[]args){
            InicioTablero();
            GenerarPerimetro();
            GenerarEntradaSalida();
            
            int opcion;
            do {
                mostrarMenu();
                opcion=leerEntero("Ingrese una opción: ");
                switch (opcion){
                    case 1: ingreseVehiculo(); 
                    break;
                    case 2: retirarVehiculo();
                    break;
                    case 3: mostrarEstacionamiento();
                    break;
                    case 4: buscarVehiculoPlaca();
                    break;
                    case 5: mostarRutasCortas();
                    break;
                    case 6: mostrarIngresos();
                    break;
                    case 7: System.out.println("Saliendo del sistema...");
                    break;
                    default: System.out.println("Opcion no válida.");
                    break;
                }
            } while (opcion !=7);
        }
        
        
        //MENÚ
        static void mostrarMenu(){
            System.out.println("\n ---SISTEMA DE ESTACIONAMIENTO---");
            System.out.println("1. Ingresar Vehiculos");
            System.out.println("2. Retirar Vehiculos");
            System.out.println("3. Mostrar Estacionamientos");
            System.out.println("4. Buscar Vehiculos por Placa");
            System.out.println("5. Mostrar ruta mas corta entre entrada y salida");
            System.out.println("6. Mostrar Ingresos");
            System.out.println("7. Salir");
        }
        
        
        //Inicio de programa
        
        
        static void InicioTablero(){
            for(int i=0; i<tamTablero; i++){
                for(int j=0; j<tamTablero; j++){
                    if (i==0 || i==tamTablero-1 || j==0 || j==tamTablero-1){
                        tablero[i][j]='=';
                    }else {
                        tablero[i][j]='L';
                    }
                }
            }
        }
        
        
        //Guardar las 36 celdas Exterior 
        static void GenerarPerimetro() {
            int idx=0;
            
            //Fila superior izqueirda a derecha
            for (int j=0; j<tamTablero; j++){
                periFilas[idx]=0; periColums[idx]=j; idx++;
            }
            
            
            //Columna derecha arriba para abajo 
            for (int i=1; i<tamTablero; i++){
                periFilas[idx]=i; periColums[idx]=tamTablero-1; idx++;
        }
        
        
    }
}

