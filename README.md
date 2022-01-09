namespace Solución_Reto_1_C
{
    class Program
    {
        static void Main(string[] args)
        {
        string palabra1 = " "; //palabra 1
        string palabra2 = " ";//palabra 2
        bool contador = true;//true cuando es un anagrama
        bool palabras_iguales = false; //true si es la misma palabra
        ConsoleKeyInfo tecla;

            do { 
           
                Console.ForegroundColor = ConsoleColor.Green;//version 0.3
                Console.WriteLine("------------------------------------------------------");
                Console.WriteLine("------------------------------------------------------");
                Console.WriteLine("--          SHENCANET RETO 1 ANAGRAMA C #           --");
                Console.WriteLine("--          MOUREDEV       ENERO-2022               --");
                Console.WriteLine("--          Hora y Fecha: {0}       " + "--", DateTime.Now);
                Console.WriteLine("------------------------------------------------------");
                Console.WriteLine("------------------------------------------------------\n\n");
                Console.ForegroundColor = ConsoleColor.Magenta;
                Console.WriteLine("  Introduzca primera palabra");//pide primera palabra
                Console.ForegroundColor = ConsoleColor.Yellow;
                palabra1 = Convert.ToString(Console.ReadLine());//evita erroeres al meter numeros
                Console.ForegroundColor = ConsoleColor.Magenta;
                Console.WriteLine("  Introduzca Segunda palabra");//pide segunda palabra
                Console.ForegroundColor = ConsoleColor.Yellow;
                palabra2 = Convert.ToString(Console.ReadLine());
                //comprueba falso positivo mayusculas misma palabra
                if (palabra1.ToLower() == palabra2.ToLower())
                {
                   palabras_iguales = true;
                }
                if (palabras_iguales == false)//evita trabajo en el
                   // caso de la misma palabra
                {
                    foreach (var item in palabra1)//para todos los elementos del array
                    {
                        if (palabra1.ToLower().Count(x => x == item) != palabra2.ToLower().Count(x => x == item))
                        {
                            contador = false;
                        }
                    }
                }
                if (contador == true && palabras_iguales == true)//entra si es la misma palabra 
                {
                    Console.ForegroundColor = ConsoleColor.Blue;
                    Console.WriteLine("   Es la misma palabra");                   
                }
                if (contador == true)//entra si es un anagrama
                {
                    Console.ForegroundColor = ConsoleColor.Blue;
                    Console.WriteLine("  Es un anagrama");                    
                }
                if (contador == false)//entra si no es un anagrama
                {
                    Console.ForegroundColor = ConsoleColor.Blue;
                    Console.WriteLine("   No es una anagrama");
                }
                Console.ForegroundColor = ConsoleColor.DarkRed;
                Console.WriteLine("  \n\nPulse 1 para salir");
                tecla = Console.ReadKey(false);
                Console.Clear();
                palabras_iguales = false;//reiniciamos  bool si no posibles errores la segunda vez
                contador = true;

            } while (tecla.KeyChar != '1');    
        }        
    }
}
