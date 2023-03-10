
---
# Segundo semestre 
----
Librerias mas usadas (en el semestre):
1. #include + <nombre de la libreria>

###<span style="color:red;">Compilador</span>

el que mas se uso fue el compilador del **_git_** y se compila de la sigiente manera:
En **C++**
``` 
g++ src/main.cpp -o soutput/main.exe
```
En **C**
```
cpp src/main.c -o aoutput/main.exe
```
###<span style="color:red;">Que hace?</span>
imprimer en pantalla y ejecuta el codigo 
###<span style="color:green;">Declaracion de variables: </span>
<span style="color:purple;">globales </span>: Ban afuea del bloque principal  y se declara:
1. #defiene
2. const
3. int, char ,etc.
4. *no va a cambier en el codigo*

<span style="color:purple;">locales </span>: Ban dentro del bloque principal, en funciones y procesos.pueden ser enteros, booleanos,flotantes,etc.
## <span style="color:purple;">No olvidar</span>
se unsa el atajo en c++ para no repetir varias veses lo mismo
``` C++
using namespace std;
```
<span style="color:blue;"> Ejemplo de codigo</span>
```C++
#include <iostream>
using namespace std;
int main()//bloque principal
{
    cout<<"hola mundo";
    return 0; //siempre retorna algo
}
```
# <span style="color:purple;"> Refuerso de lo mas basico</span>
---
## Bucles
---
<span style="color:blue;">for</span>
 el bucle for se utiliza para repetir una sección de código un número específico de veces. 
 ejemplo:
 ```c++
 #include <iostream>
using namespace std;

int main() {
   int i = 1;
   do {
      cout << i << " ";
      i++;
   } while(i <= 5);

   return 0;
}
```

<span style="color:blue;">do-while</span>
 el bucle do-while es similar al bucle while, pero la condición se evalúa después de la primera iteración, lo que significa que el código dentro del bucle se ejecutará al menos una vez.Ejm.
 ```c++
#include <iostream>
using namespace std;

int main() {
   for(int i = 1; i <= 5; i++) {
      cout << i << " ";
   }

   return 0;
}

```

<span style="color:blue;">while</span>
el bucle while se utiliza para repetir una sección de código mientras se cumple una condición específica.
 ```c++
 #include <iostream>
using namespace std;

int main() {
   int i = 1;
   do {
      cout << i << " ";
      i++;
   } while(i <= 5);

   return 0;
}
```

---
### Matrices 
---






<span style="color:#ff00ff;">Creacion de matrices y eimprimir matrices  </span>
```C++
#include <iostream>
using namespace std;

int main() {
   int matriz[3][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};

   for(int i = 0; i < 3; i++) {
      for(int j = 0; j < 3; j++) {
         cout << matriz[i][j] << " ";
      }
      cout << endl;
   }

   return 0;
}
```
<span style="color:#ff00ff;">llenado de matrices </span>
```c++
#include <iostream>
using namespace std;

int main() {
   int matriz[2][2];

   // Recorre la matriz y pide al usuario que ingrese un valor para cada elemento
   for(int i = 0; i < 2; i++) {
      for(int j = 0; j < 2; j++) {
         cout << "Ingrese un valor para la posición [" << i << "][" << j << "]: ";
         cin >> matriz[i][j];
      }
   }

   // Imprime la matriz
   cout << "La matriz ingresada es: " << endl;
   for(int i = 0; i < 2; i++) {
      for(int j = 0; j < 2; j++) {
         cout << matriz[i][j] << " ";
      }
      cout << endl;
   }

   return 0;
}
```
--- 
### <span style="color:orange;">Archivos</span>
---
Los archivos vivmos en el curso y los usamos mas para guardar informacion.

<span style="color:orange;" >Creacion archivos desde consola e insertar valores y texto </span>
```c++
#include <iostream>
#include <fstream>
using namespace std;

int main() {
   ofstream archivo("miarchivo.txt"); // Abre un archivo llamado "miarchivo.txt"

   if(archivo.is_open()) { // Verifica que el archivo se haya abierto correctamente
      archivo << "Este es un ejemplo de archivo creado con C++.\n";
      archivo << "Puedes escribir cualquier cosa que desees en este archivo.\n";
      archivo.close(); // Cierra el archivo
      cout << "El archivo se creó correctamente." << endl;
   }
   else {
      cout << "Error al crear el archivo." << endl;
   }

   return 0;
}

```

