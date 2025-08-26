.. Java Programming documentation master file, created by
   sphinx-quickstart on Mon Aug 25 19:14:28 2025.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.


Программирование на языке Java
===========================================


.. contents::
   :local:
   :depth: 2

1. Обязательные данные
----------------------


+--------------------------+-------------------------------------------------------------+
| **Часы**                 | 84                                                          |
+--------------------------+-------------------------------------------------------------+
| **Язык**                 | русский                                                     |
+--------------------------+-------------------------------------------------------------+
| **Кредиты**              | 4                                                           |
+--------------------------+-------------------------------------------------------------+
| **Преподаватель**        | Лейкин Максим Валентинович                                  |
+--------------------------+-------------------------------------------------------------+
| **Где читается**         | ФИМКН (Нижний Новгород)                                     |
+--------------------------+-------------------------------------------------------------+
| **Направление**          | 09.03.04. Программная инженерия                             |
+--------------------------+-------------------------------------------------------------+

2. Информация о преподавателе
-----------------------------

- **ФИО:** Лейкин Максим Валентинович  
- **Учёная степень:** Кандидат физико-математических наук

3. Промежуточная аттестация
----------------------------

2023/2024 учебный год 3 модуль
-------------------------------

*   **Форма контроля:** Практическая работа
*   **Вес в итоговой оценке:** 1

2023/2024 учебный год 4 модуль
-------------------------------

*   **Форма контроля:** Практическая работа + Экзамен
*   **Вес в итоговой оценке:** 0.6 (Практическая работа) + 0.4 (Экзамен)

4. Цель курса
------------------

Целями освоения данной дисциплины являются как закрепление теоретических знаний в области объектно-ориентированного программирования, так и получение практических навыков программирования на языке JAVA с использованием стандартных средств раз-работки.

5. Конспект лекций
------------------
Лекция 1. Введение в Java
==========================

1. История Java
---------------

- Создан в 1991 году командой Sun Microsystems (Джеймс Гослинг).
- Первоначальное название --- Oak, переименован в Java в 1995.
- Ключевой принцип: **"Write Once, Run Anywhere"** (WORA) благодаря JVM.

2. Особенности Java
-------------------

- **Переносимость**: Байт-код выполняется на любой платформе с JVM.
- **Объектная ориентированность**: Все сущности --- объекты (кроме примитивов).
- **Надежность**: Сборка мусора, строгая типизация, обработка исключений.
- **Многопоточность**: Встроенная поддержка через класс Thread.
- **Безопасность**: JVM ограничивает доступ к ресурсам.
- **Коллекции**: Стандартизированные структуры данных (List, Set, Map).
- **GUI**: Библиотеки AWT, Swing, JavaFX.

3. Инструменты разработки
-------------------------

- **JDK**: Включает компилятор (javac), JVM (java), утилиты (javadoc).
- **IDE**: IntelliJ IDEA, Eclipse, NetBeans.

4. Пример программы
-------------------

.. code-block:: java

   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Hello, World!");
       }
   }

Лекция 2. Синтаксис Java
========================

1. Лексические элементы
-----------------------

- **Комментарии**: //, /* */, /** */ (для документации).
- **Идентификаторы**: Начинаются с буквы, _, $; чувствительны к регистру.
- **Ключевые слова**: public, class, static, void и др.

2. Типы данных
--------------

- **Примитивные**: int, double, char, boolean и др.
- **Ссылочные**: Классы, массивы, интерфейсы.
- **Литералы**:
  - Целочисленные: 10, 0xFF, 0b1010.
  - Вещественные: 3.14, 1e-5.
  - Символьные: 'a', '\\n'.

3. Переменные и область видимости
---------------------------------

- Объявление: int x = 10;.
- Область действия: Блоки кода ({}), методы, классы.

4. Операции
-----------

- **Арифметические**: +, -, *, /, %.
- **Логические**: &&, ||, !.
- **Битовые**: &, |, ^, <<, >>, >>>.
- **Приоритет операций**: Умножение перед сложением, скобки изменяют порядок.

5. Управляющие конструкции
--------------------------

