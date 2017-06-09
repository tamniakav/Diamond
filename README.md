using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Diamond
{
    class Diamond
    {
        static void Main(string[] args)
        {
            int n = int.Parse(Console.ReadLine());

            int leftRight = (n - 1) / 2;
            int mid = 0;

            if (n == 1)
            {
                Console.WriteLine("*");
            }
            else if (n == 2)
            {
                Console.WriteLine("**");
            }
            else
            {
                for (int i = 1; i <= (n - 1) / 2; i++)
                {
                    if (n % 2 == 0)
                    {
                        if (mid < 0)
                        {
                            Console.WriteLine("{0}**{0}", new string('-', leftRight));
                        }
                        else
                        {
                            Console.WriteLine("{0}*{1}*{0}", new string('-', leftRight), new string('-', mid));
                            leftRight--;
                            mid += 2;
                        }
                    }
                    else
                    {
                        if (i == 1)
                        {
                            Console.WriteLine("{0}*{0}", new string('-', leftRight));
                            mid = 1;
                        }
                        else
                        {
                            leftRight--;
                            Console.WriteLine("{0}*{1}*{0}", new string('-', leftRight), new string('-', mid));
                            mid += 2;
                        }
                    }

                }
                leftRight = 0;
                mid = n - 2;

                for (int i = (n + 1) / 2; i >= 1; i--)
                {
                    if (n % 2 == 0)
                    {
                        Console.WriteLine("{0}*{1}*{0}", new string('-', leftRight), new string('-', mid));
                        leftRight++;
                        mid -= 2;
                    }
                    else
                    {
                        if (i == 1)
                        {
                            Console.WriteLine("{0}*{0}", new string('-', leftRight));
                            mid = 1;

                        }
                        else
                        {
                            Console.WriteLine("{0}*{1}*{0}", new string('-', leftRight), new string('-', mid));
                            leftRight++;
                            mid -= 2;
                        }
                    }
                }
            }
        }
    }
}
