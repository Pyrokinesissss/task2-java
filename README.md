import java.util.Array;
import java.util.Scanner;

public class main {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        System.out.println("Массив:");
        System.out.println(numbers[0] + ", " + numbers[1] + ", " + numbers[2] + ", " + numbers[3] + ", " + numbers[4]);

        Scanner scanner = new Scanner(System.in);

        System.out.print("Выбор: (1 добавить, 2 удалить): ");
        int choice = scanner.nextInt();
        if (choice != 1 && choice != 2) {
            System.out.println("Неверный выбор. Введите 1 или 2");
        }
        else if (choice == 1) {
            System.out.print("Введите число для добавления: ");
            int newNum = scanner.nextInt();
            int[] newNumbers = new int[6];
            newNumbers[0] = numbers[0];
            newNumbers[1] = numbers[1];
            newNumbers[2] = numbers[2];
            newNumbers[3] = numbers[3];
            newNumbers[4] = numbers[4];
            newNumbers[5] = newNum;
            System.out.println(newNumbers[0] + ", " + newNumbers[1] + ", " + newNumbers[2] + ", " + newNumbers[3] + ", " + newNumbers[4] + ", " + newNumbers[5]);
        }
        else {
            System.out.print("Введите индекс от 0 до 4 для удаления: ");
            int index = scanner.nextInt();
            if (index < 0 || index > 4) {
                System.out.println("Ошибка");
            } else {
                System.out.println("Новый массив после удаления:");

                for (int i = 0; i < 5; i++) {
                    if (i != index) {
                        System.out.print(numbers[i] + " ");
                    }
                }
            }
        }

        scanner.close();
    }
}


import java.util.Random;
import java.util.Scanner


public class dasd {
    public static void main(String[] args) {
        Random random = new Random();
        Scanner scanner = new Scanner(System.in);


        int secretNumber = random.nextInt(100) + 1;

        int maxAttempts = 10;
        int attempts = 0;

        System.out.println("Я загадал число от 1 до 100. Попробуй угадать его за 10 попыток!");

        while (attempts < maxAttempts) {
            System.out.print("Введите ваше предположение: ");

            int guess = scanner.nextInt();
            attempts++;


            if (guess < 1 || guess > 100) {
                System.out.println("Ошибка: число должно быть в диапазоне от 1 до 100");
                attempts--;
                continue;
            }

            if (guess < secretNumber) {
                System.out.println("Моё число больше");
            } else if (guess > secretNumber) {
                System.out.println("Моё число меньше");
            } else {
                System.out.println("Поздравляю! Вы угадали!");
                System.out.println("Вы угадали за " + attempts + " попыток");
                scanner.close();
                return; // завершаем программу при победе
            }
        }


        System.out.println("Вы исчерпали все попытки. Загаданное число было " + secretNumber);
        scanner.close();
    }
}
