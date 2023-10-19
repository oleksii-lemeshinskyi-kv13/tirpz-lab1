## Національний технічний університет України<br>“Київський політехнічний інститут ім. Ігоря Сікорського”

## Факультет прикладної математики<br>Кафедра системного програмування і спеціалізованих комп’ютерних систем


# Лабораторна робота №1<br>"Базова робота з git"

## КВ-13 Лемешинський Олексій

## Хід виконання роботи

### 1. Зклонувати будь-який невеликий проєкт open-source з github

Для виконання цього завдання було клоновано репозиторій проєкту "OpenRGB" з GitLab за допомогою команди:

```
$ git clone https://gitlab.com/CalcProgrammer1/OpenRGB.git
Cloning into 'OpenRGB'...
remote: Enumerating objects: 29295, done.
remote: Counting objects: 100% (869/869), done.
remote: Compressing objects: 100% (236/236), done.
remote: Total 29295 (delta 644), reused 814 (delta 618), pack-reused 28426
Receiving objects: 100% (29295/29295), 36.01 MiB | 23.00 MiB/s, done.
Resolving deltas: 100% (21719/21719), done.
Updating files: 100% (2826/2826), done.
```

### 2. Зробити не менше трьох локальних комітів

Створено файл 1.txt та зроблено перший коміт:

```
$ git add 1.txt
$ git commit -m "Додано файл 1.txt"
[master 892db637] Додано файл 1.txt
 1 file changed, 1 insertion(+)
 create mode 100644 1.txt
```

Створено файл 2.txt та зроблено другий коміт:

```
$ git add 2.txt
$ git commit -m "Додано файл 2.txt"
[master 4b0a162c] Додано файл 2.txt
 1 file changed, 1 insertion(+)
 create mode 100644 2.txt
```

Створено файл 3.txt та зроблено третій коміт:

```
$ git add 3.txt
$ git commit -m "Додано файл 3.txt"
[master d7675d37] Додано файл 3.txt
 1 file changed, 1 insertion(+)
 create mode 100644 3.txt
```

### 3. Продемонструвати уміння вносити зміни до останнього коміту за допомогою опції --amend.

Для внесення змін до останнього коміту за допомогою опції --amend були виконані наступні дії:

Внесено зміни в файл 1.txt

```
$ nano 1.txt
$ git add 1.txt
$ git commit --amend -m "Оновлено файл 1.txt"
[master bb33e25a] Оновлено файл 1.txt
 Date: Thu Oct 19 11:57:47 2023 +0300
 2 files changed, 2 insertions(+), 1 deletion(-)
 create mode 100644 3.txt
```

### 4. Продемонструвати уміння об'єднати кілька останніх комітів в один за допомогою git reset.

Для об'єднання кількох останніх комітів в один за допомогою git reset були виконані наступні дії:

Виконано git reset для об'єднання останніх двох комітів.

```
$ git reset HEAD~2
Unstaged changes after reset:
M    1.txt
```

Внесено зміни у виправленому коміті за допомогою --amend

```
$ nano 1.txt
$ git add 1.txt
$ git commit --amend -m "Оновлено файл 1.txt і об'єднано коміти"
[master d99f6a03] Оновлено файл 1.txt і об'єднано коміти
 Date: Thu Oct 19 11:53:16 2023 +0300
 1 file changed, 1 insertion(+)
 create mode 100644 1.txt
```

### 5. Видалити файл(и) одним способом на вибір.

Видалено файл 2.txt з репозиторію та з коміту за допомогою git rm.

```
$ git rm 2.txt
$ git commit -m "Видалено файл 2.txt"
[master 2ud93uw8] Видалено файл 2.txt
 1 file changed, 0 insertions(+), 1 deletion(-)
 delete mode 100644 2.txt
```

### 6. Перемістити файл(и) одним способом на вибір.

Переміщено файл 1.txt в новий каталог new_folder.

```
$ mkdir new_folder
$ git mv 1.txt new_folder/
$ git commit -m "Переміщено файл 1.txt в new_folder"
[master b217d667] Переміщено файл 1.txt в new_folder
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename 1.txt => new_folder/1.txt (100%)
```

### 7. Гілкування:

Для гілкування були створені три гілки з унікальними комітами.

Створено гілку feature_branch1 та зроблено коміт у цій гілці.

```
$ git checkout -b feature_branch1
Switched to a new branch 'feature_branch1'
$ echo "Зміна в гілці feature_branch1" > feature_file1.txt
$ git add feature_file1.txt
$ git commit -m "Коміт в гілці feature_branch1"
[feature_branch1 dca8c7de] Коміт в гілці feature_branch1
 1 file changed, 1 insertion(+)
 create mode 100644 feature_file1.txt
```

Створено гілку feature_branch2 та зроблено коміт у цій гілці

```
$ git checkout -b feature_branch2
Switched to a new branch 'feature_branch2'
$ echo "Зміна в гілці feature_branch2" > feature_file2.txt
$ git add feature_file2.txt
$ git commit -m "Коміт в гілці feature_branch2"
[feature_branch2 99f71562] Коміт в гілці feature_branch2
 1 file changed, 1 insertion(+)
 create mode 100644 feature_file2.txt
```

Створено гілку feature_branch3 та зроблено коміт у цій гілці

```
$ git checkout -b feature_branch3
Switched to a new branch 'feature_branch3'
$ echo "Зміна в гілці feature_branch3" > feature_file3.txt
$ git add feature_file3.txt
$ git commit -m "Коміт в гілці feature_branch3"
[feature_branch3 8d3a888c] Коміт в гілці feature_branch3
 1 file changed, 1 insertion(+)
 create mode 100644 feature_file3.txt
```

### 8. Продемонструвати уміння знайти в історії комітів набір комітів, в яких була зміна по конкретному шаблону в конкретному файлі.

Для пошуку комітів, в яких внесена конкретна зміна в файл 1.txt, ми використаємо комбінацію команд git log та git diff

```
$ git log -G 'new text' new_folder/1.txt            
commit b217d667c58581c2bad6ddd53f2742fe534f1e35 (HEAD -> master)
Author: Test Name <test@example.com>
Date:   Thu Oct 19 12:09:59 2023 +0300

    Переміщено файл 1.txt в new_folder
$ git show b217d667c58581c2bad6ddd53f2742fe534f1e35 new_folder/1.txt 
commit b217d667c58581c2bad6ddd53f2742fe534f1e35 (HEAD -> master)
Author: Test Name <test@example.com>
Date:   Thu Oct 19 12:09:59 2023 +0300

    Переміщено файл 1.txt в new_folder

diff --git a/new_folder/1.txt b/new_folder/1.txt
new file mode 100644
index 00000000..0d69f1dd
--- /dev/null
+++ b/new_folder/1.txt
@@ -0,0 +1 @@
+new text in file 1
```