<span style="color:orange;" >lectura e imprecion desde consola</span>
```c++
#include <iostream>
#include <fstream>
using namespace std;

int main() {
   string linea;
   ifstream archivo("miarchivo.txt"); // Abre un archivo llamado "miarchivo.txt"

   if(archivo.is_open()) { // Verifica que el archivo se haya abierto correctamente
      while(getline(archivo, linea)) { // Lee el archivo línea por línea
         cout << linea << endl; // Imprime cada línea en la consola
      }
      archivo.close(); // Cierra el archivo
   }
   else {
      cout << "Error al abrir el archivo." << endl;
   }

   return 0;
}
```

---
Temas nuevos 
---
## ___<span style="color:orange;" >Punteros </span>___
<span style="color:pink;" >que es un punero  </span>
Un puntoro es aquel que esta en el heap de la memoria ram, donde comienza la memoria dinamica.
En C++, un puntero es una variable que almacena la dirección de memoria de otra variable. En otras palabras, un puntero es una variable que "apunta" a otra variable. En lugar de almacenar el valor de la variable directamente, un puntero almacena la dirección de memoria donde se encuentra la variable.

La dirección de memoria se representa como un número entero sin signo, que indica la ubicación de la variable en la memoria. Los punteros se utilizan comúnmente para referirse a variables que se encuentran en otras partes del programa o en la memoria dinámica.
__declarar un pruntro en c++__
```c++
int* ptr;
///ejm sencillo

#include <iostream>

using namespace std;

int main() {
    int a = 10;
    int b = 20;

    // Mostramos los valores iniciales de a y b
    cout << "Antes del intercambio:" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;

    // Creamos un puntero para intercambiar los valores de a y b
    int *p = &a;
    int *q = &b;
    int temp = *p;
    *p = *q;
    *q = temp;

    // Mostramos los valores después del intercambio
    cout << "Después del intercambio:" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;

    return 0;
}
```
___ahora bien unejemplo de clase que usa punteros para matrices___
## <span style="color:orange;">Ejemplo de como reservar memoria </span>
```c++

    #include <iostream>

    using namespace std;

    int **crearMatrizMalloc(int f, int c)
    {  
        int **m=NULL;
        m = (int **) malloc(f*sizeof(int *));
        for (int i = 0; i < f; i++)
            m[i] = (int *) malloc(c*sizeof(int));
        
        return m;
    }
    int **crearMatrizCalloc(int f, int c)
    {
        int **m=NULL;
        m = (int **) calloc(f, sizeof(int *));
        for (int i = 0; i < f; i++)
            m[i] = (int *) calloc(c, sizeof(int));
        
        return m;
    }
    int **crearMatrizNew(int f, int c)
    {   //int i = new int(10);    //heap   --> delete
        //int i = 10;             //stack
        int **m=NULL;
        m = new int*[f];
        for (int i = 0; i < f; i++)
            m[i] = new int[c];

        return m;
    }
    void showMatriz(int **pd, int f,int c)
    {
        for (int i = 0; i < f; i++)
        {
                for (int j = 0; j < c; j++)
                    cout<< pd[i][j] <<"\t";   
                cout<< endl;
        }
    }

    int main()
    {
        int f = 0, c = 0;
        int **pd=NULL;

        cout<<"Ingresa fila y columnas de la matriz : ";
        cin>> f >> c;
    
        pd = crearMatrizNew(f,c);

        for (int i = 0; i < f; i++)
            for (int j = 0; j < c; j++)
                pd[i][j] = rand() % 10;  // genera randomicos hasta 10
        
        showMatriz(pd,f,c);
        return 0;
    }
```

una estructura  es una colección de variables que se agrupan bajo un nombre común. Cada variable dentro de la estructura se llama "miembro" o "campo" de la estructura, y puede ser de cualquier tipo de datos válido en C++ (como enteros, flotantes, caracteres, punteros, etc.).
EJEMPLO
```c++
struct Punto {
    int x;
    int y;
};
```

## <span style="color:orange;">COLAS </span>: 
En programación, una cola es una estructura de datos que sigue el el primer elemento que se inserta en la cola es el primero en salir de ella. Se pueden insertar nuevos elementos al final de la cola, y los elementos se eliminan del frente de la cola.

