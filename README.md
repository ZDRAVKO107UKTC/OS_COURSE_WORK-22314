# Курсовa работа по Операционни системи
## Командният интерфейс на Linux (Kali Linux)

**Ученик:** Здравко Анев  
**Преподавател:** Памела Николова  
**Дата:** 02.01.2026  
**Дистрибуция:** Kali Linux (Debian-based)

---

## Съдържание
1. Описание на Linux  
2. Linux дистрибуции  
3. Kali Linux  
4. ЗАДАЧА 1 – Файлове и директории  
5. ЗАДАЧА 2 – Разширено създаване на структура  
6. ЗАДАЧА 3 – Копиране и преместване  
7. ЗАДАЧА 4 – Потребители, групи и права  
8. ЗАДАЧА 5 – Обработка на текст  
9. ЗАДАЧА 6 – Търсене на файлове  
10. ЗАДАЧА 7 – Регулярни изрази  
11. ЗАДАЧА 8 – Управление на процеси  
12. ЗАДАЧА 9 – Пакетни мениджъри  
13. ЗАДАЧА 10 – Архиви  

---

## 1. Операционна система Linux

Linux е свободна и отворена операционна система, създадена през 1991 г. от Линус Торвалдс.
Тя използва Unix архитектура и е широко използвана при сървъри, вградени системи и
киберсигурност.

**Основни характеристики:**
- Многопотребителска система
- Стабилност и сигурност
- Разширена система за права
- Поддръжка на множество файлови системи

---

## 2. Linux дистрибуции

Linux се разпространява чрез дистрибуции, които включват:
- Linux ядро
- Пакетен мениджър
- Системни библиотеки
- Приложения

**Примери:** Ubuntu, Debian, Arch Linux, CentOS, Kali Linux

---

## 3. Kali Linux

Kali Linux е дистрибуция, предназначена за:
- Penetration testing
- Анализ на уязвимости
- Етично хакерство
- Дигитална криминалистика

---

# ЗАДАЧА 1 – Създаване на файлове и директории

**Цел:** Създаване на зададена структура в домашната директория.

```bash
cd ~
mkdir -p OS_COURSE_WORK/{Documents,Images,TextFiles}
touch OS_COURSE_WORK/TextFiles/{notes1.txt,notes2.txt}
tree OS_COURSE_WORK
rm -r Iasi   # при нечетен номер
```

---

# ЗАДАЧА 2 – Създаване с mkdir и {}

```bash
mkdir -p ProjectFiles/{Archives,Documents,Images,Spreadsheets}
touch ProjectFiles/Documents/report{1..3}.docx
touch ProjectFiles/Images/{chart.png,logo.png}
tree ProjectFiles
rm -r Spreadsheets   # при нечетен номер
```

---

# ЗАДАЧА 3 – Копиране и преместване

```bash
cp MAIN_DIR/*/*.txt MAIN_DIR/FOLDER3/
mv MAIN_DIR/*/*.pdf MAIN_DIR/FOLDER1/
mv MAIN_DIR/*/strypes* MAIN_DIR/FOLDER2/
cp MAIN_DIR/*/*.docx MAIN_DIR/FOLDER4/
rm MAIN_DIR/FOLDER3/*.???
mv MAIN_DIR/FOLDER1 MAIN_DIR/.FOLDER1
```

**Обяснение:**
- `*` – wildcard
- `???` – точно три символа

---

# ЗАДАЧА 4 – Потребители, групи и права

```bash
sudo groupadd devops
sudo groupadd support
sudo useradd -m developer
sudo usermod -aG devops,support developer
cp /etc/group ~/
chmod u=rwx,g=rx,o=--- ~/group
chmod 750 ~/group
sudo chown developer:devops ~/group
ls -l ~/group
id developer
```

---

# ЗАДАЧА 5 – Обработка на текст

**Файл:** fruits.info  
**Формат:** ПЛОД;КОЛИЧЕСТВО;ЦЕНА

```bash
cut -d';' -f1 fruits.info | sort
sort -t';' -k2,2n fruits.info
sort -t';' -k3,3n fruits.info | tail -n 1 | cut -d';' -f1 > expensive_fruit
sort -t';' -k3,3n fruits.info | head -n 3
```

---

# ЗАДАЧА 6 – Търсене на файлове

```bash
find ~ -type d -iname '*dir*' | wc -l
find ~ -type f -name '*.conf' | wc -l
find ~ -type f -name '*.pdf' -printf '%s %p\n' | sort -n | tail -1
find ~ -type f -iname '*notes*.txt' | wc -l
find ~ -type f -name '*.html' -mtime -7
find ~ -type f -regextype posix-extended -regex '.*\.[^./]{3}$'
```

---

# ЗАДАЧА 7 – Регулярни изрази

```bash
grep -E '^p.*s$' /usr/share/dict/words | wc -l
grep -E '^[a-z]{7}$' /usr/share/dict/words | wc -l
grep -Ev '^[a-z]{7}$' /usr/share/dict/words | wc -l
grep -Ev '^[dt]' /usr/share/dict/words | wc -l
grep -E '^[A-Z].*[-\'']' /usr/share/dict/words > filtered_list
```

---

# ЗАДАЧА 8 – Управление на процеси

```bash
sleep 100 &
sleep 150 &
sleep 200 &
sleep 250 &
jobs -l
fg %2
nice -n 10 xterm &
renice -n 2 -p $(pgrep -n xterm)
sudo nice -n -6 xeyes
ps -eo pid,comm,%mem,rss --sort=-rss | head -n 6
sudo shutdown -h now
```

---

# ЗАДАЧА 9 – Пакетни мениджъри

```bash
sudo apt update
sudo apt install geany
geany &
sudo apt remove geany
sudo apt autoremove
```

---

# ЗАДАЧА 10 – Работа с архиви

```bash
tar -cf home_backup.tar ~
mkdir restore
tar -xf home_backup.tar -C restore
tar -cf scripts_backup.tar *.sh
tar -tvf home_backup.tar
tar -tf home_backup.tar | grep config
```

---

**Краен резултат:**  
Документът покрива всички задачи с точни команди и кратки обяснения,
подходящ за предаване и GitHub.
