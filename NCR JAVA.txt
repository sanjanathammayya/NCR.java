import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
/*<applet code="ncr" width=500 height=500> </applet> */
public class ncr extends JApplet
{
JLabel jl;
JLabel l1,l2;
public void init()
{
try
{
SwingUtilities.invokeLater(new Runnable()
{
public void run()
{
makeGUI();
}
});
}
catch(Exception e)
{
System.out.println(e);
}
}
public void makeGUI()
{
setLayout(new FlowLayout());
l1=new JLabel("Enter value for n");
l2=new JLabel("Enter value for r");
JTextField jt=new JTextField(10);
JTextField jt1= new JTextField(10);
add(l1);
add(jt);
add(l2);
add(jt1);
jl=new JLabel("");
add(jl);
JButton jb=new JButton("NCR");
jb.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ae)
{
int n=Integer.parseInt(jt.getText());
int r=Integer.parseInt(jt1.getText());
if(n>=r){
int c= fact(n)/(fact(r)*fact(n-r));
jl.setText(String.valueOf(c));
}
else
{
jl.setText("invalid input!");
}
}
int fact(int n)
{
int i,f=1;
for(i=1;i<=n;i++)
{
f=f*i;
} 
return f;
}
});
add(jb);
}
}