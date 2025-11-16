# Домашнее задание к работе 10

## Условие задачи
Составьте программу, которая для заданной пользователем фигуры, например квадрата предлагает меню выбора одной из операций:
1) рассчитать площадь;
2) вывести определение фигуры;
3) нарисовать фигуру.

## 1. Алгоритм и блок-схема

### Алгоритм
1. **Начало**
- Установка кодировки UTF-8 для поддержки кириллицы
- Вывод заголовка программы
2. Главный цикл меню:
- Бесконечный цикл до выбора опции выхода.
3. Отображение меню.
4. Обработка выбора пользователя
Считать выбор пользователя
Если выбор = 0 → выход из программы

5. **Функции**

*area_square(a)*
	
- `Возвращает a × a`
  
*draw_square(size, symbol)*

- `Рисует квадрат: size строк × size столбцов символов`

*print_definition()*

- `Выводит текст о квадрате`

6. **Конец**

### Блок-схема 
<img width="3604" height="3284" alt="image" src="https://github.com/user-attachments/assets/03ae06f2-882b-4aa8-9801-6dfb73cb46a7" />


## 2. Реализация программы
#include <stdio.h>
#include <locale.h>

float area_square(float a) {
    return a * a;
}

void draw_square(int size, char symbol) {
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            printf("%c ", symbol);
        }
        printf("\n");
    }
}

void print_definition() {
    printf("\nКвадрат - это геометрическая фигура, правильный четырёхугольник, у которого все стороны равны и все углы прямые (90 градусов).\n");
}

int main() {
    int choice;
    float side;
    char symbol;
    setlocale(LC_ALL, "RUS");
    printf("Программа для работы с квадратом\n");

    while (1) {
        printf("\nМеню:\n");
        printf("1 - Площадь\n");
        printf("2 - Определение\n");
        printf("3 - Рисование\n");
        printf("0 - Выход\n");
        printf("Выберите: ");
        scanf("%d", &choice);

        if (choice == 0) break;

        switch (choice) {
        case 1:
            printf("Введите сторону: ");
            scanf("%f", &side);
            printf("Площадь: %.2f\n", area_square(side));
            break;

        case 2:
            print_definition();
            break;

        case 3:
            printf("Введите размер: ");
            scanf("%f", &side);
            printf("Введите символ: ");
            scanf(" %c", &symbol);
            draw_square((int)side, symbol);
            break;

        default:
            printf("Неверный выбор!\n");
        }
    }

    return 0;
}

## 3. Результаты работы программы

<img width="448" height="250" alt="image" src="https://github.com/user-attachments/assets/0f6ce57c-f3db-4efe-9c70-5f6e1936e89a" />


