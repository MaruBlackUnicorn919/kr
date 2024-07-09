Задача: Написать программу, которая из имеющегося массива строк формирует новый массив из строк, длина которых меньше,
либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. 
При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.

Примеры:
[“Hello”, “2”, “world”, “:-)”] → [“2”, “:-)”]
[“1234”, “1567”, “-2”, “computer science”] → [“-2”]
[“Russia”, “Denmark”, “Kazan”] → []


using System;



class Program

{

    static void Main()

    {

        Console.WriteLine("Введите элементы массива (разделяйте пробелом):");

        string input = Console.ReadLine();

        string[] initialArray = input.Split(' '); 



        Console.WriteLine("Первоначальный массив:");

        PrintArray(initialArray);



        string[] newArray = FilterArray(initialArray); 



        Console.WriteLine("Новый массив (длина строк <= 3):");

        PrintArray(newArray);

    }



    static void PrintArray(string[] arr)

    {

        foreach (string item in arr)

        {

            Console.Write(item + " ");

        }

        Console.WriteLine();

    }


    static string[] FilterArray(string[] arr)

    {


        int count = 0;

        foreach (string item in arr)

        {

            if (item.Length <= 3)

            {

                count++;

            }

        }

        string[] newArr = new string[count];

        int index = 0;

        foreach (string item in arr)

        {

            if (item.Length <= 3)

            {

                newArr[index] = item;

                index++;

            }

        }



        return newArr;

    }

}
