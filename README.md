using System;
using System.Collections.Generic;
using OOP;

class MainProgram
{
    public static void Main()
    {
        OOP.ManageProduct.InsertNewProduct newProduct = new OOP.ManageProduct.InsertNewProduct();

        int limit = 0;
        List<string> Name = new List<string>();
        List<int> Price = new List<int>();

        Console.WriteLine("Enter Insertion Limit: ");
        int setter = int.Parse(Console.ReadLine());

        while (limit < setter)
        {
            Console.WriteLine("Enter your new product name: ");
            string name = Console.ReadLine();
            Name.Add(name);

            Console.WriteLine("Enter your new product price: ");
            int price = int.Parse(Console.ReadLine());
            Price.Add(price);

            limit++;
        }

        Console.WriteLine("\nYour new products:");
        for (int i = 0; i < Name.Count; i++)
        {
            Console.WriteLine($"Product: {Name[i]}, Price: {Price[i]}");
        }

        Console.WriteLine("Choose the index of the product you like to remove (start from 0): ");
        int removeIndex = int.Parse(Console.ReadLine());

        if (removeIndex >= 0 && removeIndex < Name.Count)
        {
            Name.RemoveAt(removeIndex);
            Price.RemoveAt(removeIndex);
        }
        else
        {
            Console.WriteLine("Invalid index.");
        }

        Console.WriteLine("\nAfter removing product:");
        for (int i = 0; i < Name.Count; i++)
        {
            Console.WriteLine($"Product: {Name[i]}, Price: {Price[i]}");
        }

        Console.WriteLine("Insert new product name: ");
        string newName = Console.ReadLine();

        if (Name.Count >= setter)
        {
            Console.WriteLine("Cannot insert new product. Limit reached.");
        }
        else
        {
            Name.Add(newName);

            Console.WriteLine("Insert new product price: ");
            int newPrice = int.Parse(Console.ReadLine());
            Price.Add(newPrice);
        }

        Console.WriteLine("\nUpdated new product list:");
        for (int i = 0; i < Name.Count; i++)
        {
            Console.WriteLine($"Product: {Name[i]}, Price: {Price[i]}");
        }

        for (int i = 0; i < Name.Count; i++)
        {
            newProduct.InsertData(Name[i], Price[i]);
        }
    }
}
