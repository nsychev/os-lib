# Решение

Запуск

    make

Библиотеки:

* `libhello.a` — статическая библиотека с функцией `void print_hello();` для вывода `Hello, World!`
* `libbottles.so` — динамическая библиотека с функцией `void print_bottles();` для вывода текста 99 Bottles of Beer, подключается при линковке
* `libfile.so` — динамическая библиотека с функцией `void print_file(const std::string&);` для вывода содержимого файла, подключается в рантайме

Использование:

* `hello` — запуск функции `print_hello` из `libhello.a`
* `bottles` — запуск функции `print_bottles` из `libbottles.so`
* `file` — запуск функции `print_file` из `libfile.so` (библиотека подгружается и выгружается на каждый вызов)
* `help` — справка
* `exit` — выход

# Задание

##  Знакомство с библиотеками

Необходимо создать статическую, и две динамических библиотеки и программу, которая будет их использовать.
Помимо этого нужен Makefile(либо другой инструмент автоматизации сборки), с помощью которого можно будет собрать все части.

### Статическая библиотека должна:
 * Собираться статически
 * Предоставлять какие-то функции<

### Первая динамическая библиотека должна:
 * Собираться динамически
 * Динамически линковаться с программой на этапе линковки
 * Предоставлять какие-то функции

### Вторая динамическая библиотека должна:
 * Собираться динамически
 * Предоставлять какие-то функции

### Программа должна
 * Статически линковаться с статической библиотекой и вызывать предоставляемые ей функции
 * Динамически линковаться с первой динамической библиотекой и вызывать предоставляемые ей функции
 * Во время выполнения в явном виде загружать вторую динамическию библиотеку с помощью dlopen(3) и вызывать какие-то функции из нее

### Что может помочь при выполнении задания?
 * man dlopen(3), man ld(1), man gcc(1)
