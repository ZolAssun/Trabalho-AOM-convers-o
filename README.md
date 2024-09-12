/** ╬ G.A.B ╬ **/
package com.mycompany.convercao;

import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

public class Convercao {
	
    
    public static int base = 0;
    public static int baseFim = 0;
    

    
public static String dividi (String ValorDec) {
    //(10, "A", 11, "B", 12, "C", 13, "D", 14, "E", 15, "F"); 
    Map <Integer, String> Letra = new HashMap<>();
    Letra.put (10, "A");
    Letra.put (11, "B");
    Letra.put (12, "C");
    Letra.put (13, "D");
    Letra.put (14, "E");
    Letra.put (15, "F");
	
    String bag;
    String[] limpo = new String [100];
    int indice = 0;
    int comparativo;
    int valor = Integer.parseInt(ValorDec);
    for (int x = 0; x != valor;) {
        
        comparativo = (valor % baseFim);
        
       if (comparativo < 10) {  
           
           bag = Integer.toString(comparativo);                     
           limpo [indice] = bag; 
           valor  =  valor / baseFim; 
           
        }else if(comparativo >= 10){	
            
           bag = (Letra.get(comparativo));                     
           limpo [indice] = bag;                  
           valor = (valor/baseFim);           
           
        }else {     }	
       
        indice = indice + 1;       
    }
   
    String terminado = "";
    
    for ( int i =  indice - 1; i >= 0 ; i-- ) {
    
        terminado = terminado + limpo[i]  ;

    }
    
  return terminado;
}

		
public static String potencia (String ValorNum) {
    Map <String, Integer> Letra = new HashMap<>();
    Letra.put ("A", 10);
    Letra.put ("B", 11);
    Letra.put ("C", 12);
    Letra.put ("D", 13);
    Letra.put ("E", 14);
    Letra.put ("F", 15);
    
    String[] carro;
    int[] Katia = new int[15];
    int conta = 0;
    int decimalConvertido = 0;
    
    carro = ValorNum.split("");
       
    
    int anarquia = carro.length;
    

			
    //transforma a variavel carro de string para inteiro
    for (int x = 0; x < anarquia ; x++){	
        
        if (Letra.containsKey(carro[x])){
            Katia [x] = Letra.get(carro [x]);
        }
        else{
            Katia [x] = Integer.parseInt(carro [x]); 
        //System.out.println("");
        }
    }
    //System.out.println("");
    for (int hierarquia = anarquia - 1; hierarquia >= 0; hierarquia--) {  
        //System.out.println("");
        decimalConvertido = (int) (( Katia[hierarquia]*(Math.pow(base, conta))) + decimalConvertido);	
        //System.out.println("");
        conta++;
    }
    //System.out.println("");
    //System.out.println("decialcovertido potencia " + decimalConvertido);
    String fim = Integer.toString(decimalConvertido);

    return  fim;  //Integer.valueOf(decimalConvertido);
}
			
	
	public static void main(String[] args)throws IOException {
				 

// LETRAS DO HEXADECIMAL
        // DICIONARIO COM AS OPCAO DISPONIVEIS   
Map <String, Integer> escolha = new HashMap<>();
	escolha.put ("binario", 2);
	escolha.put ("ternaria", 3);
	escolha.put ("octa", 8);
	escolha.put ("decimal" , 10);
	escolha.put ("hexaDecimal", 16);

	
// V A L O R -----------------------------------------------------------------------
//System.out.println("Digite o Valor");
	String vaule = "8FFF"; //opc.nextInt();
        //System.out.println("vaule " + vaule);
//----------------------------------------------------------------------------------
	
	
// E N T R A D A -------------------------------------------------------------------
//System.out.println("Escolha Entrada - Binario Ternaria Octa Decimal HexaDecimal)");
	String entrada1 = "hexaDecimal";
//----------------------------------------------------------------------------------
	if (escolha.containsKey(entrada1)){
		base = escolha.get(entrada1);}
	//System.out.println("base " +base);
// S A I D A-----------------------------------------------------------------------
//System.out.println("Escolha a Saida- Binario Ternaria Octa Decimal HexaDecimal)");	
	String saida1 = "decimal"; 
//---------------------------------------------------------------------------------
	
	if (escolha.containsKey(saida1)) {
		baseFim = escolha.get(saida1); 
	}
        
//opc.close();
	
	if (base == 10 && baseFim != 10){
		
	String x = dividi(vaule);
	System.out.println("Primeiro if " + x);	
		
	} else if (base !=10 && base != baseFim) {
            
            if(baseFim == 10){
                System.out.println("If dentro do if " +potencia(vaule));
            return;
            }
            
            String result = potencia(vaule);
            System.out.println("segundo if " +dividi(result));
            //System.out.println ("result of dividi with var result " +dividi(result))
            
	} else {	
            System.out.println("ultimo if " + vaule);	}
	}
}

