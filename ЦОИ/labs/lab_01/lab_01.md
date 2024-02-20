# Цифровая обработка изображений

© Бибиков С.А., к.т.н., доцент кафедры суперкомпьютеров и общей информатики, Самарский университет  
© Петров М.В., старший преподаватель кафедры суперкомпьютеров и общей информатики, Самарский университет

## Лабораторная работа 1. Работа с изображениями

1. Выбрать несколько изображений (любой источник).

2. Считать изображение функцией из библиотеки.

3. Реализовать вручную алгоритм (или несколько) обработки изображений:
   - гамма-коррекция  
     ```math
     I_{out} = (\frac{I_{in}}{255})^\frac{1}{\gamma} \cdot 255
     ```
   - кривая коррекции, например, логистическая кривая (S-curve)
     ```math
     \displaylines{S = \frac{L}{1 + e^{-k \cdot (x - x_0)}} \\
     L = 1, k = 1, x_0 = 0 \\
     S(x) = \frac{1}{1 + e^{-k \cdot x}} \\
     I_{out} = (\frac{I_{in}}{255} \cdot S(x)) \cdot 255}
     ```  
     <p align="center">
       <img width=600 height=400 src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/88/Logistic-curve.svg/600px-Logistic-curve.svg.png">
     </p>
   - контрастирование
   ```math
   I_{out} = \alpha \cdot I_{in} + \beta
   ```
   - пороговая обработка, T - значение порога
   ```math
   I_{out}(x, y) = 
   \begin{cases}
    255    & \quad \text{если } I_{in}(x, y) > T \\
    0  & \quad \text{иначе}
   \end{cases}
   ```
   - наложение (бленд) изображений
   ```math
   I_{out} = \alpha \cdot I_1 + \beta \cdot I_2
   ```
   - ...  

4. Применить выбранный алгоритм (алгоритмы) к изображениям, привести результаты обработки.

Полезные ссылки:
- [OpenCV Image Filtering](https://docs.opencv.org/4.x/d4/d86/group__imgproc__filter.html)
- [OpenCV Color Space Conversions](https://docs.opencv.org/4.x/d8/d01/group__imgproc__color__conversions.html) - 
основной метод `cvtColor` и различные поля `enum cv::ColorConversionCodes`.
- [OpenCV Color conversions](https://docs.opencv.org/4.x/de/d25/imgproc_color_conversions.html)
- [Туторы на питоне](https://docs.opencv.org/4.7.0/d6/d00/tutorial_py_root.html)
- [OpenCV Getting Started with Videos, Python](https://docs.opencv.org/4.7.0/dd/d43/tutorial_py_video_display.html)