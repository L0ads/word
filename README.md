using System;
using System.Collections.Generic;
using System.Linq;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;
//ввод текста и подсчет символов, предлогов, слов, букв
namespace ConsoleApp17
{
    internal class Program
    {
        static void Main(string[] args)
        {

            Console.WriteLine("Введите Ваше слово: ");
            string Word = Console.ReadLine();
                     string[] Text = Word.Split(' ');
            int simb = Word.Length;
            int punc = 0;
            string[] words = Word.Split(new char[] { ' ' }, StringSplitOptions.RemoveEmptyEntries);
            string[] prepositions = {"в", "к", "до", "по", "через", "после", "в течение", "в продолжение", "в заключение", "из - за", "зa", "над", "под", "перед", "у", "возле", "мимо", "около", "Из-за", "от", "по", "ради", "благодаря", "в силу", "ввиду", "вследствие" };
             
            int a = 0, b = 0;
            foreach (var sub in Text)
            {
                Console.WriteLine($"Substring: {sub}");

            }
            foreach (string word in Word.Split(new char[] { ' ' }))
            {

                Console.WriteLine("{0}: {1}", word, word.Length);
            }

            foreach (char pr in Word)
            {
                if (char.IsPunctuation(pr))
                {
                    punc++;
                }

            }
            foreach (string word2 in words)
            {
                for (int i = 0; i < prepositions.Length; i++)
                {
                    if (prepositions[i] == word2)
                    {
                        Console.WriteLine(word2);
                        b++;
                        a--;
                    }

                }
            }
            Console.WriteLine("\nКоличество предлогов: " + b);
            Console.WriteLine("Количество знаков препинания ");
            Console.WriteLine(punc);

            Console.WriteLine("Количество слов ");

            Console.WriteLine(Text.Length);
            Console.WriteLine("Количество символов ");
            Console.WriteLine(simb);
          
            
             Console.ReadLine();

        }
    }
}
