# PythonSetupExample

## Вступление

К сожалению сейчас нет простого способа для распространения приложений написаных на `Python`.
Это связано с тем что `Python` является интерпретируемым языком, и при попытке запустить приложение в другом окружении возникают проблемы с тем что:

* Не все нужные сторонние библиотеки установленны
* Не все установленные библиотеки обновлены до нужной версии

Есть несколько путей решения это проблемы. На первый взгляд самый простой путь --- статическая сборка (когда все нужные зависимости зашиваются в один/несколько бинарных файлов и поставляются вместе).
Для этого уже написано много разных утилит, например [pyinstaller](https://www.pyinstaller.org) или [py2exe](https://www.py2exe.org).
Но эти утилиты стабильно работают только в рамках одной системы, например при попытке перенести бинарный файл собраный на `windows 7` на `windows 10` при запуске может возникнуть окно `magic *.dll file not found`,
а в худшем случае приложение будет крашится при запуске и понять в чем причина будет очень сложно.

Поэтому не хочется использовать статическую сборку, а хочется оставить интерпритацию кода.
Но в этом случае помимое основного приложения надо поставлять ещё и скрипт для установки всех нужных зависимостей.
В качестве этого скрипта предлагается использовать [setuptools](https://setuptools.readthedocs.io/en/latest).
Это достаточно популярный метод распространения библиотек на `Python`, в котором очень много сложных зависимостей можно описать в одну строчку:

```
install_requires=['kivy>=1.11.1', 'click']
```

И при вызове скрипта установки он сам найдет все нужные пакеты и установит/обновит их:

```
# Обновление kivy с версии 1.11.1 до версии 2.0.0rc4
# Обновление происходи поскольку мы разрешаем версию >=1.11.1 и при установке ищется максимально возможная версия,
# которая удовлетворяет ограничениям

Processing dependencies for gui-example==1.0
Searching for Kivy==2.0.0rc4
Best match: Kivy 2.0.0rc4
Processing Kivy-2.0.0rc4-py3.7-macosx-10.12-x86_64.egg
Removing Kivy 1.11.1 from easy-install.pth file
Adding Kivy 2.0.0rc4 to easy-install.pth file

# Если бы было указано kivy-=1.11.1, то была бы установленна именно эта версия

Processing dependencies for gui-example==1.0
Searching for kivy==1.11.1
Reading https://pypi.org/simple/kivy/
Downloading https://files.pythonhosted.org/packages/0f/51/1fdcd05217919e77016f8f241d19a87d1d15cf1c074d78a6f3c5ca44198b/Kivy-1.11.1-cp37-cp37m-macosx_10_6_intel.macosx_10_9_intel.macosx_10_9_x86_64.macosx_10_10_intel.macosx_10_10_x86_64.whl#sha256=8819a27a09871af451760cb69486ced52e830c8a0a37480f22ef5e692f12c05b
Best match: Kivy 1.11.1
Processing Kivy-1.11.1-cp37-cp37m-macosx_10_6_intel.macosx_10_9_intel.macosx_10_9_x86_64.macosx_10_10_intel.macosx_10_10_x86_64.whl
Installing Kivy-1.11.1-cp37-cp37m-macosx_10_6_intel.macosx_10_9_intel.macosx_10_9_x86_64.macosx_10_10_intel.macosx_10_10_x86_64.whl to /usr/local/lib/python3.7/site-packages
writing requirements to /usr/local/lib/python3.7/site-packages/Kivy-1.11.1-py3.7-macosx-10.12-x86_64.egg/EGG-INFO/requires.txt
Removing Kivy 2.0.0rc4 from easy-install.pth file
Adding Kivy 1.11.1 to easy-install.pth file
```


## Как установить pip3, setuptools, etc

TODO

### Linux
TODO

### Mac OS
TODO

### Windows

TODO

## Setup.py

TODO

### Как написать

TODO

### Как запускать

TODO

### Пример с GUI

TODO

### Особенности работы с Windows

TODO
