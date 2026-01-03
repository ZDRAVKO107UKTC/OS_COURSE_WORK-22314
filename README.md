# Курсовa работа  
## Операционни системи  
### „Командният интерфейс на Linux“

**Ученик:** Здравко Анев  
**Преподавател:** Памела Николова  
**Дата:** 02.01.2026  
**Дистрибуция:** Kali Linux  

---

## 1. Операционна система Linux

Linux е свободна и отворена операционна система, разработена първоначално през 1991 г. от Линус Торвалдс. Тя се базира на Unix архитектура и се характеризира с висока стабилност, сигурност и гъвкавост.

### Основни характеристики
- Висока стабилност и надеждност  
- Отлична система за потребители и права  
- Поддръжка на многопотребителска и многозадачна работа  
- Широко използване при сървъри, облачни платформи и вградени системи  

---

## 2. Linux дистрибуции

Linux се разпространява под формата на дистрибуции, които включват:
- Linux ядро  
- Пакетен мениджър  
- Системни библиотеки  
- Графична среда и приложения  

Примери:
- Ubuntu – крайни потребители  
- Debian / CentOS – сървъри  
- Arch Linux – напреднали потребители  
- Kali Linux – киберсигурност  

---

## 3. Kali Linux – използвана дистрибуция

Kali Linux е специализирана дистрибуция за:
- Penetration testing  
- Етично хакерство  
- Анализ на уязвимости  
- Дигитална криминалистика  

---

# ЗАДАЧИ И КОМАНДИ

## ЗАДАЧА 1 – Създаване на файлове и директории
```bash
mkdir -p dir1/{subdir1,subdir2}
touch file1.txt file2.txt
tree
rm -r Iasi
cd ~
```

## ЗАДАЧА 3 – Копиране и преместване
```bash
cp MAIN_DIR/*/*.txt MAIN_DIR/FOLDER3/
mv MAIN_DIR/*/*.pdf MAIN_DIR/FOLDER1/
mv MAIN_DIR/*/strypes* MAIN_DIR/FOLDER2/
cp MAIN_DIR/*/*.docx MAIN_DIR/FOLDER4/
rm MAIN_DIR/FOLDER3/*.???
mv MAIN_DIR/FOLDER1 MAIN_DIR/.FOLDER1
```

## ЗАДАЧА 4 – Потребители и права
```bash
sudo groupadd devops
sudo groupadd support
sudo useradd -m developer
sudo usermod -aG devops,support developer
chmod 750 ~/group
sudo chown developer:devops ~/group
```

## ЗАДАЧА 5 – Текстова обработка
```bash
cut -d';' -f1 fruits.info | sort
sort -t';' -k2,2n fruits.info
sort -t';' -k3,3n fruits.info | tail -n 1 | cut -d';' -f1 > expensive_fruit
```

## ЗАДАЧА 6 – Търсене
```bash
find ~ -type d -iname '*dir*' | wc -l
find ~ -type f -name '*.conf' | wc -l
find ~ -type f -name '*.pdf' -printf '%s %p\n' | sort -n | tail -1
```

## ЗАДАЧА 7 – grep
```bash
grep -E '^p.*s$' /usr/share/dict/words | wc -l
grep -E '^[a-z]{7}$' /usr/share/dict/words | wc -l
```

## ЗАДАЧА 8 – Процеси
```bash
sleep 100 &
jobs -l
nice -n 10 xterm &
sudo shutdown -h now
```

## ЗАДАЧА 9 – Пакети
```bash
sudo apt update
sudo apt install geany
sudo apt remove geany
```

## ЗАДАЧА 10 – Архиви
```bash
tar -cf home_backup.tar ~
tar -tvf home_backup.tar
```
