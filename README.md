# Installing phpMyAdmin in OpenServer 6.0.0

This README file describes the process of installing and integrating **phpMyAdmin** into the **OpenServer 6.0.0** system.

## Step 1: Downloading and Placing phpMyAdmin

1. Download phpMyAdmin from the [official website](https://www.phpmyadmin.net/).
2. Place it in a convenient folder for you. In this example:
   ```
   {projects_search_path}/addons
   ```

   **Note:**
    - The `phpMyAdmin` folder should be located where your projects are stored by default.
    - You can check or change the `projects_search_path` parameter in the `OpenServer/config/program.ini` file.

## Step 2: Creating Configuration for phpMyAdmin

1. Inside the `addons` folder, create a folder called `.osp`.
2. In this folder, create a `project.ini` file and add the following code:

   ```ini
   [phpmyadmin]
   php_engine   = PHP-8.1
   public_dir   = D:\Deka\Projects\PHP\addons\phpmyadmin
   ```

    - **php\_engine**: The version of PHP you are using. In this example – `PHP-8.1`.
    - **public\_dir**: The path to the directory where your phpMyAdmin is located.

### Directory Hierarchy

```
addons/ (located in the projects directory)
  └── .osp/
      └── project.ini
  └── phpmyadmin/
```

## Step 3: Configuring OpenServer

In the `OpenServer/config` directory, there are two important configuration files:

- `menu.ini`
- `program.ini`

### Changes in `menu.ini`

Add the following block to `menu.ini`:

```ini
[phpMyAdmin]
caption    = phpMyAdmin
category   = {lang_addons}
command    = "%COMSPEC%" /c "start "" "https://phpmyadmin/""
hide       = on
icon       = database
hr_after   = on
```

- **[phpMyAdmin]** - A unique identifier that must not be repeated.
- **caption** - The name of the application. You can use translations from `OpenServer/system/lang`.
- **category** - The category to which the application belongs. In this example, `{lang_addons}` is used, but you can change or remove this parameter.
- **command** - The command to run phpMyAdmin.
- **hide** - This parameter hides the terminal when the page opens in the browser.
- **icon** - The application icon. Here, `database` is used. You can choose another one, such as `tools` or `sailboat`.
- **hr\_after** - Adds a horizontal line if the category is not specified.

### Changes in `program.ini`

In the `program.ini` file, the following parameters have been modified:

```ini
show_projects_in_groups  = on
show_projects_in_submenu = on
```

These parameters allow you to display projects in groups and in a submenu for easier navigation.

## Conclusion

After completing these steps, **phpMyAdmin** will be integrated into the **OpenServer 6.0.0** system, and you will be able to quickly launch it from a convenient menu. Make sure all parameters are configured correctly so that your application runs smoothly.

---

# Встановлення phpMyAdmin у OpenServer 6.0.0

Цей файл README описує процес встановлення та інтеграції **phpMyAdmin** у систему **OpenServer 6.0.0**.

## Крок 1: Завантаження та розміщення phpMyAdmin

1. Скачайте phpMyAdmin з [офіційного сайту](https://www.phpmyadmin.net/).
2. Помістіть його у зручну для вас папку. У прикладі це:
   ```
   {projects_search_path}/addons
   ```

   **Примітка:**
    - Папка `phpMyAdmin` має бути розміщена там, де за замовчуванням знаходяться ваші проєкти.
    - Ви можете перевірити або змінити значення параметра `projects_search_path` у файлі `OpenServer/config/program.ini`.

## Крок 2: Створення конфігурації для phpMyAdmin

1. Усередині папки `addons` створіть папку `.osp`.
2. У цій папці створіть файл `project.ini` та додайте в нього наступний код:

   ```ini
   [phpmyadmin]
   php_engine   = PHP-8.1
   public_dir   = D:\Deka\Projects\PHP\addons\phpmyadmin
   ```

    - **php\_engine**: Версія PHP, яку ви використовуєте. У цьому прикладі – `PHP-8.1`.
    - **public\_dir**: Шлях до директорії, де знаходиться ваш phpMyAdmin.

### Ієрархія директорій

```
addons/ (знаходиться в директорії проєктів)
  └── .osp/
      └── project.ini
  └── phpmyadmin/
```

## Крок 3: Конфігурація OpenServer

У директорії `OpenServer/config` є два важливих файли для конфігурації:

- `menu.ini`
- `program.ini`

### Зміни у `menu.ini`

Додайте наступний блок у `menu.ini`:

```ini
[phpMyAdmin]
caption    = phpMyAdmin
category   = {lang_addons}
command    = "%COMSPEC%" /c "start "" "https://phpmyadmin/""
hide       = on
icon       = database
hr_after   = on
```

- **[phpMyAdmin]** - унікальний ідентифікатор, який не повинен повторюватися з іншими.
- **caption** - назва додатку. Можна використовувати переклади з `OpenServer/system/lang`.
- **category** - категорія, до якої належить додаток. У цьому прикладі використовується `{lang_addons}`, але ви можете змінити або видалити цей параметр.
- **command** - команда для запуску phpMyAdmin.
- **hide** - параметр, що приховує відкриття терміналу при запуску сторінки у браузері.
- **icon** - іконка для додатку. Тут використовується `database`. Ви можете вибрати іншу, наприклад `tools` або `sailboat`.
- **hr\_after** - додає горизонтальну лінію, якщо категорія не вказана.

### Зміни у `program.ini`

У файлі `program.ini` змінено наступні параметри:

```ini
show_projects_in_groups  = on
show_projects_in_submenu = on
```

Ці параметри дозволяють показувати проєкти у групах та у підменю для зручнішої навігації.

## Висновок

Після виконання цих кроків **phpMyAdmin** буде інтегровано у систему **OpenServer 6.0.0**, і ви зможете швидко запускати його зі зручного меню. Переконайтеся, що всі параметри налаштовані правильно, щоб ваш додаток працював без проблем.

