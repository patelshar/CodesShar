import java.awt.*;

import java.awt.event.*;

import java.applet.*;

/* 
*/
public class exp extends Applet implements ActionListener
{
String msg;
Button submit,change;
TextField nameField;
Image img1;
String filenames[]={“Image1″,”Image2″,”Image3″,”Image1”};

String filetext[]={“moiates”,”plings”,”pritio”,”tibra”};

String filename;
int x;
public void init()
{
setLayout(null);
nameField = new TextField(“”,5);
submit = new Button(“Submit”);
add(nameField);
add(submit);
submit.addActionListener(this);
filename=new String(filenames[0]);
img1 = getImage(getDocumentBase(), getParameter(filename));
nameField.setBounds(100,150,100,30);
submit.setBounds(100,200,100,40);
}
public void actionPerformed(ActionEvent ae)
{
String str=nameField.getText();
if(str.equals(filetext[x]))
{
msg=”LOG IN”;
repaint();
}
else
{
msg=”WRONG TRY AGAIN”;

x=(int)((Math.random()*100)%4);
filename=new String(filenames[x]);
img1 = getImage(getDocumentBase(), getParameter(filename));
repaint();
}
}

public void paint(Graphics g)
{
g.drawImage(img1, 10,10,this);
g.drawString(msg,100,300);
}
}
