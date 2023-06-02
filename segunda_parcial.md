# heber emmanuel figueroa rodriguez
# DIAGRAMAS DE CLASE
###  DIAGRAMA DE CLASE #1
[![1.jpg](https://i.postimg.cc/wxJbCGKb/1.jpg)](https://postimg.cc/QV8b5Sdp)

### CODIGO #1
#### MAIN:
```dart
import 'dart:io';
import 'dart:math';

void main(List<String> args) {
var e1 = Estudiante();
Estudiante e2 = Estudiante();
e1.nombre='juan';
e1.aNacimiento = 1990;

e2.nombre='heber';
e2.aNacimiento = 2004;
e1.reporte();
//e2.reporte();

/* print(e1.nombre);
print(e2.nombre);
print(e1.aNacimiento);
print(e2.aNacimiento); */

}
```
#### CLASS ESTUDIANTE
```dart

class Estudiante{
  
  String nombre = '';
  int?  aNacimiento;
  void reporte (){
    print('dame tu nombre');
    String? nombre = stdin.readLineSync();
    print('dame el año actual');
        

    int? aActual = int.parse(stdin.readLineSync()!);
    print('dame el año de nacimiento');
        int? aNacimiento = int.parse(stdin.readLineSync()!);
   }
}
```
### DIAGRAMA DE CLASE #2
[![2.jpg](https://i.postimg.cc/4d6Zxv26/2.jpg)](https://postimg.cc/XGYt25bq)

### CODIGO #2
#### MAIN:
```dart
 void main(List<String> args) {
  Animal  perro =Animal();
  perro.nombre = 'boby';
  perro.sonido = 'guau';
  Animal gato = Animal();
  gato.nombre = 'tonchi';
  gato.sonido = 'miau';
  Animal pato =Animal();
  pato.nombre = 'juan';
  pato.sonido = 'cua cua';
  reporte(pato);
  reporte(gato);
  reporte(perro);
  
}
```
#### CLASS ANIMAL:
```dart

class Animal{
  String nombre = '';
  String sonido = '';
}
void reporte(Animal a){
print('nombre: ${a.nombre}');
print('sonido: ${a.sonido}');
} 
```
### DIAGRAMA DE CLASE #3
[![3.jpg](https://i.postimg.cc/KY7sK9F8/3.jpg)](https://postimg.cc/p9TB4Jpw)

### CODIGO #3
#### MAIN:
```dart
import 'animal.dart';

void main(List<String> args) {
  Dias d1 = new Dias('martes', 25, 'abril');
  d1.calcula(2023);
}
```
#### CLASS DIAS
```dart
class Dias{
  String? dia ;
  int? numeroDia ;
  String? mes ;
  Dias(String dia, int numeroDia, String mes){
    this.dia = dia;
    this.mes = mes;
    this.numeroDia = numeroDia;
      }
  void calcula(int a_Actual){
    print('hoy es $dia $numeroDia del mes de $mes del $a_Actual');
  }

}
```
### DIAGRAMA DE CLASE #4
[![4.jpg](https://i.postimg.cc/t4jcXQQM/4.jpg)](https://postimg.cc/BXmpgzvT)

### CODIGO #4
#### MAIN:
```dart
import 'figura.dart';
void main(List<String> args) {
  Figura rectangulo1 = new Figura.rectangulo(3, 12);
  Figura cuadrado1 = new Figura.cuadrado(3);
  print('Area de Recangulo: ${rectangulo1.areaRectangulo()}');
  print('Area Cuadrado: ${cuadrado1.areaCuadrado()}');
  print('Perimetro de Recangulo: ${rectangulo1.perimetroRectangulo()}');
  print('Perimetro Cuadrado: ${cuadrado1.perimetroCuadrado()}');
  
}
```
#### CLASS FIGURA:
```dart

class Figura{
  int? base;
  int? altura;

  Figura.rectangulo(this.base, this.altura);

  Figura.cuadrado(int base){
    this.base = base;
  }
  
  int areaRectangulo(){
    if (altura == null || base == null){
      print('no se puede calcular');
      return 0;
    }
    return base! * altura! ;
  }

  int areaCuadrado(){
    int res = 0;
    if(base == null){
      print('no se puede calcular');
    } else {
      res = base! * base!; 
    }
    return res; 
  }

  int perimetroRectangulo(){
    return (base! + altura!)*2;
  }

  int perimetroCuadrado(){
    return (base! *4);
  }
}
```
### DIAGRAMA DE CLASE #5
[![unnamed5.jpg](https://i.postimg.cc/VvTc77Jc/unnamed5.jpg)](https://postimg.cc/N21VFk8N)
### CODIGO #5
#### MAIN:
```dart
 import 'shpe.dart';

void main(List<String> args) {
  Shape f1 = Shape(10, 8);
  print(f1.getArea());
  f1.base = 2;
  f1.altura = 2;
  print(f1.getArea());
  print(
    '''   el area es: ${f1.base} 
    y la altura es: ${f1.altura}
    '''
);
} 
```
#### CLASS SHAPE:
```dart
class Shape{
  int? _base;
  int? _altura;
  
  Shape(this._base, this._altura);

  int getArea(){
    return _calculadoraArea();
  }

  int _calculadoraArea(){
    return _base! * _altura!;
  }

  void set base(int? base) => _base = base;
  void set altura(int? altura) => _altura = altura;
  int? get base =>  _base;
  int? get altura =>  _altura;

  }
```

### DIAGRAMA DE CLASE #6
[![unnamed6.jpg](https://i.postimg.cc/Z5wXj72s/unnamed6.jpg)](https://postimg.cc/mPFdgwb7)
### CODIGO #6
#### MAIN:
```dart
import 'vehiculo.dart';

void main(List<String> args) {
  Vehiculo v1 = Vehiculo('TOYOTA', 2023, 'ROJO', 'AUTOMATICO');
  Vehiculo v2 = Vehiculo('BOCHO', 1900, 'BLANCO', 'ESTANDAR');
  /* v1.carro();
  v2.carro(); */
  List<Vehiculo> vehiculos =[v1,v2];
  //for(var carros in vehiculos);
  vehiculos.forEach((carro) => carro.carro()
  );
  
  } 
  ```
#### CLASS VEHICULO
  ```dart

class Vehiculo{
  String? _marca;
  int? _modelo; 
  String? _color; 
  String? _transmicion;

  Vehiculo(this._marca, this._modelo, this._color, this._transmicion);

  void carro(){
    print(' marca: ${_marca} \n color:${_color} \n transmicion: ${_transmicion} \n modelo:${_modelo} \n');

  }
 
   void set marca(String marca) => this._marca = marca;
  void set modelo(int modelo) => this._modelo = modelo;
  void set color(String color) => this._color = color;
  void set transmicion(String transmicion) => this._transmicion = transmicion;

  String get marca => this.marca;
  int get modelo => this.modelo;
  String get color => this.color;
  String get transmicion => this.transmicion; 
 
}
```

### DIAGRAMA DE CLASE #7
[![unnamed7.jpg](https://i.postimg.cc/sg0GyzbY/unnamed7.jpg)](https://postimg.cc/Wdg16BNz)
### CODIGO #7
#### MAIN:
```dart
import 'animal.dart';
 void main(List<String> args) {
  Animal a1 = Animal('vaca', 10);
  a1.instancia();
  Animal.instanciaStatic();
  print('-' *20);
  Animal a2 = Animal('CERDO', 20);
  a2.instancia();
  Animal.instanciaStatic();
  Animal a3 = Animal('vaca', 10);
  a3.instancia();
  Animal.instanciaStatic();
  print('-' *20);
  List<Animal> animales=[a1,a2,a3];
  int suma =0;
  animales.forEach((element) {
    suma += element.cantidad;
   });
   print('total de animales: $suma');
} 
 ```
#### CLASS ANIMAL:
 ```dart

class Animal{
  String tipoAnimal;
  int cantidad;
  static int cantidadS = 0;

  Animal(this.tipoAnimal, this.cantidad){
    cantidadS ++;
     }
  void instancia(){
    print('el animal es: $tipoAnimal');
    print('la cantidad es: $cantidad');
  }

  static void instanciaStatic(){
    
    print('la cantidad es:$cantidadS');
  }
} 
```

### DIAGRAMA DE CLASE #8
[![unnamed8.jpg](https://i.postimg.cc/4ySv0cvc/unnamed8.jpg)](https://postimg.cc/Mf1jMvFZ)
### CODIGO #8
#### MAIN:
```dart
import 'caballo.dart';
import 'pato.dart';
import 'animal.dart';
import 'vaca.dart';
void main(List<String> args) {
  Animal a1 = Animal('animal', 100);
  a1.showPropiedades();
  print('-'*20);
   a1.quantity = 1000;
   a1.showPropiedades();
   print('°'*20);
  Pato pato1 = Pato('pekines', 10, 'curvo');
  pato1.showPropiedades();
  print('-'*20);
   pato1.quantity =100;
  pato1.showPropiedades();
  print('°'*20);
  Vaca vaca1 = Vaca('suiza', 20, 'negro');
  vaca1.showPropiedades();
  print('-'*20);
  vaca1.quantity = 100;
  vaca1.showPropiedades();
  print('°'*20);
  Caballo caballo1 = Caballo('frision', 30,'larga' );
  caballo1.showPropiedades();
  print('-'*20);
  caballo1.quantity = 100;
  caballo1.showPropiedades();
  
  }
  ```
#### CLASS ANIMAL:
```dart
  class Animal{
  String? _breed;
  int? _quantity;
Animal(this._breed, this._quantity);

  String? get breed => _breed;
  int? get quantity => _quantity;
  set breed(String? breed) => _breed=breed;
  set quantity (int? quantity) => _quantity=quantity;
  

  void showPropiedades(){
    print('breed: $_breed');
    print('quantity: $_quantity');
    
  }
}
  ``` 
#### CLASS CABALLO EXTENDS ANIMAL:
```dart
import 'animal.dart';

class Caballo extends Animal{
  String? _melena;
  Caballo(super._breed, super._quantity, this._melena);


   @override
  void showPropiedades() {
    super.showPropiedades();
    
  print('melena: $_melena');
  } 
}
```
#### CLASS PATO EXTENDS ANIMAL:
```dart
import 'animal.dart';

class Pato extends Animal{
  String? _tipoPico;
  Pato(super._breed, super._quantity, this._tipoPico);

    @override 
   void showPropiedades(){
    super.showPropiedades();
    print('tipoPico: $_tipoPico');
   }
   
}
```
#### CLASS VACA EXTENDS ANIMAL:
```dart
import 'animal.dart';

class Vaca extends Animal{
  String? _color_manchas;
  Vaca (super._breed, super._quantity, this._color_manchas);

  
  @override
  void showPropiedades() {
    super.showPropiedades();
    print('colr manchas: $_color_manchas');
  }

}
```

### DIAGRAMA DE CLASE #9
[![unnamed9.jpg](https://i.postimg.cc/FRMNxr1x/unnamed9.jpg)](https://postimg.cc/XGkRj0fZ)

### CODIGO #9
#### MAIN:
```dart
void main(List<String> args) {
  final Carro jeep = Carro('rojo', 100, 'jeep', 'suv');
  jeep.showVehiculo();
  jeep.maxVelocidad();

  final Motocicleta yamaha = Motocicleta('rosita', 160, 'r6');
  yamaha.showVehiculo();
  yamaha.maxVelocidad();
}
```
#### CLASS VEHICULO:
```dart
abstract class Vehiculo{
  String? _color;
  int? _velocidad;

  Vehiculo(this._color, this._velocidad){
    print('constructor padre vehiculo');
  }
    set color(String? color) => this._color = color;
  set velocidad(int? velocidad) => this._velocidad = velocidad;
  
  String? get color => _color;
  int? get velocidad => _velocidad;

  int maxVelocidad() => _velocidad! * 2;

  void showVehiculo(){
    print('color: $_color');
    print('velocidad: $_velocidad');
  }
}
``` 
#### CLASS CARRO EXTENDS VEHICULO
```dart
class Carro extends Vehiculo{
  String? _marca;
  String? _tipo;

  Carro(super._color, super._velocidad, this._marca, this._tipo){
    print('constructor hijo carro');
  }
  @override
  void showVehiculo(){
    super.showVehiculo();
    print('marca: $_marca');
    print('tipo: $_tipo');
  }
}
```
#### CLASS MOTOCICLETA EXTENDS VEHICULO
```dart
class Motocicleta extends Vehiculo{
  String? _marca;
  
  Motocicleta(super._color, super._velocidad, this._marca){
    print('constructor hijo Motocicleta');
  }

  @override
  void showVehiculo() {
    super.showVehiculo();
    print('marca: $_marca');
  }
}
```
### DIAGRAMA DE CLASE #10
[![unnamed10.jpg](https://i.postimg.cc/XqD2SqSR/unnamed10.jpg)](https://postimg.cc/kRKNWn5s)

### CODIGO #10
#### MAIN:
```dart
void main(List<String> args) {
  Dolphin flippy = Dolphin();
  flippy.swim();
}
```
#### CLASS ANIMAL:
```dart
class Animal{
  Animal(){
  print('ANIMAL CONSTRUCTOR');
  }
}
```
#### CLASS MAMMAL EXTENDS ANIMAL:
```dart
class Mammal extends Animal{
  Mammal(){
    print('mammal constructor');
  }
}
```
#### CLASS BIRD EXTENDS ANIMAL:
```dart
class Bird extends Animal{
  Bird(){
    print('bird constructor');
  }
}
```
#### CLASS FISH EXTENDS ANIMAL:
```dart
class Fish extends Animal{
  Fish(){
    print('fish constructor');
  }
}
```
#### CLASS SWIMMER:
```dart
abstract class Swimmer{
  void swim(){
    print('swimming');
  }
}
```
#### CLASS DOLPHIN EXTENDS MAMMAL WITH SWIMMER
```dart
class Dolphin extends Mammal with Swimmer{
  Dolphin(){
    print('Dolphin constructor');
  }
}
```
