# Vetor-III-em-Java-Desafio-Dio-Everis Bootcamp

 * Resolvendo Desafios em Java - 1/3 - Preenchimento de Vetor III
 * Leia um valor X. Coloque este valor na primeira posição de um vetor N[100]. Em cada posição subsequente
 * de N (1 até 99), coloque a metade do valor armazenado na posição anterior, conforme o exemplo abaixo.
 * Imprima o vetor N.
 *
 * ENTRADA:
 * A entrada contem um valor de dupla precisão com 4 casas decimais.
 *
 * SAÍDA:
 * Para cada posição do vetor N, escreva "N[i] = Y", onde i é a posição do vetor e Y é o
 * valor armazenado naquela posição. Cada valor do vetor deve ser apresentado com 4 casas decimais.
 *
 * Exemplo de Entrada       Exemplo de Saída
 * 200.0000                 N[0] = 200.0000
 *                          N[1] = 100.0000
 *                          N[2] = 50.0000
 *                          N[3] = 25.000
 *                          N[4] = 12.5000


import java.io.IOException;
import java.math.BigDecimal;
import java.text.DecimalFormat;
import java.util.Locale;
import java.util.Scanner;

public class PreenchimentoDeVetorIII {
    public static void main(String[] args) throws IOException {
        Locale.setDefault(Locale.US);
        Scanner leitor = new Scanner(System.in);
        double X = leitor.nextDouble();
        BigDecimal[] N = new BigDecimal[100];
        N[0] = new BigDecimal(X);

        for(int i = 1; i < N.length; i++){
            N[i] = N[i - 1].divide(new BigDecimal("2.00"));
        }

        for(int i = 0; i < N.length; i++){
            System.out.println("N[" + i + "] = " + new DecimalFormat("0.0000").format(N[i]));
        }
        leitor.close();
    }
}

