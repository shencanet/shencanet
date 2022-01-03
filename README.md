using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Solución_Reto_1_C
{
    class Program
    {
        
        static void Main(string[] args)
        {
            string palabra1 = " "; //palabra 1
            string palabra2 = " ";//palabra 2
            bool contador = true;//true cuando es un anagrama
            bool palabras_iguales = false;//true si es la misma palabra

           
              
              
            Console.ForegroundColor = ConsoleColor.Green;
            Console.WriteLine("------------------------------------------------------");
            Console.WriteLine("------------------------------------------------------");
            Console.WriteLine("--          SHENCANET RETO 1 ANAGRAMA C #           --");
            Console.WriteLine("--          MOUREDEV       ENERO-2022               --");
            Console.WriteLine("------------------------------------------------------");
            Console.WriteLine("------------------------------------------------------\n\n");
            Console.ForegroundColor = ConsoleColor.DarkRed;
            Console.WriteLine("introduzca primera palabra");
            Console.ForegroundColor = ConsoleColor.Yellow;
            palabra1 = Convert.ToString(Console.ReadLine());
            Console.ForegroundColor = ConsoleColor.DarkRed;
            Console.WriteLine("introduzca Segunda palabra");
            Console.ForegroundColor = ConsoleColor.Yellow;
            palabra2 = Convert.ToString(Console.ReadLine());
            //comprueba falso positivo mayusculas misma palabra
            if (palabra1.ToLower() == palabra2.ToLower())
            {

                palabras_iguales = true;


            }


            foreach (var item in palabra1)
                {
                    if (palabra1.ToLower().Count(x => x == item) != palabra2.ToLower().Count(x => x == item))
                    {
                        contador = false;
                        break;
                    }
                }
            
                if (contador == true && palabras_iguales == true)//entra si es la misma palabra 
                {
                    Console.ForegroundColor = ConsoleColor.Blue;
                    Console.WriteLine("   Es la misma palabra");
                    
                    
                }

            
                if (contador == true && palabras_iguales == false)//entra si es un anagrama
                {
                    Console.ForegroundColor = ConsoleColor.Blue;
                    Console.WriteLine("  Es un anagrama");

                }

                if (contador == false && palabras_iguales == false)//entra si no es un anagrama

                {
                    Console.ForegroundColor = ConsoleColor.Blue;
                    Console.WriteLine("   No es una anagrama");

                }


                Console.ReadKey();
            
    
        }
        
    }
}
