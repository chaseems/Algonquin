package testOne;

import javax.swing.JFrame;
import javax.swing.JButton;
import javax.swing.JPanel;
import javax.swing.JTextField;
import java.awt.*;
import java.awt.event.ComponentAdapter;
import java.awt.event.ComponentEvent;
import java.util.ArrayList;

/**
 * Created by chase on 2015-09-19.
 * OOP with Design Patterns- Assignment 01
 */
public class Calculator1 {

    /** build all component */
    JFrame frame = new JFrame("CalculatorGraphic");
    String[] buttonText = {"7", "8", "9", "/",
                            "4", "5", "6", "*",
                            "1", "2", "3", "-",
                            "0", ".", "=", "+"};
    ArrayList<JButton> buttonArrayList = new ArrayList<JButton>();
    JPanel buttonPanel = new JPanel();
    JTextField textField = new JTextField();
    JPanel framePanel = new JPanel();

    /** Class constructor */
    public Calculator1(){
        /*new all button*/
        for (int i=0; i<buttonText.length; i++){
            JButton button = new JButton(buttonText[i]);
            buttonArrayList.add(button);
        }

        /*add 16 button to buttonPanel with GridLayout*/
        buttonPanel.setLayout(new GridLayout(4, 4, 2, 2));
        for (int i = 0; i < buttonText.length; i++) {
            buttonPanel.add(buttonArrayList.get(i));
        }
        buttonArrayList.get(0).setPreferredSize(new Dimension(80, 100));

        /*set textPanel's layout, and add textField to textPanel*/
        framePanel.setLayout(new BorderLayout());
        framePanel.add(textField, BorderLayout.NORTH);
        framePanel.add(buttonPanel, BorderLayout.CENTER);

        /* set up the main frame */
        frame.add(framePanel);
        frame.pack();
        frame.setVisible(true);

        /* listen the frame changing, then change the button text size*/
        frame.addComponentListener(new ComponentAdapter() {
            @Override
            public void componentResized(ComponentEvent e) {
                /* set button's font*/
                int buttonFontWidth = buttonArrayList.get(0).getWidth();
                if(buttonFontWidth>buttonArrayList.get(0).getHeight()){
                    buttonFontWidth = buttonArrayList.get(0).getHeight();
                }
                buttonFontWidth /= 2;

                /*set textField's width and height*/
                int textPanelWidth = framePanel.getWidth();
                int textPanelHeight = framePanel.getHeight()/9;
                textField.setPreferredSize(new Dimension(textPanelWidth, textPanelHeight));
                textField.setFont(new Font("Calibri", Font.PLAIN, textPanelHeight));
                textField.setBackground(Color.gray);

                    /*set button's font*/
                for (int i = 0; i < buttonArrayList.size(); i++) {
                    buttonArrayList.get(i).setFont(new Font("Calibri", Font.PLAIN, buttonFontWidth));
                }
            }//end of componentResized()
        });//end of listener
    }//end of constructor
}//end of class Calculator1

