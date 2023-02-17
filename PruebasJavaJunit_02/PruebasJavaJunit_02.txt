package mx.generation;

import java.util.Scanner;

public class PruebasJavaJunit_02 {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

    System.out.print("Introduzca una palabra: ");
    String palabra = scanner.nextLine();

    boolean esCasiPalindromo = false;

    for (int i = 0; i < palabra.length(); i++) {
      StringBuilder palabraCambiada = new StringBuilder(palabra);
      char letraOriginal = palabra.charAt(i);
      for (char letra = 'a'; letra <= 'z'; letra++) {
        if (letra != letraOriginal) {
          palabraCambiada.setCharAt(i, letra);
          if (esPalindromo(palabraCambiada.toString())) {
            esCasiPalindromo = true;
            break;
          }
        }
      }
      if (esCasiPalindromo) {
        break;
      }
    }

    if (esCasiPalindromo) {
      System.out.println("La palabra es casi un palíndromo.");
    } else {
      System.out.println("La palabra no es casi un palíndromo.");
    }
  }

  public static boolean esPalindromo(String palabra) {
    String palabraInvertida = new StringBuilder(palabra).reverse().toString();
    return palabra.equalsIgnoreCase(palabraInvertida);
  }
}
