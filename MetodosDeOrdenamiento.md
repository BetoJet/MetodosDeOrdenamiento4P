Métodos de ordenamiento 

Ordenamineto burbuja
El ordenamiento burbuja hace múltiples pasadas a lo largo de una lista. Compara los ítems adyacentes e intercambia los que no están en orden.
Cada pasada a lo largo de la lista ubica el siguiente valor más grande en su lugar apropiado. En esencia, cada ítem “burbujea” hasta el lugar al que pertenece.

Su objetivo principal es colocar los elementos de una lista en una secuencia ordenada, lo que implicaria intercambiar de posiciones los datos en la estructura de almacenamiento. 

Este seria el ejemplo del algoritmo de ordenamiento en JAVA 

    public static int[] bubbleSort( int[] datos ){
        
        int auxiliar;
        boolean noCambios;
        
        do {
            noCambios = false;
            for ( int i = 0; i < datos.length-1; i++){
                
                if ( datos[i] > datos[i+1]){
                    auxiliar = datos[i];
                    datos[i] = datos[i+1];
                    datos[i+1] = auxiliar;
                    noCambios = true;
                }
            }
            
            System.out.println("Pasada: ");        
            imprimirDatos(datos);
        } while ( noCambios == true );
        
        return datos;
        
    }

Ordenamiento por selección 

Intercambia un solo valor por cada pasada a diferencia del burbuja que compara dos valores distintos para identificar cual es mas bajo.

Pero en este método se busca el valor mayor y a medida de que hace la pasada, lo coloca en su ubicación correcta de mas grande a mas pequeño.

En lenguaje JAVA este seria una implementación 

for (int i = 0; i < a.length - 1; i++)
       {
               int min = i;
               for (int j = i + 1; j < a.length; j++)
               {
                       if (a[j] < a[min])
                       {
                               min = j;
                       }
               }
               if (i != min) 
               {
                       int aux= a[i];
                       a[i] = a[min];
                       a[min] = aux;
               }
       }


Ordenamiento por insercción

Consiste en insertar un elemento de la lista o un arreglo en la parte ordenada de la misma, asumiendo que el primer elemento es la parte ordenada, este algoritmo comparará un elemento de la parte desordenada de la lista con los de la parte ordenada, insertando el elemento en la posición correcta dentro de la parte ordenada.

por poner un ejemplo en una lista como esta:

5,4,3,7,2

La lista tiene 5 elementos y se recorrerá 4 veces, tomaremos el segundo numero (4) para compararlo con el anterior (5), si es correcta la posición osea que es menor el 4 que el 5, se recorre el mayor a la derecha y se coloca el menor antes de el, despues tomariamos el numero 3 y lo comparamos con los dos anteriores digitos, si fuera falsa la comparación no se haria ningun movimiento, asi hasta terminar con todos los dígitos.

un ejemplo en lenguaje C seria

#include<stdio.h>
#define N 5
void mostrarLista(int*);
int main(int argc, char** argv){
	int arreglo[N]={5,2,4,1,3};
	int i,clave,j;
   //Recorrer el arreglo
	for (i = 1; i < N; i++){	   
		clave = *(arreglo+i);
		j = i-1;
		//Comparar el valor selecionado con todos los valores anteriores
		while (j >= 0 && *(arreglo+j) > clave){
			//Insertar el valor donde corresponda
			*(arreglo+j+1) = *(arreglo+j);
			j = j-1;
		}
		*(arreglo+j+1) = clave;
		mostrarLista(arreglo);
	}    
	mostrarLista(arreglo);  
	return 0;
}
//Función para mostrar estado de la lista
void mostrarLista(int *lista){
	int i;
	for (i=0; i< N; i++){
		printf("%d ",*(lista+i));
	}
	printf("\n");;
   
}