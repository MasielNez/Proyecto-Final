Proyecto-Final
==============

//Proyecto Final ISC-205
//Integrantes: Emmanuel, Masiel y Jordaliz.
//PROYECTO FINAL DE ISC-205 // ESTUDIANTES: EMMANUEL, MASIEL Y JORDALIZ.

#define MAX_WORKERS 2
#include <iostream>
using namespace std;

struct workers{
string name;
string department;
int wage;
int hoursworked;
}typedef workers;

//FUNCIONES:
int FuncSalario(int lenght, workers worker[].hoursworked, workers worker[].wage, workers worker[].department,int hoursmonth);//Hay que revisar bien la funcion, me da 5 errores por ella
//FINAL FUNCIONES

int main()
{
    int menu;
    int lenght=0;
    workers worker[MAX_WORKERS];

    cout << "\tCONTROL DE REGISTRO - TRABAJADORES ITT" << endl;
    cout<<" *************************************************"<<endl;
    cout<<" *      Selecciones una de las opciones          *"<<endl;
    cout<<" *************************************************"<<endl;
    cout<<" * 1- Listado de trabajadores                    *"<<endl;// dividido por departamento y en orden descendente
    cout<<" * 2- Registrar trabajador                       *"<<endl;
    cout<<" * 3- Mostrar salario de un trabajador especifico*"<<endl;//una busqueda
    cout<<" * 4- Comision a pagar por la empresa            *"<<endl;// incluir salario total a pagar con y sin bono. Dividirlo tambien por departamento.
    cout<<" * 5- Listado trabajador/es con el mayor salario *"<<endl;
    cout<<" * 6- Listado trabajadores que no recibiran bonos*"<<endl;//dividido por departamento
    cout<<" * 7- Dia de mayores ausencias en el mes         *"<<endl;
    cout<<" * 0- Salir                                      *"<<endl;
    cout<<" ************************************************"<<endl;
    cin >> menu;
string nombre;
            int j;
     while(menu!= 0){
    switch (menu){

    case 1:

            for(int i = 0; i < lenght; i++)
            {
                workers aux= *worker[i];
                cout << i+1 << " - " << aux.name << " - " << aux.department << " - " << aux.wage;
            }
            break;
    case 2:

            if(lenght < MAX_WORKERS)
            {
                cout << "Digite el nombre del trabajador:\n";
                cin >> worker[lenght].name;
                cout << "Digite el departamento al que pertenece. Administrativo: admin | Tecnico: tec \n";
                cin >> worker[lenght].department;
                cout << "Digite la cantidad de horas que trabajo: " << endl;
                cin >> worker[lenght].hoursworked;
                cout << "Digite su salario mensual: " << endl;
                cin >> worker[lenght].wage;
                lenght++;

            }
            else
            {
                cout << "No se aceptan mas trabajadores.";
            }
            break;

    case 3:

            cout << "Digite el nombre del jugador" << endl;
            cin >> nombre;
            bool encontrado;
            encontrado = false;
            j = 0;
            while(encontrado == false && j < lenght)
            {
                if(worker[j].name == nombre)
                {
                    cout << "El trabajador " << nombre << " gana: " << worker[j].wage;
                    encontrado = true;
                }
                j++;
            }
            if(j == lenght)
                cout << "No se encontró ningún trabajador con dicho nombre.";
            break;

    case 4:

            cout << "Total a pagar a trabajadores: " << FuncSalario(lenght, workers); //crear funcion para calcular bonos y salario
            break;

    case 5:
            cout<< "klk";
            break;


    }
                    }

    return 0;
}

int FuncSalario(int lenght, workers &worker,int hoursmonth){
    
    workers aux2=worker[lenght];
    
    int hoursmonth=160;//4 semanas, 5 dias laborales, 8 hrs diarias.
    for(int x=0; x<lenght; x++){

        if ((hoursmonth == worker[x].hoursworked) && (worker[x].department == 'admin'))
       {
           worker[x].wage = (worker[x].wage + (worker[x].wage * 0.005));
       }

        else if ((hoursmonth == worker[x].hoursworked) && (worker[x].department == 'tec')
        {
            worker[x].wage = (worker[x].wage + (worker[x].wage * 0.008));
        }

}

return worker[lenght].wage;
}
