# Startup

When first launching AnkerMake Studio, it will ask you to choose a printer:

![printer-choice](img/printer-choice.png)

These choices are controlled via the _Anker.ini_ file where AnkerMake Studio is installed. Typically it's "C:\Users\<your profile name>\AppData\Roaming\AnkerMake Studio Profile\vendor". Here's a sample for the AnkerMake M5:

```
    [printer_model:M5]
    name = AnkerMake M5
    variants = 0.4
    technology = FFF
    family = AnkerMake M5
    bed_model = M5-bed.stl
    bed_texture = M5-texture_m5.svg
    thumbnail = M5.png
    default_materials = PLA+; TPU; PETG; ABS
```
