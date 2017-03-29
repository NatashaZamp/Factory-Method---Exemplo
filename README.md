# Factory-Method---Exemplo
Atividade 1

public abstract class Pizza {
    protected float valor;

    public float getPreco() {
        return valor;
    }
}

----------------------------------------------------------------------------------------------

public class Pequena extends Pizza {
    public Pequena() {
        valor = 15.0f;
    }
}

----------------------------------------------------------------------------------------------

public class Media extends Pizza {
    public Media() {
        valor = 20.0f;
    }
}

---------------------------------------------------------------------------------------------- 

public class Grande extends Pizza {
    public Grande() {
        valor = 30.0f;
    }
}  
----------------------------------------------------------------------------------------------

public class PizzaFactory {       
    public static Pizza getPizza( String tamanhoPizza ) {
        if( tamanhoPizza == null ) return null;
        else if( tamanhoPizza.equals("Pequena") ) return new Pequena();
        else if( tamanhoPizza.equals("Media") ) return new Media();
        else if( tamanhoPizza.equals("Grande") ) return new Grande();

        else return null;
    }   
}  

----------------------------------------------------------------------------------------------
  
public class FactoryExample {   
    public static void main( String args[] ) {   
       String tamanho = JOptionPane.showInputDialog("Tamanho da pizza:");
       Pizza pizza = PizzaFactory.getPizza(tamanho); 
        if( pizza != null ) {   
           System.out.println( "Preço: " + pizza.getPreco() );   
     }   
} 