- **Условные**:

  .. code-block:: java

     if (x > 0) { ... } else { ... }

     switch (x) { case 1: ... break; default: ... }

- **Циклы**:

  .. code-block:: java

     for (int i = 0; i < 10; i++) { ... }

     while (x > 0) { ... }

     do { ... } while (x > 0);

6. Массивы
----------

- Объявление:

  .. code-block:: java

     int[] arr = new int[5];
     int[][] matrix = {{1, 2}, {3, 4}};

7. Преобразование типов
-----------------------

- **Автоматическое**: int → long.
- **Явное**: (int) 3.14.

Лекция 3. Классы и интерфейсы в Java
====================================

1. Основы классов
-----------------

- **Структура класса**:

  .. code-block:: java

     <modifier> class <ClassName> {
         [modifier] <type> <instanceVariable>;
         [modifier] <type> <method>(<arguments>) { ... }
     }

- **Пример класса**:

  .. code-block:: java

     class Point {
         int x, y;
         Point() { x=0; y=0; } // Конструктор
         int getX() { return x; } // Метод
     }

2. Создание объектов
--------------------

- **Ссылки и объекты**:

  .. code-block:: java

     Point p1 = new Point(); // Создание объекта
     Point p2 = p1; // p2 ссылается на p1

3. Перегрузка методов (Overloading)
-----------------------------------

- Методы с одинаковыми именами, но разными параметрами:

  .. code-block:: java

     void test() { ... }
     void test(int a) { ... }

4. Модификатор static
---------------------

- **Статические переменные и методы**:
  - Существуют в единственном экземпляре.
  - Обращение: ClassName.methodName().
- **Статические блоки**:

  .. code-block:: java

     static { ... } // Выполняется при загрузке класса

5. Ключевое слово this
----------------------

- Используется для:
  - Разрешения конфликтов имён (например, this.x = x).
  - Вызова одного конструктора из другого:

    .. code-block:: java

       Rectangle() { this(0, 0); }

6. Вложенные классы
-------------------

- **Статические вложенные классы**:
  - Не имеют доступа к нестатическим членам внешнего класса.
- **Нестатические (inner classes)**:
  - Существуют только в контексте объекта внешнего класса.

7. Наследование
---------------

- **Синтаксис**:

  .. code-block:: java

     class SubClass extends SuperClass { ... }

- **Конструкторы**:
  - Конструктор суперкласса вызывается первым (используется super()).
  - Пример:

    .. code-block:: java

       Point3D(int x, int y, int z) {
           super(x, y); // Вызов конструктора Point
           this.z = z;
       }

8. Абстрактные классы и методы
------------------------------

- **Абстрактный метод**:

  .. code-block:: java

     abstract void methodName();

- **Абстрактный класс**:

  .. code-block:: java

     abstract class ClassName { ... }

9. Интерфейсы
-------------

- **Определение**:

  .. code-block:: java

     interface InterfaceName {
         void method(); // Абстрактный метод
         default void defaultMethod() { ... } // Дефолтный метод
     }

- **Реализация**:

  .. code-block:: java

     class ClassName implements InterfaceName { ... }

10. Перечисления (enum)
-----------------------

- **Пример**:

  .. code-block:: java

     enum Season { WINTER, SPRING, SUMMER, AUTUMN }

- **Методы**:
  - values(): возвращает все элементы.
  - valueOf("WINTER"): возвращает элемент по имени.

11. Пакеты
----------

- **Объявление**:

  .. code-block:: java

     package pkg1.pkg2;

- **Импорт**:

  .. code-block:: java

     import pkg1.ClassName;

12. Модификаторы доступа
------------------------

- public: доступ везде.
- private: только внутри класса.
- protected: доступ в пакете и подклассах.
- <default>: доступ только в пакете.

13. Методы с переменным числом аргументов
-----------------------------------------

- **Синтаксис**:

  .. code-block:: java

     void methodName(int... args) { ... }

14. Final
---------

- final для переменных: неизменяемое значение.
- final для методов: запрет переопределения.
- final для классов: запрет наследования.

Лекция 4. Обработка исключений в Java
=====================================

1. Типы ошибок
--------------

