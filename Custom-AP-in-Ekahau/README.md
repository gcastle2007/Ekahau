# Добавление своей точки доступа в Ekahau

У многих из нас возникает вопрос: Как добавить новую точку доступа в Ekahau?

Ответ на данный вопрос достаточно прост и кроется в конфигурациионных файлах Ekahau и даташите на точку доступа.

Сразу скажу, что если Вы это делаете, то понимаете, что делаете и зачем. Всё сделаное Вами делается на ваш страх и риск.

Папку инсталляции Ekahau обозначим как `root`.

Соответственно конфигруационные файлы по точкам доступа лежат в `root\conf\accessPointTypes.xml`.

Простой случай: необходимо создать точку доступа 4:4x4 с частотами 2.4 Ghz и 5Ghz, технология AX, антенны встроенные, без BLE. За основу возьмём, наприпер, Aruba AP-503H.

В конфигруационном файле находим секцию:

    <accessPointType vendor="Aruba" model="AP-503H">
        <radioType technology="ax" frequencyBand="2.4" mimo="2x2" spatialStreams="2"/>
        <radioType technology="ax" frequencyBand="5" mimo="2x2" spatialStreams="2"/>
        <radioType radioTechnology="bluetooth" frequencyBand="2.4" defaultAntennaBluetooth="Aruba AP-503H BLE"/>
    </accessPointType>


Копируем её и создаём свою:
 
    <accessPointType vendor="Custom AP" model="AP-101">
        <radioType technology="ax" frequencyBand="2.4" mimo="4x4" spatialStreams="4"/>
        <radioType technology="ax" frequencyBand="5" mimo="4x4" spatialStreams="4"/>
    </accessPointType>

Сохраняем.
  
Также необходимо добавить антенны. Эти данные хранятся в архиве `root\conf\antennas.zip`.

Ищем в архиве следующие файлы:

    Aruba AP-503H 2.4GHz.json
    Aruba AP-503H 5GHz.json
    Aruba AP-503H BLE.json

Делаем их копию, обозвав соответствующим образом:

    Custom AP AP-101 2.4Ghz.json
    Custom AP AP-101 5Ghz.json
  
Если открыть эти файлы на редактирование, то увидим описание диаграммы направленности антенны:

    {
        "directional": false,
        "horizontalPlane": {
            "alignment": {
                "degrees": 90.0
            },
        "gains": [
        {
          "angleInDegrees": 0.0,
          "dBi": 3.3
        },
        {
          "angleInDegrees": 5.0,
          "dBi": 3.38
        }
    ... (etc..)
  
Данные можно взять из даташита и внести в соответствующие поля, как для `horizontalPlane`, так и для `elevationPlane`.

Обратите внимание на то, что в конце файла также необходимо скорректировать записи:
  
    "frequencyBand": "TWO",
    "accessPointVendorModel": {
    "vendor": {
        "vendor": "Custom AP"
    },
    "model": {
        "model": "AP-101"
    }
    },
    "wcsMapping": {},
    "defaultTiltAngle": {
    "degrees": 0.0
    },
    "manufacturerMaximumGain": NaN,
    "antennaTechnology": "WIFI",
    "defaultMounting": "WALL",
    "apCoupling": "INTERNAL_ANTENNA"
    }
  
Файлы необходимо будет сохранить в архиве с антеннами.

Итого получим:

![Custom AP AP-101](./images/Custom_AP_AP-101.PNG)

Дальнейшее изучение файла `accessPointTypes.xml` поможет Вам понять, как корректно добавлять точки с теми или иными настройками.

PS: В папке AP_and_antennas могут находится конифгурации точек доступа и антенн, которых нет в официальном дистрибутиве. Если Вы хотите сделать конфигурацию какой-то точки доступа или антенны общедоступными, то Вы можете сделать это через Pull Request.

# change log:
2022-04-29 + Eltex WEP-3ax
