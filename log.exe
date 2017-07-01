using System;
using System.Data;
using System.Data.SqlClient;
using System.Configuration;
protected void btnSubmit_Click(object sender, EventArgs e)
{
SqlConnection con = new SqlConnection(ConfigurationManager.ConnectionStrings["dbconnection"].ConnectionString);
con.Open();
SqlCommand cmd = new SqlCommand("select * from UserInformation where UserName =@username and Password=@password",con);
cmd.Parameters.AddWithValue("@username", txtUserName.Text);
cmd.Parameters.AddWithValue("@password", txtPWD.Text);
SqlDataAdapter da = new SqlDataAdapter(cmd);
DataTable dt = new DataTable();
da.Fill(dt);
if(dt.Rows.Count>0)
{
Response.Redirect("Details.aspx");
}
else
{
ClientScript.RegisterStartupScript(Page.GetType(), "validation", "<script language='javascript'>alert('Invalid Username and Password')</script>");
}
}