- **Синтаксические**: Ловятся компилятором.
- **Логические**: Обнаруживаются при тестировании.
- **Времени выполнения**: Возникают при выполнении программы (например, деление на ноль).

2. Исключения
-------------

- Исключение --- это объект, описывающий ошибку во время выполнения.
- Может быть сгенерировано JVM или вручную (throw).

3. Блоки try-catch
------------------

- **Синтаксис**:

  .. code-block:: java

     try {
         // Код, который может вызвать исключение
     } catch (ExceptionType e) {
         // Обработка исключения
     } finally {
         // Код, выполняемый в любом случае
     }

- **Особенности**:
  - Управление не возвращается в try после catch.
  - catch-блоки обрабатываются сверху вниз (подклассы исключений должны быть раньше суперклассов).
  - finally выполняется всегда, даже если исключение не возникло.

4. Иерархия исключений
----------------------

- Error: Критические ошибки (например, OutOfMemoryError), обычно не обрабатываются.
- RuntimeException (unchecked): Не требуют обязательной обработки (например, NullPointerException).
- Exception (checked): Требуют обработки или объявления в throws (например, IOException).

5. Генерация исключений
-----------------------

- **Вручную**:

  .. code-block:: java

     throw new Exception("Описание ошибки");

- **Повторное выбрасывание**:

  .. code-block:: java

     catch (Exception e) {
         System.out.println("Ошибка");
         throw e; // Повторное выбрасывание
     }

6. Правило "Catch or Specify"
-----------------------------

- Для checked-исключений:
  - Либо обрабатывать в try-catch.
  - Либо объявлять в throws метода:

    .. code-block:: java

       void method() throws IOException { ... }

7. Try-with-resources
---------------------

- Автоматическое закрытие ресурсов (реализующих AutoCloseable):

  .. code-block:: java

     try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
         // Работа с ресурсом
     } catch (IOException e) {
         // Обработка исключения
     }

- Ресурсы закрываются в обратном порядке их создания.

8. Подавленные исключения
-------------------------

- Если исключения возникают и в try, и при закрытии ресурса, исключение из try выбрасывается, а остальные подавляются (доступны через getSuppressed()).

9. Пример пользовательского исключения
--------------------------------------

- Создание checked-исключения:

  .. code-block:: java

     class MyException extends Exception {
         MyException(String message) {
             super(message);
         }
     }

Лекция 5. Консольный ввод-вывод в Java
=======================================

1. Потоки ввода-вывода
----------------------

- **Байтовые потоки** (InputStream, OutputStream):
  - Работают с байтами (двоичные данные).
  - Примеры:
    - FileInputStream/FileOutputStream --- чтение/запись файлов.
    - ByteArrayInputStream/ByteArrayOutputStream --- работа с массивами байтов.
- **Символьные потоки** (Reader, Writer):
  - Работают с символами (текст в Unicode).
  - Примеры:
    - FileReader/FileWriter --- чтение/запись текстовых файлов.
    - InputStreamReader/OutputStreamWriter --- преобразуют байты в символы.

2. Примеры использования
------------------------

- **Чтение файла** (FileInputStream):

  .. code-block:: java

     try (InputStream in = new FileInputStream("file.txt")) {
         int data;
         while ((data = in.read()) != -1) {
             System.out.print((char) data);
         }
     } catch (IOException e) {
         e.printStackTrace();
     }

- **Запись в файл** (FileOutputStream):

  .. code-block:: java

     try (OutputStream out = new FileOutputStream("output.txt")) {
         out.write("Hello, Java!".getBytes());
     } catch (IOException e) {
         e.printStackTrace();
     }

3. Буферизованные потоки
------------------------

- Увеличивают производительность за счёт буферизации:
  - BufferedInputStream/BufferedOutputStream --- для байтов.
  - BufferedReader/BufferedWriter --- для символов.
- Пример (BufferedReader):

  .. code-block:: java

     try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
         String line;
         while ((line = br.readLine()) != null) {
             System.out.println(line);
         }
     } catch (IOException e) {
         e.printStackTrace();
     }

4. Класс Scanner
----------------