Las colas son útiles en situaciones donde se necesita procesar elementos en el orden en que se reciben. Algunos ejemplos de aplicaciones de colas en programación incluyen:

1.Simulaciones: Las colas pueden usarse para modelar una línea de espera en una simulación, donde cada cliente o evento que llega se inserta en la cola y se procesa en orden de llegada.
2.Sistemas operativos: Las colas son una forma común de manejar procesos en un sistema operativo. Los procesos se insertan en la cola de acuerdo a ciertos criterios de prioridad, y se ejecutan en el orden en que se extraen de la cola.
3.Redes de computadoras: Las colas se utilizan en el enrutamiento de paquetes de red, donde los paquetes se encolan en los routers y se envían en el orden en que se recibieron.
<span style="color:orange;">ejm </span>: 
```c++
#include <iostream>
using namespace std;
 
struct nodo              //  [ # ]>-->
{
    int nro;
    struct nodo *sgte;
};
 
struct cola             //  <--< >-->   
{
    nodo *delante;
    nodo *atras  ;
};
 
 
void encolar( struct cola &q, int valor )
{
     struct nodo *aux = new(struct nodo);
     
     aux->nro = valor;
     aux->sgte = NULL;
     
     if( q.delante == NULL)
         q.delante = aux;   // encola el primero elemento
     else
         (q.atras)->sgte = aux;
     q.atras = aux;        // puntero que siempre apunta al ultimo elemento
}
 
int desencolar( struct cola &q )
{
     int num ;
     struct nodo *aux ;
     
     aux = q.delante;      // aux apunta al inicio de la cola
     num = aux->nro;
     q.delante = (q.delante)->sgte;
     delete(aux);          // libera memoria a donde apuntaba aux
     
     return num;
}
 
void muestraCola( struct cola q )
{
     struct nodo *aux;
     aux = q.delante;
         
     while( aux != NULL )
     {
            cout<<"   "<< aux->nro ;
            aux = aux->sgte;
     }    
}
 
void vaciaCola( struct cola &q)
{
     struct nodo *aux;
     
     while( q.delante != NULL)
     {
            aux = q.delante;
            q.delante = aux->sgte;
            delete(aux);
     }
     q.delante = NULL;
     q.atras   = NULL;
}
 
int menu()
{
    int op=0;
    system("cls");
    cout<< endl <<"[...] COLAS          "
        << endl <<"  0.  SALIR          "
        << endl <<"  1.  ENCOLAR        "
        << endl <<"  2.  DESENCOLAR     "
        << endl <<"  3.  MOSTRAR COLA   "
        << endl <<"  4.  VACIAR COLA    "
        << endl <<"  5.  SALIR          "
        << endl <<"\n INGRESE OPCION:   ";
    cin>> op;
    return op;
}
 
int main()
{
    struct cola q;
    q.delante = NULL;
    q.atras   = NULL;
   
    int dato;  // numero a encolar
    int x ;    // numero que devuelve la funcon pop
   
    system("color 0b");
    do
    {
        switch( menu() )
        {
            case 0: exit(0); 
            case 1:
                    cout<< "\n NUMERO A ENCOLAR: "; cin>> dato;
                    encolar( q, dato );
                    cout<<"\n\n\t\tNumero " << dato << " encolado...\n\n";
                    break;
            case 2:
                    x = desencolar( q );
                    cout<<"\n\n\t\tNumero "<< x <<" desencolado...\n\n";
                    break;
            case 3:
                    cout << "\n\n MOSTRANDO COLA\n\n";
                    if(q.delante!=NULL) muestraCola( q );
                    else   cout<<"\n\n\tCola vacia...!"<<endl;
                    break;
            case 4:
                    vaciaCola( q );
                    cout<<"\n\n\t\tHecho...\n\n";
                    break;
         }
        cout<<endl<<endl;
        system("pause");  
    }while(true);
    return 0;
}
```
### <span style="color:orange;">Pilas </span>
En programación, una pila  es una estructura de datos que sigue el principio  último elemento que se inserta en la pila es el primero en salir de ella. Se pueden insertar nuevos elementos en la parte superior de la pila, y los elementos se eliminan de la misma posición.

Las pilas son útiles en situaciones donde se necesita procesar elementos en orden inverso al que se recibieron. Algunos ejemplos de aplicaciones de pilas en programación incluyen:

