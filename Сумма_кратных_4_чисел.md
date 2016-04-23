using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;

namespace Сумма_кратных_4_чисел  
{
    public partial class Сумма_кратных_4_чисел : Form  
    {
        public Сумма_кратных_4_чисел()  
        {
            InitializeComponent();
        }
        private void Сумма_кратных_4_чисел_Load(object sender, EventArgs e)
        {
        }

        private void button1_Click(object sender, EventArgs e)
        { // нахождение суммы целых положительных чисел кратных 4 из промежутка от а до b
            int n, m; // проверка введены ли пользователем целые числа или нет
            bool result = Int32.TryParse(textBox1.Text, out n);
            bool result1 = Int32.TryParse(textBox2.Text, out m);
            if (result && result1)
            { // перевод символов чисел из типа строки в целочисленный тип
                int a = Int32.Parse(textBox1.Text);
                int b = Int32.Parse(textBox2.Text);
               // проверка введенных чисел на условие а и b
                if (a < 0 && b < 0)
                { label1.Text = ("Введено два отрицательных числа, ошибка ввода"); }
                else
                {
                    if (a > b)
                    { label1.Text = ("a > b, ошибка ввода"); }
                    else
                    {
                        int sum = 0;
                        for (int k = a; k <= b; k++)
                        {
                            if (k > 0 && k % 4 == 0) sum += k;
                        }
                        label1.Text = ("Сумма положительных чисел кратных 4 =" + " " + sum);
                    }
                }
            }
            else
            {
                label1.Text = ("ошибка ввода, в окне ввода не числовые символы, либо не целые числа");
            }
        }
        private void button2_Click(object sender, EventArgs e)
        { // очищает окна ввода
            textBox1.Clear();
            textBox2.Clear();
        }
    }
}