- Удобен для чтения ввода с консоли или файлов:

  .. code-block:: java

     Scanner sc = new Scanner(System.in);
     System.out.print("Введите число: ");
     int num = sc.nextInt();
     System.out.print("Введите строку: ");
     String str = sc.next();
     sc.close();

5. Класс File
-------------

- Представляет путь к файлу/директории:

  .. code-block:: java

     File file = new File("example.txt");
     System.out.println("Существует: " + file.exists());
     System.out.println("Размер: " + file.length() + " байт");

6. Сериализация объектов
------------------------

- **Сериализация** --- сохранение объекта в байтовый поток.
- **Десериализация** --- восстановление объекта из потока.
- **Интерфейс Serializable**:
  - Маркерный интерфейс (не содержит методов).
  - Пример:

    .. code-block:: java

       class Person implements Serializable {
           private String name;
           private transient int age; // Поле не будет сериализовано
       }

- **Сохранение объекта** (ObjectOutputStream):

  .. code-block:: java

     try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("person.ser"))) {
         out.writeObject(new Person("Alice", 30));
     } catch (IOException e) {
         e.printStackTrace();
     }

- **Восстановление объекта** (ObjectInputStream):

  .. code-block:: java

     try (ObjectInputStream in = new ObjectInputStream(new FileInputStream("person.ser"))) {
         Person p = (Person) in.readObject();
         System.out.println(p.getName());
     } catch (IOException | ClassNotFoundException e) {
         e.printStackTrace();
     }

7. Особенности сериализации
---------------------------

- transient --- исключает поле из сериализации.
- serialVersionUID --- контроль версий класса:

  .. code-block:: java

     private static final long serialVersionUID = 1L;

- **Кастомная сериализация**:
  - Переопределение writeObject и readObject.
  - Пример:

    .. code-block:: java

       private void writeObject(ObjectOutputStream out) throws IOException {
           out.defaultWriteObject();
       }

8. Производительность и советы
------------------------------

- **Буферизация** ускоряет ввод-вывод.
- **Закрытие потоков** --- используйте try-with-resources.
- **Сериализация**:
  - Избегайте сериализации больших объектов.
  - Закрывайте потоки после использования.

Лекция 6. Стандартная библиотека Java
=====================================

1. Класс Object
---------------

- **Методы**:
  - clone(): Создает копию объекта (требует Cloneable).
  - equals(): Сравнивает объекты (должен быть переопределён вместе с hashCode()).
  - hashCode(): Возвращает хэш-код объекта.
  - toString(): Возвращает строковое представление объекта.
  - finalize(): Не рекомендуется переопределять (устарел).
- **Пример equals() и hashCode()**:

  .. code-block:: java

     @Override
     public boolean equals(Object o) {
         if (o == this) return true;
         if (!(o instanceof PhoneNumber)) return false;
         PhoneNumber pn = (PhoneNumber) o;
         return pn.areaCode == areaCode && pn.exchange == exchange;
     }

     @Override
     public int hashCode() {
         int result = 17;
         result = 31 * result + areaCode;
         result = 31 * result + exchange;
         return result;
     }

2. Классы-оболочки
------------------

- **Примеры**: Integer, Double, Boolean.
- **Автоупаковка/распаковка**:

  .. code-block:: java

     Integer x = 12; // Автоупаковка
     int y = x; // Автораспаковка

3. Класс Math
-------------

- **Константы**: Math.PI, Math.E.
- **Методы**: sin(), cos(), pow(), sqrt().
- **Пример**:

  .. code-block:: java

     double result = Math.pow(2, 3); // 8.0

4. Класс String
---------------

- **Неизменяемость**: Строки нельзя изменить после создания.
- **Методы**:
  - length(), charAt(), substring(), indexOf().
  - equals(): Сравнение содержимого (не ==).
- **Пример**:

  .. code-block:: java

     String s = "Hello";
     System.out.println(s.substring(1, 3)); // "el"

5. StringBuilder и StringBuffer
-------------------------------

- **Изменяемые строки**:
  - StringBuilder: Быстрее, но не потокобезопасен.
  - StringBuffer: Потокобезопасен.
- **Пример**:

  .. code-block:: java

     StringBuilder sb = new StringBuilder();
     sb.append("Hello").append(" World");
     System.out.println(sb.toString()); // "Hello World"

