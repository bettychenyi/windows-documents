## Read xml file by Powershell

* Exmaple of the XML file (car.xml)
```
<?xml version="1.0" encoding="UTF-8"?>
<!-- This is the XML exmaple. I am comments -->
<Cars>
  <Car Maker="TTTES" Model="X">
    <Seats>6</Seats>
    <Wheels>4</Wheels>
  </Car>
  <Car Maker="Porsh" Model="910">
    <Seats>4</Seats>
    <Wheels>4</Wheels>
  </Car>
  <Car />
</Cars>
```

* Read it with xml format:
```
PS C:\Users\betty\Desktop> [xml] $contentAsXml = Get-Content .\car.xml
PS C:\Users\betty\Desktop> $contentAsNormalText = Get-Content .\car.xml

PS C:\Users\betty\Desktop> $contentAsXml.Cars.Car.Count
3

PS C:\Users\betty\Desktop> $contentAsNormalText.Count
13
```
