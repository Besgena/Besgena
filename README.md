from random import *


def is_valid(j):
    if j.isdigit() and 1 <= int(j) <= 100:
        return True
    return False


def valid_s(m):
    if str(m).isdigit() and m >= 2:
        return True
    return False


def game():
    print('Поехали! Введите правую границу рандома')
    s = int(input('Правая граница >>> '))
    if valid_s(s):
        a = randint(1, s+1)
        c = 0
        while True:
            s = input('Число >>> ')
            c += 1
            if is_valid(s):
                s = int(s)
                if s > a:
                    print('Ваше число больше загаданного, попробуйте еще разок')
                elif s < a:
                    print('Ваше число меньше загаданного, попробуйте еще разок')
                else:
                    print('Вы угадали, поздравляем!')
                    break
            else:
                print('А может быть, все-таки введем целое число от 1 до 100?')
        print('Число попыток:', c)


print('Добро пожаловать в числовую угадайку')
game()

while True:
    print('Хотите сыграть ещё раз? Да = д, нет = н')
    n = input()
    if n == 'д':
        game()
    elif n == 'н':
        print('Спасибо, что играли в числовую угадайку. Еще увидимся...')
        break
    else:
        print('Может, всё же введём "д" или "н"?')
