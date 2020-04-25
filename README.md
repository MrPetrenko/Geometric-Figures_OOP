# Geometric-Figures_OOP
This application calculates area of geometric figures
I used object oriented programming

``` 
using System;
namespace Abstract_Shape
{

   abstract class Shape
    {
        public abstract void SetData();
        public abstract void CalculatePerimetr();
        public abstract void CalculateArea();
    }

    class Square : Shape
    {
        int _side;
        
        public Square(int Side)      
        {
            _side = Side;
        }

        public int Side
        {
            set { _side = value; }
            get { return _side; }
        }

        public override void SetData()
        {
            Console.Write("Enter the side... ");
            Side = Convert.ToInt32(Console.ReadLine());
        }

        public override void CalculateArea()
        {
            Console.WriteLine($"Square`s Area == {Side * Side}");
        }

        public override void CalculatePerimetr()
        {
            Console.WriteLine($"Square`s Perimetr == {Side * 4}");
        }
    }

    class Rectangle : Shape
    {
        float _height;
        float _width;

        public Rectangle(float Height, float Width) 
        {
            _height = Height;
            _width = Width;
        }

        public float Height
        {
            set { _height = value; }
            get { return _height; }
        }

        public float Width
        {
            set { _width = value; }
            get { return _width; }
        }

        public override void SetData()
        {
            Console.Write("Enter the Height... ");
            Height = Convert.ToSingle(Console.ReadLine());

            Console.Write("Enter the Width... ");
            Width = Convert.ToSingle(Console.ReadLine());
        }

        public override void CalculatePerimetr()
        {
            Console.WriteLine($"Rectangle`s perimetr == {(Height + Width) * 2}");
        }

        public override void CalculateArea()
        {
            Console.WriteLine($"Rectangle`s area == {Height * Width}");
        }
    }

    class Circle : Shape
    {
        float _radius;

        public Circle (float Radius) 
        {
            _radius = Radius;
        }

        public float Radius
        {
            set { _radius = value; }
            get { return _radius; }
        }

        public override void SetData()
        {
            Console.WriteLine("enter radius... ");
            Radius = Convert.ToSingle(Console.ReadLine());
        }

        public override void CalculatePerimetr()
        {
            Console.WriteLine($"Perimetr`s circle {2 * System.Math.PI * Radius}");
        }

        public override void CalculateArea()
        {
            Console.WriteLine($"Area`s circle {System.Math.PI * (Radius * Radius)}");
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Console.BackgroundColor = ConsoleColor.Black;
            Console.ForegroundColor = ConsoleColor.Green;

            Shape[] figure = new Shape[10];
            int i = 0;

            string exit = "";
            do
            {
                Console.WriteLine("Hello!\nDo you want work with : \n1) Square \n2) Rectangle \n3) Circle");
                string subkey = Console.ReadLine();
                switch(subkey)
                {
                    case "1": figure[i] = new Square(0); break;
                    case "2": figure[i] = new Rectangle(0,0); break;
                    case "3": figure[i] = new Circle(0); break;
                }

                figure[i].SetData();
                figure[i].CalculatePerimetr();
                figure[i].CalculateArea();

                i++;
                
                Console.WriteLine("Continue? (y/n)");
                exit = Console.ReadLine();

            } while (exit == "y" || exit == "Y");

            Console.ReadKey();
        }
    }
}
```

