#include <iostream>
#include <string>
using namespace std;

int main() {
  // Variables
  string input, clas;
  int nota;
  int notas = 0; int count = 0;
  int aprobados = 0; int reprobados = 0;
  float promedio;

  // Loop principal
  while (true) {

    // Conteo de estudiantes
    count++;

    // Recopilación de datos
    cout << "Ingrese la nota del estudiante \n>>> ";
    cin >> nota;

    // Clasificacion
    if (nota <= 9 && nota >= 0) {
      reprobados++;
      switch (nota) {
      case 1:
      case 2:
      case 3:
      case 4:
      case 5:
        clas = "Deficiente";
        break;
      case 6:
      case 7:
      case 8:
      case 9:
        clas = "Mejorable";
        break;
      }
    } else if (nota <= 20) {
      aprobados++;
      switch (nota) {
      case 10:
      case 11:
      case 12:
        clas = "Regular";
        break;
      case 13:
      case 14:
      case 15:
        clas = "Bueno";
        break;
      case 16:
      case 17:
      case 18:
        clas = "Muy bueno";
        break;
      case 19:
      case 20:
        clas = "Sobresaliente";
        break;
      }
    }
    // Controlador de cantidades
    else {
      cout << "Esta entrada no es válida, intente con otra." << endl;
      continue;
    }
    cout << "Esta nota es: " << clas << endl;
    notas += nota;

    // Salida del loop
    cout << "\nQuiere ingresar otra nota? (ingrese 'y' para afirmar o "
            "cualquier otro caracter para salir) \n>>> ";
    cin >> input;
    if (input != "y") {
      break;
    }
  }
  // Salida y muestra de resultados
  cout << "Cantidad de alumnos en la sección: " << count << endl;
  cout << "Cantidad de alumnos aprobados: " << aprobados << endl;
  cout << "Cantidad de alumnos reprobados: " << reprobados << endl;
  cout << "Promedio de la sección: " << (notas / count) << endl;
  return 0;
}
