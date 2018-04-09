# Calender
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Day26_Calender
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter year");
            int year = Int32.Parse(Console.ReadLine());
            
            for(int month = 1; month <= 12; month++)
            {                                
                PrintCalender(year, month);
                Console.WriteLine();
            }

            //Console.ResetColor();
            
            Console.ReadKey();
        }

            int[] day={1,7,18,25};
            int[] mon={3,7,10,12};


        //a fully matured code
        static void PrintCalender(int year, int month)
        {
            string[] weekdays = { "Su", "Mo", "Tu", "We", "Th", "Fr", "Sa" };
            int[] monthDays = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
            string[] months = { "Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"};
            int dayCount = 0;
            int weekdaycount;
            if (year % 4 == 0)
            {
                monthDays[1] = monthDays[1] + 1;
            }
           
            int monthWeekDayStart;
            DateTime dt = new DateTime(year, month, 1);
            Console.WriteLine(months[month - 1]);

            for (int i = 0; i <= weekdays.Length - 1; i++)
            {
                Console.Write(weekdays[i] + " ");

            }
            Console.WriteLine();

            monthWeekDayStart = ((int)dt.DayOfWeek) + 1;// dt.DayOfWeek.ToString();
                                                        
            for (int j = 1; j <= monthWeekDayStart - 1; j++)
            {
                Console.Write("  " + " ");
            }
            weekdaycount = monthWeekDayStart - 1;
            //Console.ForegroundColor = ConsoleColor.Red;
            for (int i = 1; i <= monthDays[month - 1]; i++)
            {
                dayCount++;
                weekdaycount++;
                Console.Write(i.ToString("00") + " ");
                
                if (weekdaycount % 7 == 0)
                {
                    weekdaycount=0;
                    Console.WriteLine();
                }

            }
        }
    }
}