Manejo de memoria: En algunos lenguajes de programación, como C++, se utilizan pilas para asignar y liberar memoria de manera dinámica.

 Evaluación de expresiones: En la notación polaca inversa, las expresiones se evalúan utilizando una pila. Los operandos se insertan en la pila, y los operadores se aplican a los elementos del tope de la pila.
    
Navegación en el historial: En algunos navegadores web, las páginas visitadas se almacenan en una pila, lo que permite al usuario volver atrás en su historial de navegación.
### <span style="color:turquoise;">ejemplo </span>
```c++
#include <iostream>
using namespace std;
 
struct nodo{
    int nro;
    struct nodo *sgte;
};
 
typedef nodo *ptrPila;   // creando nodo tipo puntero( tipo de valor )
//struct nodo1 ptrPila1;   

void push( ptrPila &p, int valor )      // Apilar
{
     ptrPila aux = new(struct nodo);  // apuntamos al nuevo nodo creado
     aux->nro = valor;
     
     aux->sgte = p ;
     p = aux ;
     cout <<" << apilado >> " <<endl;
}
 
void pop( ptrPila &p )   // Desapilar
{
     ptrPila aux;
     
     aux = p ;
     //num = aux->nro;   // asignamos el primer vamor de la pila
     cout <<" << desapilado >> " << aux->nro <<endl;
     
     p = aux->sgte ;
     delete(aux);
}
 
void mostrar_pila( ptrPila p )
{
     ptrPila aux;
     aux = p;     // apunta al inicio de la lista
     
     while( aux !=NULL )
     {
        cout<<"\t"<< aux->nro <<endl;
        aux = aux->sgte;
     }    
}
 
void destruir_pila( ptrPila &p)
{
     ptrPila aux;
     
     while( p != NULL)
     {
           aux = p;
           p = aux->sgte;
           cout<<"despachando: "<< aux->nro <<"\t";
           delete(aux);
     }
     cout<<"\n\n\t\t Pila despachada...\n\n";
}
 
int menu()
{
    int op;
    cout<<endl;
    cout<<" 1. APILAR                                "<<endl;
    cout<<" 2. DESAPILAR                             "<<endl;
    cout<<" 3. ELIMINAR PILA                         "<<endl;
    cout<<" 4. SALIR                                 "<<endl;
    cout<<"\n INGRESE OPCION: ";
    cin>> op;
    if (op==4)  exit(0);
    return op;
}
 
int main()
{
    ptrPila p = NULL;  // creando pila
    int valor;
    int op;
   
    do
    {
        cout<<"\n\n    FUNCIONALIDAD PILA : \n";
        if(p==NULL)
            cout<<"\t << vacia >> ";
        else
            mostrar_pila( p );
        switch(menu())
        {
            case 1: cout<< "\n NUMERO A APILAR: "; cin>> valor;
                    push( p, valor );
                    break;
            case 2: pop( p );
                    break;
            case 3: destruir_pila( p );
                    break;
         }
    }while(op!=5);
    return 0;
}


//  push            1   5
//  pop             2   6
//  mostrar_pila    3   7
//  destruir_pila   4   8
```
### <span style="color:red;">Pilas </span>
una lista es una estructura de datos que contiene una secuencia de elementos en un orden específico. A diferencia de los arreglos, las listas no tienen un tamaño fijo y pueden crecer o reducirse dinámicamente durante la ejecución del programa. Cada elemento de la lista está enlazado con el siguiente elemento mediante punteros.

Las listas son útiles en situaciones donde se necesita realizar muchas inserciones o eliminaciones de elementos en una estructura de datos. Algunos ejemplos de aplicaciones de listas en programación incluyen:

Gestión de memoria: En algunos lenguajes de programación, como Java, se utilizan listas para gestionar la memoria de manera dinámica, ya que permiten insertar y eliminar objetos de forma eficiente.

Implementación de colas y pilas: Las colas y las pilas se pueden implementar utilizando listas. En lugar de usar punteros para enlazar elementos consecutivos, se pueden usar punteros para enlazar el primer y último elemento de la lista, lo que permite implementar estructuras de datos como colas y pilas.

Algoritmos de búsqueda y ordenamiento: En algunos algoritmos de búsqueda y ordenamiento, como el algoritmo de ordenamiento rápido (quicksort), se utilizan listas para almacenar temporalmente los elementos que se están ordenando.
 #### ejemplo
