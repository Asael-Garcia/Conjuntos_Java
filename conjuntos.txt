/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package conjuntos;

import java.util.ArrayList;
import java.util.HashSet;
import java.util.Set;
import javax.swing.JOptionPane;

/**
 *
 * @author asael
 */
public class Conjuntos {

  
    public static void main(String[] args) {
       String menu=
               """
               1. Crear conjuntos
               2. Union
               3. Interseccion
               4. Diferencia entre el primer conjunto y el segundo
               5. Diferencia entre el segundo y primero
               6. Mostrar conjuntos
               7. Salir
               """;
        Set<String> conjunto1=new HashSet();
        Set<String> conjunto2=new HashSet();
        ArrayList<String> array_conjunto1=new ArrayList<String>();
        ArrayList<String> array_conjunto2=new ArrayList<String>();
        JOptionPane.showMessageDialog(null,"Hola");
        String mostrar="";
        int bandera=1;
        int bandera_conjunto=1;
        while(bandera==1){
            
            
            //MOSTRAR MENU
        String seleccion=JOptionPane.showInputDialog(null,menu);
        
 
        
        
        //decicion
        switch (seleccion){
            
            //PARA AÑADIR LOS ELEMENTOS AL CONJUNTO
            case "1":
                conjunto1.clear();
                conjunto2.clear();
                array_conjunto1.clear();
                array_conjunto2.clear();
                JOptionPane.showMessageDialog(null,"Crearas los elelemtos de los conjunto");
                int elementos=Integer.parseInt(JOptionPane.showInputDialog(null,"¿Cuantos elementos a añadir al conjunto 1?"));
                for(int i=0; i<elementos;i++){
                    String cosa=JOptionPane.showInputDialog(null,"Elemento numero "+(i+1)+" en el conjunto 1: ");
                    conjunto1.add(cosa);
                    array_conjunto1.add(cosa);
                }
                elementos=Integer.parseInt(JOptionPane.showInputDialog(null,"¿Cuantos elementos a añadir al conjunto 2?"));
                for(int i=0; i<elementos;i++){
                    String cosa=JOptionPane.showInputDialog(null,"Elemento numero "+(i+1)+" en el conjunto 2: ");
                    conjunto2.add(cosa);
                    array_conjunto2.add(cosa);
                }
                bandera_conjunto=0;
                break;
                
                //PARA LA UNION
            case "2":
                if (bandera_conjunto==0){
                    JOptionPane.showMessageDialog(null,"Crearas la union los elelemtos de los conjunto");
                    conjunto1.addAll(conjunto2);
                    mostrar="";
                    for (String x: conjunto1){
                       mostrar+= "\n"+x;
                    }
                    JOptionPane.showMessageDialog(null,"La union es de: "+mostrar); 
                    conjunto1.clear();
                    for (int i=0; i<array_conjunto1.size();i++){
                        conjunto1.add(array_conjunto1.get(i));
                    }
                }
                else{
                    JOptionPane.showMessageDialog(null,"Crea primero un conjunto para continuar");
                }
                
                
                break;
                
                
                //PARA LA INTERSECCION
            case "3":
                if (bandera_conjunto==0){
                    JOptionPane.showMessageDialog(null,"Se hará la interseccion de los conjuntos");
                conjunto1.retainAll(conjunto2);
                mostrar="";
                for (String elemento : conjunto1){
                     mostrar+="\n"+elemento;
                }
                 JOptionPane.showMessageDialog(null,"La interseccion es de: " + mostrar);
                 //borro sus datos
                conjunto1.clear();
                //y los vuelvo a rellenar
                for (int i=0; i<array_conjunto1.size();i++){
                    conjunto1.add(array_conjunto1.get(i));
                }
                } else{
                    JOptionPane.showMessageDialog(null,"Crea primero un conjunto para continuar");
                }
                
                
                break;
                
                
                //PAA LA DIFERENCIA DE A-B
            case "4":
                if (bandera_conjunto==0){
                    JOptionPane.showMessageDialog(null,"Se hará la diferencia del primer conjunto con el segundo");
                    conjunto1.removeAll(conjunto2);
                    mostrar="";
                    for (String elemento : conjunto1){
                         mostrar+="\n"+elemento;
                    }
                     JOptionPane.showMessageDialog(null,"La diferencia es de: " + mostrar);
                     //borro los datos
                    conjunto1.clear();
                    conjunto2.clear();
                    //y los vuelvo a rellenar
                    for (int i=0; i<array_conjunto1.size();i++){
                        conjunto1.add(array_conjunto1.get(i));
                    }
                    for (int i=0; i<array_conjunto2.size();i++){
                        conjunto2.add(array_conjunto2.get(i));
                    }
                } else{
                    JOptionPane.showMessageDialog(null,"Crea primero un conjunto para continuar");
                }
                
                break;
                
                
                //PARA LA DIFERENCIA DE B-A
            case "5":
                if (bandera_conjunto==0){
                    JOptionPane.showMessageDialog(null,"Se hará la diferencia del segundo conjunto con el primero");
                    conjunto2.removeAll(conjunto1);
                    mostrar="";
                    for (String elemento : conjunto2){
                         mostrar+="\n"+elemento;
                    }
                     JOptionPane.showMessageDialog(null,"La diferencia es de: " + mostrar);
                     //borro los datos
                    conjunto1.clear();
                    conjunto2.clear();
                    //y los vuelvo a rellenar
                    for (int i=0; i<array_conjunto1.size();i++){
                        conjunto1.add(array_conjunto1.get(i));
                    }
                    for (int i=0; i<array_conjunto2.size();i++){
                        conjunto2.add(array_conjunto2.get(i));
                    }
                } else{
                    JOptionPane.showMessageDialog(null,"Crea primero un conjunto para continuar");
                }
                
                
                
                break;
                
                
                //PARA MOSTRAR LOS CONJUNTOS
            case "6":
                if (bandera_conjunto==0){
                    mostrar="";
                   for (String elemento : conjunto1){
                        mostrar+="\n"+elemento;
                   }
                    JOptionPane.showMessageDialog(null,"Conjunto 1:" + mostrar); 
                    mostrar="";
                   for (String elemento : conjunto2){
                        mostrar+="\n"+elemento;
                   }
                    JOptionPane.showMessageDialog(null,"Conjunto 2: " + mostrar);
                } else{
                    JOptionPane.showMessageDialog(null,"Crea primero un conjunto para continuar");
                }
               
                break;
                
                
                //SALIR
            case "7":
                JOptionPane.showMessageDialog(null,"Nos vemos gracias");
                bandera=2;
                break;
            default:
                JOptionPane.showMessageDialog(null,"Opcion incorrecta porfavor selecciona una opcion valida");
        }
        }
        
       
    }

    
    
}