6. Класс Random
---------------

- **Генерация случайных чисел**:

  .. code-block:: java

     Random rand = new Random();
     int num = rand.nextInt(100); // 0..99

7. Классы Runtime и System
--------------------------

- **Управление памятью и процессы**:

  .. code-block:: java

     Runtime rt = Runtime.getRuntime();
     System.out.println(rt.freeMemory()); // Свободная память

Лекция 7. Параметризация типов (Generics)
=========================================

1. Зачем нужны дженерики?
-------------------------

- **Безопасность типов**: Ошибки обнаруживаются на этапе компиляции.
- **Универсальность**: Обобщённые алгоритмы для разных типов.

2. Параметризованные классы
---------------------------

- **Пример**:

  .. code-block:: java

     public class Box<T> {
         private T content;
         public void put(T item) { this.content = item; }
         public T get() { return content; }
     }

- **Использование**:

  .. code-block:: java

     Box<Integer> intBox = new Box<>();
     intBox.put(10);
     int value = intBox.get();

3. Ограниченные типы
--------------------

- **Пример**:

  .. code-block:: java

     public <T extends Number> void inspect(T item) {
         System.out.println(item.doubleValue());
     }

4. Wildcards (подстановки)
--------------------------

- **Пример**:

  .. code-block:: java

     public void printList(List<? extends Number> list) {
         for (Number n : list) System.out.println(n);
     }

5. Очистка типов (Type Erasure)
-------------------------------

- **Особенности**:
  - Информация о типах удаляется после компиляции.
  - Нельзя создать массив дженериков (new T[10]).

6. Ограничения
--------------

- Нельзя параметризовать примитивы (Box<int>).
- Нельзя использовать instanceof с дженериками.

Лекция 8. Коллекции в Java
==========================

1. Интерфейсы коллекций
-----------------------

- Collection: Базовый интерфейс для всех коллекций.
- List: Упорядоченная коллекция с дубликатами (ArrayList, LinkedList).
- Set: Уникальные элементы (HashSet, TreeSet).
- Map: Пары "ключ-значение" (HashMap, TreeMap).
- Queue/Deque: Очереди (LinkedList, PriorityQueue).

2. Основные методы
------------------

- List:

  .. code-block:: java

     List<String> list = new ArrayList<>();
     list.add("A");
     list.get(0); // "A"

- Set:

  .. code-block:: java

     Set<Integer> set = new HashSet<>();
     set.add(1);
     set.contains(1); // true

- Map:

  .. code-block:: java

     Map<String, Integer> map = new HashMap<>();
     map.put("key", 10);
     int value = map.get("key"); // 10

3. Итерация по коллекциям
-------------------------

- **For-each**:

  .. code-block:: java

     for (String s : list) System.out.println(s);

- **Итератор**:

  .. code-block:: java

     Iterator<String> it = list.iterator();
     while (it.hasNext()) System.out.println(it.next());

4. Алгоритмы (Collections класс)
--------------------------------

- **Сортировка**:

  .. code-block:: java

     Collections.sort(list);

- **Поиск**:

  .. code-block:: java

     int index = Collections.binarySearch(list, "A");

- **Перемешивание**:

  .. code-block:: java

     Collections.shuffle(list);

5. Производительность
---------------------

- ArrayList: Быстрый доступ по индексу, медленные вставка/удаление.
- LinkedList: Быстрые вставка/удаление, медленный доступ по индексу.
- HashSet/HashMap: O(1) для основных операций.
- TreeSet/TreeMap: O(log n) для основных операций.

Лекция 9. Сетевое программирование в Java
=========================================

1. Основные понятия
-------------------

- **IP-адреса**: Уникальные числовые идентификаторы устройств в сети (например, 199.1.32.90).
- **DNS**: Система доменных имен, преобразующая имена (например, www.example.com) в IP-адреса.
- **Порты**: Логические каналы на одном хосте (от 0 до 65535). Примеры:
  - HTTP: 80
  - HTTPS: 443
  - FTP: 21.

2. Класс InetAddress
--------------------