``` c++
// Ordenamiento de burbuja en una lista de numeros : lista enlazada simple
#include <iostream>
#include <stdlib.h>
using namespace std;

struct nodo{
       int nro;        // en este caso es un numero entero
       struct nodo *sgte;
};

typedef struct nodo *Tlista;

Tlista inicio, fin;

void generarLista( Tlista &inicio, Tlista &fin, int n ) 
{
     Tlista q, t;
     for(int i=0; i<n; i++)
     {
         q = new(struct nodo);
         q->nro = rand()%51;
         
         if(inicio==NULL)
         {
              q->sgte = inicio;
              inicio  = q;
              fin     = q;          
         }
         else
         {
              q->sgte   = fin->sgte;
              fin->sgte = q;
              fin       = q;
         }
     }
     cout<<"\n\n\tLista de numeros generados... "<<endl;
}

void mostrarLista(Tlista inicio)
{
     while(inicio != NULL)
     {
          cout <<"  " << inicio->nro ;
          inicio = inicio->sgte;
     }
}

void ordenarLista(Tlista lista)
{
     Tlista actual , siguiente;
     int t;
     
     actual = lista;
     while(actual->sgte != NULL)
     {
          siguiente = actual->sgte;
          while(siguiente!=NULL)
          {
               if(actual->nro > siguiente->nro)
               {
                    t = siguiente->nro;
                    siguiente->nro = actual->nro;
                    actual->nro = t;          
               }
               siguiente = siguiente->sgte;                    
          }    
          actual = actual->sgte;
          siguiente = actual->sgte;
           
     }
     cout<<"\n\n\tLista ordenada..."<<endl;
}

void menu()
{
    cout<<"\n\t\tORDENAMIENTO BURBUJA EN LISTA ENLAZADA SIMPLE\n\n";
    cout<<" 1. GENERAR NUMEROS                  "<<endl;
    cout<<" 2. MOSTRAR NUMEROS                   "<<endl;
    cout<<" 3. ORDENAR NUMEROS                   "<<endl;
    cout<<" 4. SALIR                            "<<endl;
    cout<<"\n INGRESE OPCION: ";
}


/*                        Funcion Principal
------------------------------------------------------------------*/
int main()
{
    inicio = NULL;
    fin    = NULL;
    
    int op;     // opcion del menu
    int num;   // elemenento a ingresar

    do
    {
        menu();  cin>> op;
        switch(op)
        {      
            case 1:
                 cout<< "\n Cantidad de numeros: "; cin>> num;
                 generarLista( inicio, fin, num );
                break;
            case 2:
                 cout<<"\n\n LISTA:\n\n";
                 mostrarLista( inicio );
                break;
            case 3:
                 ordenarLista( inicio );
                break;            
        }
        cout<<endl<<endl;
    }while(op!=4);
   return 0;
}
```
### <span style="color:red;">Arboles binarios de busqueda </span>
En programación, un árbol binario de búsqueda es una estructura de datos en la que cada nodo tiene como máximo dos hijos, llamados subárbol izquierdo y subárbol derecho. Además, cada nodo tiene un valor asociado que cumple con la propiedad de que todos los valores del subárbol izquierdo son menores que el valor del nodo y todos los valores del subárbol derecho son mayores.

Los árboles binarios de búsqueda son útiles para almacenar y buscar información de manera eficiente. Algunas aplicaciones de los árboles binarios de búsqueda incluyen:

Búsqueda y ordenamiento: Los árboles binarios de búsqueda se pueden utilizar para buscar y ordenar datos de manera eficiente. La búsqueda se realiza en tiempo O(log n) en promedio, donde "n" es el número de elementos en el árbol. Además, los árboles binarios de búsqueda permiten recorrer los elementos en orden ascendente o descendente, lo que facilita la tarea de ordenamiento.

Indexación: Los árboles binarios de búsqueda se pueden utilizar para indexar información, por ejemplo, en una base de datos. Cada nodo del árbol puede contener información sobre un registro en la base de datos, y los valores asociados a los nodos se pueden utilizar para realizar búsquedas eficientes.

Compresión de datos: Los árboles binarios de búsqueda se pueden utilizar para comprimir datos, por ejemplo, en la implementación de algoritmos de compresión de texto. La idea es construir un árbol en el que los caracteres más frecuentes se almacenen en los nodos cercanos a la raíz, y los caracteres menos frecuentes se almacenen en los nodos más profundos.

