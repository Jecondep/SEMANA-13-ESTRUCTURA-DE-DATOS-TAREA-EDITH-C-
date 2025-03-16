using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        // Información del estudiante
        Console.WriteLine("Universidad Estatal Amazónica");
        Console.WriteLine("Carrera Tecnologías de la Información");
        Console.WriteLine("Alumna: Johnny Edith Conde Paucar");
        Console.WriteLine("Paralelo: A");
        Console.WriteLine("------------------------------------");

        // 1. Crear catálogo de revistas usando una lista
        List<string> catalogoRevistas = new List<string>();

        // 2. Ingresar 10 nuevos títulos al catálogo
        catalogoRevistas.Add("Revista Ecología");
        catalogoRevistas.Add("Tecnología Hoy");
        catalogoRevistas.Add("Ciencia Amazónica");
        catalogoRevistas.Add("Innovación Digital");
        catalogoRevistas.Add("Explorador Natural");
        catalogoRevistas.Add("Mundo Programador");
        catalogoRevistas.Add("Visión Científica");
        catalogoRevistas.Add("Futuro Tecnológico");
        catalogoRevistas.Add("Naturaleza Viva");
        catalogoRevistas.Add("Informática Avanzada");

        bool continuar = true;

        while (continuar)
        {
            // 3. Mostrar menú
            Console.WriteLine("\n=== Sistema de Búsqueda de Revistas ===");
            Console.WriteLine("1. Buscar un título");
            Console.WriteLine("2. Salir");
            Console.Write("Seleccione una opción: ");

            string opcion = Console.ReadLine();

            switch (opcion)
            {
                case "1":
                    Console.Write("Ingrese el título a buscar: ");
                    string tituloBuscado = Console.ReadLine();

                    // Búsqueda iterativa
                    bool encontrado = BuscarTitulo(catalogoRevistas, tituloBuscado);

                    // Mostrar resultado
                    if (encontrado)
                        Console.WriteLine("Resultado: Encontrado");
                    else
                        Console.WriteLine("Resultado: No encontrado");
                    break;

                case "2":
                    continuar = false;
                    Console.WriteLine("¡Gracias por usar el sistema!");
                    break;

                default:
                    Console.WriteLine("Opción no válida. Intente de nuevo.");
                    break;
            }
        }
    }

    // Función de búsqueda iterativa
    static bool BuscarTitulo(List<string> catalogo, string titulo)
    {
        foreach (string revista in catalogo)
        {
            // Comparación sin distinguir entre mayúsculas y minúsculas
            if (revista.Equals(titulo, StringComparison.OrdinalIgnoreCase))
            {
                return true;
            }
        }
        return false;
    }
}