- **Назначение**: Представление IP-адресов и работа с DNS.
- **Методы**:
  - getByName(String host): Возвращает InetAddress по имени хоста или IP-адресу.
  - getHostName(): Возвращает имя хоста.
  - getHostAddress(): Возвращает IP-адрес.
- **Пример**:

  .. code-block:: java

     InetAddress address = InetAddress.getByName("www.example.com");
     System.out.println("IP: " + address.getHostAddress());

3. Класс URL
------------

- **Назначение**: Работа с Uniform Resource Locators (URL).
- **Методы**:
  - openStream(): Открывает поток для чтения данных по URL.
  - getProtocol(), getHost(), getPort(): Разбор URL.
- **Пример**:

  .. code-block:: java

     URL url = new URL("http://example.com");
     try (BufferedReader reader = new BufferedReader(new InputStreamReader(url.openStream()))) {
         String line;
         while ((line = reader.readLine()) != null) {
             System.out.println(line);
         }
     }

4. Класс URLConnection
----------------------

- **Назначение**: Управление соединением с сервером (чтение/запись данных).
- **Методы**:
  - getInputStream(): Получение входного потока.
  - getOutputStream(): Получение выходного потока (для POST-запросов).
  - setDoOutput(true): Разрешение записи данных.
- **Пример (POST-запрос)**:

  .. code-block:: java

     URL url = new URL("http://example.com/api");
     URLConnection connection = url.openConnection();
     connection.setDoOutput(true);
     try (OutputStream os = connection.getOutputStream()) {
         os.write("data=example".getBytes());
     }

5. Класс HttpURLConnection
--------------------------

- **Назначение**: Расширенная работа с HTTP (поддержка методов GET, POST и др.).
- **Методы**:
  - setRequestMethod("GET/POST"): Установка метода запроса.
  - getResponseCode(): Получение HTTP-кода ответа (200, 404 и т.д.).
- **Пример**:

  .. code-block:: java

     HttpURLConnection httpConn = (HttpURLConnection) url.openConnection();
     httpConn.setRequestMethod("GET");
     int responseCode = httpConn.getResponseCode();
     System.out.println("Response Code: " + responseCode);

6. Протокол HTTP
----------------

- **Заголовки (Headers)**:
  - Content-Type: Тип данных (например, text/html).
  - Content-Length: Размер данных.
- **Методы**:
  - GET: Получение данных.
  - POST: Отправка данных.
- **Пример заголовков**:

  .. code-block:: text

     HTTP/1.1 200 OK
     Content-Type: text/html
     Content-Length: 1234

7. MIME-типы
------------

- **Назначение**: Определение формата данных (например, text/plain, image/jpeg).
- **Пример**:

  .. code-block:: java

     String mimeType = URLConnection.guessContentTypeFromName("file.jpg");
     System.out.println("MIME Type: " + mimeType); // "image/jpeg"

8. Примеры кода
---------------

- **Чтение данных с сервера**:

  .. code-block:: java

     URL url = new URL("http://example.com");
     try (BufferedReader reader = new BufferedReader(new InputStreamReader(url.openStream()))) {
         reader.lines().forEach(System.out::println);
     }

- **Отправка данных на сервер**:

  .. code-block:: java

     URL url = new URL("http://example.com/api");
     HttpURLConnection conn = (HttpURLConnection) url.openConnection();
     conn.setRequestMethod("POST");
     conn.setDoOutput(true);
     try (OutputStream os = conn.getOutputStream()) {
         os.write("param=value".getBytes());
     }

9. Обработка ошибок
-------------------

- **Исключения**:
  - MalformedURLException: Некорректный URL.
  - IOException: Ошибки ввода/вывода.
- **Пример**:

  .. code-block:: java

     try {
         URL url = new URL("http://invalid.url");
     } catch (MalformedURLException e) {
         System.err.println("Некорректный URL: " + e.getMessage());
     }

Лекция 10. Threads & Concurrency
================================

1. Процессы и потоки
--------------------

- Процесс имеет собственную среду исполнения и ресурсы.
- Потоки (threads) --- легковесные процессы, выполняются внутри процесса и разделяют его ресурсы.
- Каждое Java-приложение имеет минимум один поток (main thread).

