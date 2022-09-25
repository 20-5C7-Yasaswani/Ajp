# Ajp
package yashu;

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.FileWriter;

import javax.swing.JButton;
import javax.swing.JComboBox;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JTabbedPane;
import javax.swing.JTextArea;
import javax.swing.JTextField;

	public class StudentRegisterForm {
	    JFrame f;
		StudentRegisterForm(){
		f=new JFrame(); 
		JTextArea ta=new JTextArea(200,200); 
		JPanel p1=new JPanel();
		JPanel p2=new JPanel();
		JPanel p3=new JPanel();
		p1.add(ta);
		JTabbedPane tabp=new JTabbedPane();
		tabp.setBounds(50,50,800,800);
		tabp.add("Register",p1); 
		JLabel l0=new JLabel("FIRST NAME:"); 
		l0.setBounds(50, 50, 200, 60); 
		p1.add(l0); p1.setLayout(null); 
		JTextField f0=new JTextField(35); 
		p1.add(f0); 
		f0.setBounds(180, 50, 200, 30);

		JLabel ll=new JLabel("LAST NAME:");	
		ll.setBounds(30, 50, 200 , 120);
		p1.add(ll);
		p1.setLayout(null);
		JTextField f1=new JTextField(35);
		p1.add(f1);
		f1.setBounds(180, 90, 250, 70);
		
		JLabel l2=new JLabel("ROLL NO");	
		l2.setBounds(60, 180, 200 , 250);
		p1.add(l2);
		p1.setLayout(null);
		JTextField f2=new JTextField(35);
		p1.add(f2);
		f2.setBounds(180, 270, 350, 60);
		
		
		JLabel l3=new JLabel("GENDER:");	
		l3.setBounds(60, 300, 150 , 400);
		p1.add(l3);
		p1.setLayout(null);
		String s1[]= {"male","female"};
		JComboBox c1=new JComboBox(s1);
		p1.add(c1);
		c1.setBounds(180, 450, 300, 90);


		JLabel l4=new JLabel("EMAIL:");	
		l4.setBounds(60, 100, 200 , 200);
		p1.add(l4);
		p1.setLayout(null);
		JTextField f4=new JTextField(50);
		p1.add(f4);
		f4.setBounds(180, 200, 300, 50);

		
		JLabel l5=new JLabel("Skills");	
		l5.setBounds(60, 200, 300 , 350);
		p1.add(l5);
		p1.setLayout(null);
		String s2[]= {"java","c++","c","python","html","javascript"};
		JComboBox c2=new JComboBox(s2);
		p1.add(c2);
		c2.setBounds(180, 350, 300, 70);

		JButton b=new JButton("SAVE");  
		b.setBounds(50,600,95,30);  
		p1.add(b);  
		JButton b1=new JButton("CLOSE");
		b1.setBounds(170,600,95,30);
		p1.add(b1);  
		
		b.addActionListener(new ActionListener()
				{
			@Override
			public void actionPerformed(ActionEvent e) {
				String s1=f0.getText();
				String s2=f1.getText();
				String s3=f2.getText();
				String s4=c1.getSelectedItem()+"";
				String s5=f4.getText();
				String s6=c2.getSelectedItem()+"";
				if (e.getSource()==b) {
			    	   try {
			    		   FileWriter w  =new FileWriter("loc.txt",true);
			    		   w.write(s1 + "\n");
			    		   w.write(s2 + "\n");
			    		   w.write(s3 + "\n");
			    		   w.write(s4 + "\n");
			    		   w.write(s5 + "\n");
			    		   w.write(s6 + "\n");
			    		   w.close();
			    	   }
			    	   catch(Exception ae) {
			    		   System.out.println(ae);
			    	   }
			       }
		   JOptionPane.showMessageDialog(f,"successfully saved " + " the details");
				}
			    		  });
			      b1.addActionListener(new ActionListener()
				  {
			@Override
			public void actionPerformed(ActionEvent e) {
				f.dispose();
			}
				});

		tabp.add("Login",p2);
		JLabel l6=new JLabel("EMAIL");	
		l6.setBounds(50, 50, 100, 60);
		p2.add(l6);
		p2.setLayout(null);
		JTextField f6=new JTextField(35);
		p2.add(f6);
		f6.setBounds(180, 50, 200, 30);

		JLabel l7=new JLabel("PASSWORD");
		l7.setBounds(30, 50, 200 , 120);
		p2.add(l7);
		p2.setLayout(null);
		JTextField f7=new JTextField(35);
		p2.add(f7);
		f7.setBounds(180, 90, 250, 70);
		JButton b2=new JButton("LOGIN");  
		b2.setBounds(50,200,95,30);  
		p2.add(b2); 

		tabp.add("Search",p3); 
		JLabel l8=new JLabel("NAME");
		l8.setBounds(30, 50, 200 , 120);
		p3.add(l8);
		p3.setLayout(null);
		JTextField f8=new JTextField(35);
		f8.setBounds(180, 90, 250, 70);
		p3.add(f8);
		JButton b3=new JButton("SEARCH");  
		b3.setBounds(50,200,95,30);  
		p3.add(b3); 
		f.add(tabp);  
		f.setSize(800,800); 
		f.setLayout(null);  
		f.setVisible(true);  
		}
		public static void main(String[] args) {
		new StudentRegisterForm();
		}
	}
