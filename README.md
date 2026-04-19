# PPM Image Processor

## English version

A set of utilities for reading, saving, and performing basic operations on images in PPM (Portable Pixmap) format.

Supported format
- PPM (ASCII/Plain P3 or binary P6). The parser expects a header with the format type, width, height, and maximum color value (maxval), followed by the pixel data.
- Limitations: maxval is assumed to be ≤ 255 (byte representation of channels).

Architecture and modules
- Parser: reads the header, validates the fields, and loads the pixel array into memory.
- Serializer (saving): writes the header and pixel data to the specified format (P3/P6).
- Image operations: transformations (rotation, mirroring), color inversion, brightness/contrast changes, simple filtering.
- Tests/examples: a set of PPM files for verifying the correctness of operations.

Repository structure
- Sources and project:
- [Test_cpp_penyaz/Test_cpp_penyaz.vcxproj](Test_cpp_penyaz/Test_cpp_penyaz.vcxproj)
- [Test_cpp_penyaz/Test_cpp_penyaz.vcxproj.filters](Test_cpp_penyaz/Test_cpp_penyaz.vcxproj.filters)
- [Test_cpp_penyaz/test.cpp](Test_cpp_penyaz/test.cpp)
- Test PPM files:
- [Test_cpp_penyaz/test_color_changing.ppm](Test_cpp_penyaz/test_color_changing.ppm)
- [Test_cpp_penyaz/test_colors_inverting.ppm](Test_cpp_penyaz/test_colors_inverting.ppm) 
- [Test_cpp_penyaz/test_flip_over_180.ppm](Test_cpp_penyaz/test_flip_over_180.ppm) 
- [Test_cpp_penyaz/test_flip_over_90.ppm](Test_cpp_penyaz/test_flip_over_90.ppm) 
- [Test_cpp_penyaz/test_mirroring.ppm](Test_cpp_penyaz/test_mirroring.ppm) 
- [Test_cpp_penyaz/test_save.ppm](Test_cpp_penyaz/test_save.ppm)
- Root configuration files: 
- [.gitattributes](.gitattributes)
- [.gitignore](.gitignore)
- [Test_cpp_penyaz.sln](Test_cpp_penyaz.sln)
- [README.md](README.md)

Build and Run
- Open [Test_cpp_penyaz.sln](Test_cpp_penyaz.sln) in Visual Studio.
- Build the solution (Release/Debug).
- Run example: execute the binary from the project; the test `test.cpp` demonstrates parser/save calls and several image operations.

Usage Examples (Logic)
- Load: open file, read header, allocate buffer of width*height*3, fill with RGB bytes. - Change: Perform byte-by-byte/coordinate-by-coordinate operations on the buffer (e.g., channel swap, inversion: 255 - value).
- Save: Write the header and buffer in the selected format.

Testing
- Use the provided PPMs in the [Test_cpp_penyaz](Test_cpp_penyaz) folder for validation: visually and programmatically.
- Check the header for correctness and the buffer size (width * height * 3).

Limitations and Notes
- Intended for images that fit entirely in RAM.
- No support for color profiles or formats with a maxval > 255.
- If expansion is needed, add stream processing for large images and support for additional PNM types.

## Russian version

Набор утилит для чтения, сохранения и выполнения базовых операций над изображениями в формате PPM (Portable Pixmap).

Поддерживаемый формат
- PPM (ASCII/Plain P3 или бинарный P6). Парсер ожидает заголовок с типом формата, шириной, высотой и максимальным значением цвета (maxval), затем следуют данные пикселей.
- Ограничения: maxval предполагается ≤ 255 (байтовое представление каналов).

Архитектура и модули
- Парсер: считывает заголовок, валидирует поля и загружает массив пикселей в память.
- Сериализатор (сохранение): записывает заголовок и данные пикселей в указанный формат (P3/P6).
- Операции над изображением: трансформации (поворот, зеркалирование), инверсия цветов, изменение яркости/контраста, простая фильтрация.
- Тесты/примеры: набор PPM-файлов для проверки корректности операций.

Структура репозитория
- Исходники и проект:
  - [Test_cpp_penyaz/Test_cpp_penyaz.vcxproj](Test_cpp_penyaz/Test_cpp_penyaz.vcxproj)
  - [Test_cpp_penyaz/Test_cpp_penyaz.vcxproj.filters](Test_cpp_penyaz/Test_cpp_penyaz.vcxproj.filters)
  - [Test_cpp_penyaz/test.cpp](Test_cpp_penyaz/test.cpp)
- Тестовые файлы PPM:
  - [Test_cpp_penyaz/test_color_changing.ppm](Test_cpp_penyaz/test_color_changing.ppm)
  - [Test_cpp_penyaz/test_colors_inverting.ppm](Test_cpp_penyaz/test_colors_inverting.ppm)
  - [Test_cpp_penyaz/test_flip_over_180.ppm](Test_cpp_penyaz/test_flip_over_180.ppm)
  - [Test_cpp_penyaz/test_flip_over_90.ppm](Test_cpp_penyaz/test_flip_over_90.ppm)
  - [Test_cpp_penyaz/test_mirroring.ppm](Test_cpp_penyaz/test_mirroring.ppm)
  - [Test_cpp_penyaz/test_save.ppm](Test_cpp_penyaz/test_save.ppm)
- Корневые файлы конфигурации:
  - [.gitattributes](.gitattributes)
  - [.gitignore](.gitignore)
  - [Test_cpp_penyaz.sln](Test_cpp_penyaz.sln)
  - [README.md](README.md)

Сборка и запуск
- Открыть [Test_cpp_penyaz.sln](Test_cpp_penyaz.sln) в Visual Studio.
- Построить решение (Release/Debug).
- Пример запуска: выполнить бинарь из проекта; тестовый `test.cpp` демонстрирует вызовы парсера/сохранения и нескольких операций над изображением.

Примеры использования (логика)
- Загрузка: открыть файл, прочитать заголовок, выделить buffer ширины*высоты*3, заполнить RGB-байтами.
- Изменение: выполнять побайтовые/покоординатные операции над буфером (например, swap каналов, инверсия: 255 - value).
- Сохранение: записать заголовок и буфер в выбранном формате.

Тестирование
- Использовать предоставленные PPM в папке [Test_cpp_penyaz](Test_cpp_penyaz) для валидации: визуально и програмно.
- Проверять корректность заголовка и соответствие размера буфера (width * height * 3).

Ограничения и замечания
- Предназначено для изображений, которые полностью помещаются в оперативную память.
- Нет поддержки цветовых профилей или форматов с maxval > 255.
- При необходимости расширения — добавить стримовую обработку для больших изображений и поддержку дополнительных типов PNM.