2. Создание потоков
-------------------

- Два способа:
  - Наследование от класса Thread.
  - Реализация интерфейса Runnable (предпочтительнее).
- Запуск потока: метод start().

3. Управление потоками
----------------------

- Приостановка: Thread.sleep().
- Прерывание: interrupt(), проверка через Thread.interrupted().
- Связывание: join() для ожидания завершения потока.
- Приоритеты: setPriority(), MIN_PRIORITY, MAX_PRIORITY, NORM_PRIORITY.
- Потоки-демоны: setDaemon(true), завершаются при остановке всех обычных потоков.

4. Проблемы многопоточности
---------------------------

- Race Condition: конфликты при одновременном доступе к данным.
- Ошибки целостности памяти: несогласованность данных между потоками.
- Отношение "happens-before": гарантирует видимость изменений между потоками.

5. Синхронизация
----------------

- Мониторы объектов: synchronized методы и блоки.
- Реентерабельность: поток может повторно захватывать монитор.
- Атомарные операции: volatile переменные, классы AtomicInteger и др.

6. Тупики (deadlocks)
---------------------

- Возникают при взаимной блокировке потоков.
- Методы борьбы: упорядочение ресурсов, алгоритм банкира.

7. Wait-set методы
------------------

- wait(), notify(), notifyAll() для управления потоками.
- Вызываются только внутри synchronized блоков.

8. Пакет java.util.concurrent
-----------------------------

- Executors: управление пулами потоков (ThreadPoolExecutor).
- Concurrent Collections: потокобезопасные коллекции (ConcurrentHashMap, CopyOnWriteArrayList).
- Blocking Queues: очереди с блокировкой (ArrayBlockingQueue).
- Atomics: атомарные операции (AtomicInteger).
- Locks: альтернативы synchronized (ReentrantLock).
- Semaphores: управление доступом к ресурсам.

9. Интерфейс Callable
---------------------

- Аналог Runnable, но возвращает результат через Future.
- Позволяет отменять задачи (cancel()), проверять статус (isDone()).

Лекция 11. Lambdas & Streams
============================

1. Лямбда-выражения
-------------------

- Позволяют передавать функции как аргументы методов.
- Синтаксис: (параметры) -> { тело }.
- Пример:

  .. code-block:: java

     list.forEach(n -> System.out.println(n));

- Функциональные интерфейсы (например, Runnable, Comparator) --- интерфейсы с одним абстрактным методом.

2. Stream API
-------------

- Обработка данных в функциональном стиле.
- Этапы:
  - **Источник** (коллекция, массив).
  - **Промежуточные операции** (filter, map, sorted).
  - **Терминальные операции** (forEach, collect, reduce).
- Пример:

  .. code-block:: java

     int sum = list.stream().filter(x -> x % 2 == 0).mapToInt(x -> x).sum();

3. Ссылки на методы
-------------------

- Упрощение лямбд: System.out::println.

Лекция 12. Annotations
======================

1. Аннотации
------------

- Метаданные для компилятора, JVM или инструментов.
- Примеры встроенных аннотаций:
  - @Override --- проверка переопределения метода.
  - @Deprecated --- отметка устаревшего кода.
  - @SuppressWarnings --- подавление предупреждений.

2. Создание аннотаций
---------------------

- Пример:

  .. code-block:: java

     @interface Info {
         String author() default "Anonymous";
         int version();
     }

- Мета-аннотации:
  - @Retention --- политика жизни аннотации.
  - @Target --- область применения (класс, метод и т.д.).

3. Типовые аннотации (Java 8+)
-------------------------------

- Аннотации для типов: List<@NonNull String>.
- Повторяемые аннотации: @Schedule(day="Mon") @Schedule(day="Fri").

Лекция 13. RxJava
=================

1. Reactive Programming
-----------------------

- Работа с асинхронными потоками данных.
- Основные компоненты:
  - **Observable** --- источник данных.
  - **Observer** --- подписчик на данные.
  - **Операторы** (map, filter, flatMap).

2. Примеры
----------

- Создание Observable:

  .. code-block:: java

     Observable.just("Hello", "World").subscribe(System.out::println);

