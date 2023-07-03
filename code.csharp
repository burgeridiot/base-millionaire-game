using System;

public class Program
{
        public static class Global
   {
        public static int questionsanswered = 0;
        public static int money = 0;
    public static string[] questions = {"Bill Gates is the CEO of what company?", "What is the world's fastest animal?", "Who is the president of Spain?"};
        public static int randomnumb = 0;
        public static string[,] answers = new string[3, 4]{
                {"Microsoft", "Bosch", "Tesla", "Ubisoft"},
                {"Elephant", "Whale", "Guepardo", "Human"}, // imagine as a table
        {"Barack Obama", "Pedro Sanchez", "Emmanuel Macron", "Stepan Bandera"}
        };
        public static string[] correctanswers = {"Microsoft", "Guepardo",
"Pedro Sanchez"};
    };
        public static void DisplayQuestion(int number)
        {

                Console.WriteLine(Global.questions[number]);
                Console.WriteLine("From 1 to 4...");
                for (int i = 0; i < Global.answers.GetLength(1); i++)
                {
                        Console.WriteLine($"{i + 1}. {Global.answers[number, i]}");
                }

                return;
        }

        public static bool CheckAnswer(int number, int numb2)
        {
                bool CorrectAnswer = false;

                foreach (string answer in Global.correctanswers)
                {
                        if (Global.answers[numb2, number-1] == answer)
                        {
                                CorrectAnswer = true;
                                break;
                        }
                }

                return CorrectAnswer;
        }

        public static void Main()
        {
                Random rnd = new Random();
               
                bool start = false;
                Console.WriteLine("Would you like to be a millionaire? (S/N)");
                string starts = Console.ReadLine();
                if (starts.ToLower() == "s")
                {
                        Console.WriteLine("Good luck.");
                        start = true;
                }
                else if (starts.ToLower() == "n")
                {
                        Console.WriteLine("You just lost 5000€.");
                }

                while (start)
                {
                        Console.ForegroundColor = ConsoleColor.Black;
                        Global.randomnumb = rnd.Next(0, 3);
                        Console.WriteLine(Global.randomnumb);
                        DisplayQuestion(Global.randomnumb);
                        int answering = int.Parse(Console.ReadLine());

                        if (!CheckAnswer(answering, Global.randomnumb))
                        {
                                Console.ForegroundColor = ConsoleColor.Red;
                                Console.WriteLine($"Wrong answer! The correct answer was {Global.correctanswers[Global.randomnumb]}");
                        }
                        else if (CheckAnswer(answering, Global.randomnumb))
                        {
                                Console.ForegroundColor = ConsoleColor.Green;
                                Global.questionsanswered += 1;
                                Global.money += 100*Global.questionsanswered;
                                Console.WriteLine($"Correct answer! You currently have: {Global.money}€!");
                        }
                }
        }
}