*** Codigo del arbol ***
```c++
#include <iostream>
#include <cstdlib>
using namespace std;

struct nodo{
     int nro;
     struct nodo *izq, *der;
};

typedef struct nodo *ABB;
/* es un puntero de tipo nodo que hemos llamado ABB, que ulitizaremos
   para mayor facilidad de creacion de variables */

ABB crearNodo(int x)
{
     ABB nuevoNodo = new(struct nodo);
     nuevoNodo->nro = x;
     nuevoNodo->izq = NULL;
     nuevoNodo->der = NULL;

     return nuevoNodo;
}
void insertar(ABB &arbol, int x)
{
     if(arbol==NULL)
     {
           arbol = crearNodo(x);
     }
     else if(x < arbol->nro)
          insertar(arbol->izq, x);
     else if(x > arbol->nro)
          insertar(arbol->der, x);
}

void preOrden(ABB arbol)
{
     if(arbol!=NULL)
     {
          cout << arbol->nro <<" ";
          preOrden(arbol->izq);
          preOrden(arbol->der);
     }
}

void enOrden(ABB arbol)
{
     if(arbol!=NULL)
     {
          enOrden(arbol->izq);
          cout << arbol->nro << " ";
          enOrden(arbol->der);
     }
}

void postOrden(ABB arbol)
{
     if(arbol!=NULL)
     {
          postOrden(arbol->izq);
          postOrden(arbol->der);
          cout << arbol->nro << " ";
     }
}

void verArbol(ABB arbol, int n)
{
     if(arbol==NULL)
          return;
     verArbol(arbol->der, n+1);

     for(int i=0; i<n; i++)
         cout<<"   ";

     cout<< arbol->nro <<endl;

     verArbol(arbol->izq, n+1);
}

int main()
{
    ABB arbol = NULL;   // creado Arbol

    int n;  // numero de nodos del arbol
    int x; // elemento a insertar en cada nodo

    cout << "\n\t\t  ..[ ARBOL BINARIO DE BUSQUEDA ]..  \n\n";

    cout << " Numero de nodos del arbol:  ";
    cin >> n;
    cout << endl;

    for(int i=0; i<n; i++)
    {
        cout << " Numero del nodo " << i+1 << ": ";
        cin >> x;
        insertar( arbol, x);
    }

    cout << "\n Mostrando ABB \n\n";  verArbol( arbol, 0);
    cout << "\n Recorridos del ABB";
    cout << "\n\n En orden   :  ";   enOrden(arbol);
    cout << "\n\n Pre Orden  :  ";   preOrden(arbol);
    cout << "\n\n Post Orden :  ";   postOrden(arbol);
    cout << endl << endl;
    return 0;
}
// DEBER : candida de numeros a ingresar deber ser mayor 6...
//     Task                           group
//     verArbol( arbol, 0);             1    5    9
//     enOrden(arbol);                  2    6    ...
//     preOrden(arbol);                 3    7
//     postOrden(arbol);                4    8
```
### <span style="color:red;">Automata finito determinista  </span>
 Consiste en un conjunto finito de estados, una entrada de alfabeto finito, una función de transición que describe cómo el autómata cambia de un estado a otro al leer un símbolo de entrada, un estado inicial y un conjunto de estados finales.

