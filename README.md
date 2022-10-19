
/**
 * Write a description of class Calculator here.
 *
 * @author (your naame)
 * @version (a version number or a date)
 */
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.awt.event.WindowAdapter;

public class Calculator extends JFrame
{
    JLabel operandlabel1 = new JLabel();
    JLabel operatorlabel = new JLabel();
    JLabel operandlabel2 = new JLabel();
    JLabel resultlabel = new JLabel();
    
    
    JTextField operandfield1 = new JTextField();
    JTextField operatorfield = new JTextField();
    JTextField operandfield2 = new JTextField();
    JTextField resultfield = new JTextField();
    
    
    JButton calculatebutton = new JButton();
    JButton exitbutton =new JButton();
    
    
    public Calculator(){
        
        
        
        
        setTitle("Simple Calculator");
        setSize(200 , 200 );
        
        addWindowListener(new WindowAdapter(){
            public void windowClosing(WindowEvent e ){
                windowclose(e);
                
            }
        });
        
        getContentPane().setLayout(new GridBagLayout());
        
        GridBagConstraints gridbag = new GridBagConstraints();
        
        
        operandlabel1.setText("Operand 1:   ");
        gridbag.gridx = 0;
        gridbag.gridy = 0;
        getContentPane().add(operandlabel1 , gridbag);
        
        
        operatorlabel.setText("Operator: ");
        gridbag.gridx = 0;
        gridbag.gridy = 1;
        getContentPane().add(operatorlabel, gridbag);
        
        operandlabel2.setText("Operand 2:   ");
        gridbag.gridx = 0;
        gridbag.gridy = 2;
        getContentPane().add(operandlabel2 , gridbag);
        
        resultlabel.setText("Result:  ");
        gridbag.gridx = 0;
        gridbag.gridy = 3;
        getContentPane().add(resultlabel,gridbag);
        
    
        
        //Textfield
        operandfield1.setText("");
        operandfield1.setColumns(8);
        gridbag.gridx = 1 ;
        gridbag.gridy = 0;
        getContentPane().add(operandfield1,gridbag);
        
        
        operatorfield.setText("");
        operatorfield.setColumns(2);
        gridbag.gridx = 1 ;
        gridbag.gridy = 1;
        getContentPane().add(operatorfield,gridbag);
        
        
        operandfield2.setText("");
        operandfield2.setColumns(8);
        gridbag.gridx = 1 ;
        gridbag.gridy = 2;
        getContentPane().add(operandfield2,gridbag);
        

         
        resultfield.setText("");
        resultfield.setColumns(8);
        gridbag.gridx = 1;
        gridbag.gridy = 3;
        getContentPane().add(resultfield,gridbag);

         addWindowListener(new WindowAdapter(){
            public void windowListener( WindowEvent e){
                
            }
                
        });
        
        
        
        
        calculatebutton.setText("Calculate");
        gridbag.gridx = 0;
        gridbag.gridy = 4;
        getContentPane().add(calculatebutton,gridbag);
        
        calculatebutton.addActionListener(new ActionListener(){
            public void actionPerformed(ActionEvent e ){
                calculatebuttonActionPerformed(e);
                
            }
        });
        
        exitbutton.setText("Exit");
        gridbag.gridx = 1; 
        gridbag.gridy = 4;
        getContentPane().add(exitbutton,gridbag);
        
        exitbutton.addActionListener(new ActionListener(){
            public void actionPerformed(ActionEvent e ){
                exitbuttonActionPerformed(e);
                
            }
        });
        
        
    }
    
     public void calculatebuttonActionPerformed(ActionEvent e){
        
        Double operand1 = Double.parseDouble(operandfield1.getText());
        Double operand2 = Double.parseDouble(operandfield2.getText());
        
           
     if (operatorfield.getText().equals("/")) {
             
            Double calculateresult = (operand1/ operand2);
            String calculate = String.valueOf(calculateresult);
            resultfield.setText(calculate);
                     
        }else if (operatorfield.getText().equals("+")){
            Double calculateresult = operand1 + operand2;
             String calculate = String.valueOf(calculateresult);
            resultfield.setText(calculate);
            
        }else if (operatorfield.getText().equals("*")){
            Double calculateresult = (operand1 * operand2);
             String calculate = String.valueOf(calculateresult);
            resultfield.setText(calculate);
            
        }else if (operatorfield.getText().equals("-")){
            Double calculateresult = (operand1 - operand2);
            String calculate = String.valueOf(calculateresult);
            resultfield.setText(calculate);
        }else{
           resultfield.setText("");
      }
           
    }
    public void windowclose(WindowEvent e){
        JFrame f;
        f = new JFrame();
        exitMain(f);    
        
    }
        

    public void exitMain(JFrame f){
        JOptionPane.showMessageDialog(f," Exit");
        System.exit(0);
        
    }  
    
    public void exitbuttonActionPerformed(ActionEvent e){
        JFrame f;
        f = new JFrame();
        exitMain(f);
    }
     
    public static void main(String[] args){
        
    new Calculator().show();
    
    }
    

}