- Операторы:

  .. code-block:: java

     Observable.range(1, 10).filter(x -> x % 2 == 0).map(x -> x * x);

3. Schedulers
-------------

- Управление потоками:
  - Schedulers.io() --- для I/O операций.
  - Schedulers.computation() --- для вычислений.
- Методы: subscribeOn(), observeOn().

4. Особенности
--------------

- Ленивые вычисления (без подписки --- нет выполнения).
- Обработка ошибок: onError().

Лекция 14. Reflection API
=========================

1. Рефлексия
------------

- Механизм исследования и изменения структуры программы во время выполнения.
- Основные классы: ``Class``, ``Field``, ``Method``, ``Constructor`` из пакетов ``java.lang`` и ``java.lang.reflect``.

2. Основные возможности
-----------------------

- Получение информации о классе: модификаторы, поля, методы, конструкторы.
- Создание объектов динамически:

  .. code-block:: java

     Class<?> clazz = Class.forName("com.example.MyClass");
     Constructor<?> constructor = clazz.getConstructor(int.class, String.class);
     Object instance = constructor.newInstance(42, "test");

- Доступ к приватным полям и методам через ``setAccessible(true)``.

3. Примеры
----------

- Получение полей:

  .. code-block:: java

     Field[] fields = clazz.getDeclaredFields();

- Вызов метода:

  .. code-block:: java

     Method method = clazz.getMethod("setName", String.class);
     method.invoke(instance, "New Name");

4. Генерация и работа с массивами
---------------------------------

- Создание массива:

  .. code-block:: java

     int[] array = (int[]) Array.newInstance(int.class, 5);

5. Рефлексия и дженерики
------------------------

- Получение информации о параметризованных типах через ``ParameterizedType``.

Лекция 15. Шаблоны проектирования
=================================

1. Основные категории шаблонов
-------------------------------

- **Порождающие (Creational)**: Singleton, Builder, Factory.
- **Структурные (Structural)**: Decorator, Adapter, Facade.
- **Поведенческие (Behavioral)**: Observer, Strategy, Iterator.

2. Примеры шаблонов
-------------------

- **Singleton**: Гарантирует единственный экземпляр класса.

  .. code-block:: java

     public class Singleton {
         private static final Singleton INSTANCE = new Singleton();
         private Singleton() {}
         public static Singleton getInstance() { return INSTANCE; }
     }

- **Builder**: Упрощает создание сложных объектов.

  .. code-block:: java

     Person person = new PersonBuilder().name("Alice").age(30).build();

- **Decorator**: Динамически добавляет функциональность.

  .. code-block:: java

     Coffee coffee = new Milk(new SimpleCoffee());

3. MVC (Model-View-Controller)
------------------------------

- Разделение на компоненты:
  - **Модель (Model)**: Данные и логика.
  - **Вид (View)**: Отображение.
  - **Контроллер (Controller)**: Обработка ввода.

Лекция 16. JUnit Framework
==========================

1. Основы модульного тестирования
---------------------------------

- Написание тестов для проверки отдельных модулей кода.
- Аннотации: ``@Test``, ``@Before``, ``@After``, ``@BeforeClass``, ``@AfterClass``.

2. Пример теста
---------------

.. code-block:: java

   import org.junit.Test;
   import static org.junit.Assert.*;

   public class MathTest {
       @Test
       public void testAddition() {
           assertEquals(5, 2 + 3);
       }
   }

3. Фикстуры
-----------

- Общие настройки для тестов через методы ``@Before`` и ``@After``.

4. Расширенные возможности
--------------------------

- **Игнорирование тестов**: ``@Ignore``.
- **Проверка исключений**:

  .. code-block:: java

     @Test(expected = ArithmeticException.class)
     public void testDivisionByZero() { int x = 1 / 0; }

- **Таймаут**: ``@Test(timeout = 1000)``.

5. JUnit 5
----------

- Новые аннотации: ``@BeforeEach``, ``@AfterAll``.
- Динамические тесты:

  .. code-block:: java

     @TestFactory
     Stream<DynamicTest> dynamicTests() { ... }