El AFD comienza en el estado inicial y avanza por el alfabeto de entrada, moviéndose de un estado a otro a medida que lee los símbolos de entrada. Si llega a un estado final después de procesar toda la entrada, se dice que el autómata acepta la entrada. De lo contrario, se dice que la entrada es rechazada.
 ``` c++
 void MostrarEstados(vector<int> v){
    cout << "\n\n ESTADOS DEL AUTOMATA \n\n";
    for(int i=0; i<v.size(); i++){
        cout << " " << i <<"  -->  q" << v[i] << endl;
    }
}

void IngresaAutomata(vector<int> &E, vector<char> &S, int T[MAX][MAX]){

    int numE;  // Numero de estados
    int numS;  // Numero de simbolos
    char c;

    // Generando estados
    cout << "\n Cantidad de Estados: ";
    cin >> numE;
    for(int i=0; i<numE; i++){
        E.push_back(i);
    }

    // Ingresando simbolos
    cout << "\n Cantidad de Simbolos: "; cin >> numS;
    cout << endl;
    for(int i=0; i<numS; i++){
        cout << "\t Simbolo " << i+1 << " : ";
        cin >> c;
        S.push_back(c);
    }
    sort(S.begin(),S.end());  // Ordenando simbolos

    // Ingresando tabla de transiciones
    cout << "\n INGRESE TABLA DE TRANSICIONES \n\n";
    for(int i=0; i<numE; i++){
        for(int j=0; j<numS; j++){
            cout << "\t T["<<i<<"]["<<j<<"] : ";
            cin >> T[i][j];
        }
    }

    // Mostrando tabla de transiciones
    cout << "\n\n TABLA DE TRANSICIONES \n\n";
    for(int i=0; i<numE; i++){
        for(int j=0; j<numS; j++){
            cout << "\t" << T[i][j] << "  ";
        }
        cout << endl;
    }
}

void menu(){
    cout << "\n\t\t AUTOMATA FINITO DETERMINISTA\n\n";
    cout << "\t 1. Ingresar Automata \n";
    cout << "\t 2. Verificar palabra              \n";
    cout << "\t 3. Salir                          \n";
    cout << "\t Ingrese opcion: ";
}

bool VerificarPalabra(vector<int> w, int T[MAX][MAX], int q0, vector<int>qf){

    int q, s;
    q = q0;
    bool EstadoVerificacion = false;

    for(int i=0; i<w.size(); i++){
        s = w[i];
        q = T[q][s];
    }

    for(int i=0; i<qf.size(); i++){
        if(q==qf[i]){
            EstadoVerificacion = true;
            break;
        }
    }
    return EstadoVerificacion;
}

void ConvertirPalabra(string palabra, vector<char>S, vector<int>&w){

    int i, k=0;

    while(w.size()!=palabra.length()){
        for(i=0; i<S.size(); i++){
            if(palabra[k]==S[i]){
                w.push_back(i);
            }
        }
        k++;
    }
}
/*                  Funcion Principal
--------------------------------------------------------------*/
int main()
{
    vector<int> Estados;
    vector<char> Simbolos;
    int Transiciones[MAX][MAX];
    int q0;              // Estado inicial
    vector<int>qf;       // Estados finales
    vector<int>w;
    bool AutomataIngresado = false;  // Aun no se ha ingresado automata

    int op, temp, tam;

    do{
        menu(); cin>>op;

        switch(op){

            case 1:
                Estados.clear();
                Simbolos.clear();
                qf.clear();

                IngresaAutomata(Estados, Simbolos, Transiciones);
                MostrarEstados(Estados);

                cout << "\n Ingrese estado inicial: ";
                cin >> q0;

                cout << "\n Cuantos de estados finales hay?: ";
                cin >> tam;

                cout << endl;
                for(int i=0; i<tam; i++){
                    cout << "\t Numero de estado final: ";
                    cin >> temp;
                    qf.push_back(temp);
                }

                AutomataIngresado = true;
                break;

            case 2:

                if(AutomataIngresado){
                    string palabra;
                    w.clear();
                    bool EstadoVerificacion = false;
                    cout << "\n Ingrese palabra: ";
                    cin>> palabra;

                    ConvertirPalabra(palabra, Simbolos, w);

                    EstadoVerificacion = VerificarPalabra(w, Transiciones, q0, qf);

                    if(EstadoVerificacion){
                        cout << "\n\t Palabra aceptada \n\n";
                    }
                    else{
                        cout << "\n\t Palabra no aceptada \n\n";
                    }
                }
                else{
                   cout << "\n Automata no ingresado..! \n";
                }

                break;

            case 3:
                exit(0);

            default:
                cout << "\n\tOpcion incorrecta..!\n";
        }

        //cout << "\n\n"; system("pause"); system("cls");

    }while(op!=3);
}
```
---
### <span style="color:green;">Pluss  </span>

### <span style="color:red;">try and catch </span>
Try y catch son bloques utilizados en programación para manejar excepciones (errores en tiempo de ejecución).

La estructura try-catch permite que el programa intente ejecutar un bloque de código que puede producir una excepción. Si ocurre una excepción, se lanza al bloque catch, donde se maneja y se toman las medidas necesarias.
```c++
try {
  int x = 10;
  int y = 0;
  int z = x/y;
} catch (const std::exception& e) {
  std::cout << "Se ha producido una excepción: " << e.what() << std::endl;
}
```

