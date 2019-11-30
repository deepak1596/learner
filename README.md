using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using System.Data.SqlClient;

namespace society
{
    public partial class Form2 : Form
    {
        SqlConnection sqlCon = new SqlConnection(@"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=C:\USERS\AADITRI RAI\SOURCE\REPOS\SOCIETY\SOCIETY\SOCIETY.MDF;Integrated Security=True;Connect Timeout=30");
        
        public Form2()
        {
            InitializeComponent();
        }
        public static string SetValueForText = "";
        public static string SetValueForText1 = "";
        public static string SetValueForText2 = "";
        public static string SetValueForText3 = "";
        public static string SetValueForText5 = "";
        public static string SetValueForText6 = "";
        public static string SetValueForText7 = "";
        public static string SetValueForText8 = "";
        public static string SetValueForText9 = "";
        public static string SetValueForText10 = "";
        public static string SetValueForText4 = "";
        public static string SetValueForText11 = "";



        private void button1_Click(object sender, EventArgs e)
        {
            this.Hide();
            Form1 d = new Form1();
                d.ShowDialog();
        }

        private void button2_Click(object sender, EventArgs e)
        {
            
            try
            {
               

                if (sqlCon.State == ConnectionState.Closed)
                


                   
                
                    sqlCon.Open();
                    SqlCommand sqlCmd = new SqlCommand("RHSA", sqlCon);
                    sqlCmd.CommandType = CommandType.StoredProcedure;
                    sqlCmd.Parameters.AddWithValue("project_name", textBox1.Text);
                    sqlCmd.Parameters.AddWithValue("configuration", textBox2.Text);
                    sqlCmd.Parameters.AddWithValue("price", textBox3.Text);
                    sqlCmd.Parameters.AddWithValue("Address", textBox4.Text);
                    sqlCmd.Parameters.AddWithValue("floor_rise_prize", textBox12.Text);
                    sqlCmd.Parameters.AddWithValue("floor", textBox11.Text);
                    sqlCmd.Parameters.AddWithValue("possion", textBox10.Text);
                    sqlCmd.Parameters.AddWithValue("project_developer", textBox9.Text);
                    sqlCmd.Parameters.AddWithValue("status", textBox8.Text);
                    sqlCmd.Parameters.AddWithValue("amenities", textBox5.Text);
                    sqlCmd.Parameters.AddWithValue("sales_person_contact_no", textBox6.Text);
                    sqlCmd.Parameters.AddWithValue("1bhk", checkBox1.Checked);
                    sqlCmd.Parameters.AddWithValue("2bhk", checkBox2.Checked);
                    sqlCmd.Parameters.AddWithValue("3bhk", checkBox3.Checked);
                    sqlCmd.Parameters.AddWithValue("4_5bhk", checkBox4.Checked);
                    sqlCmd.Parameters.AddWithValue("@SrNo", 0);



                    sqlCmd.ExecuteNonQuery();
                    MessageBox.Show("successfully");
               


            
            }
            catch (Exception ex)
            {
                MessageBox.Show(ex.Message, "error");
            }
            finally
            {
                sqlCon.Close();
            }
        }

       

        private void Form2_Load(object sender, EventArgs e)
        {
           
            
           
        }

        private void label4_Click(object sender, EventArgs e)
        {

        }

        private void groupBox1_Enter(object sender, EventArgs e)
        {

        }

      
    }
}
    

