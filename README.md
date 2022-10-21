// CLASE SERIE

//PUNTO #1 Cesar Eduardo Gomez Angel AP02

public class Serie implements Entregable{
 
    // a) Constantes
     
    private final static int NUM_TEMPORADAS_DEF = 3;
    public final static int MAYOR = 1;
    public final static int MENOR = -1;
    public final static int IGUAL = 0;
  
    // b) Atributos

    private String titulo;
    private int numeroTemporadas;
    private boolean entregado;
    private String genero;
    private String creador;
  
    // d) Métodos
    
    public String getTitulo () {
        return titulo;
    }

    public void setTitulo (String titulo) {
        this.titulo = titulo;
    }

    public int getnumeroTemporadas() {
        return numeroTemporadas;
    }

    public void setnumeroTemporadas (int numeroTemporadas) {
        this.numeroTemporadas = numeroTemporadas;
    }

    public String getGenero () {
        return genero;
    }

    public void setGenero (String genero) {
        this.genero = genero;
    }

    public String getcreador () {
        return creador;
    }

    public void setcreador (String creador) {
        this.creador = creador;
    }

    public void entregar () {
        entregado = true;
    }

    public void devolver () {
        entregado = false;
    }

    public boolean isEntregado () {
        if (entregado) {
            return true;
        }
        return false;
    }
  

    public int compareTo (Object a) {
        int estado = MENOR;
  
     //Para usar el metodo get
        
        Serie ref = (Serie) a;
        if (numeroTemporadas > ref.getnumeroTemporadas ()) {
            estado = MAYOR;
        }else if (numeroTemporadas == ref.getnumeroTemporadas ()) {
            estado = IGUAL;
        }
  
        return estado;
    }

    public String toString (){
        return "Informacion de la Serie: \n" +
                "\tTitulo: "+titulo+"\n" +
                "\tNumero de temporadas: "+numeroTemporadas+"\n" +
                "\tGenero: "+genero+"\n" +
                "\tCreador: "+creador;
    }

    public boolean equals (Serie a) {
        if (titulo.equalsIgnoreCase(a.getTitulo ()) && creador.equalsIgnoreCase(a.getcreador ())) {
            return true;
        }
        return false;
    }
  
   // c) Constructores

    public Serie (){
        this("",NUM_TEMPORADAS_DEF, "", "");
    }

    public Serie (String titulo, String creador) {
        this (titulo,NUM_TEMPORADAS_DEF, "", creador);
    } 

    public Serie (String titulo, int numeroTemporadas, String genero, String creador) {
        this.titulo = titulo;
        this.numeroTemporadas = numeroTemporadas;
        this.genero = genero;
        this.creador = creador;
        this.entregado = false;
    }
  
}

----------------------------------- CLASE VIDEOJUEGOS -----------------------------------

//PUNTO #2 Cesar Eduardo Gomez Angel AP02

public class Videojuego implements Entregable{
  
    private final static int HORAS_ESTIMADAS_DEF = 100;
    public final static int MAYOR = 1;
    public final static int MENOR = -1;
    public final static int IGUAL = 0;
  
    // a) Atributos

    private String titulo;
    private int horasEstimadas;
    private boolean entregado;
    private String genero;
    private String compañia;
  
    // d) Métodos publicos

    public String getTitulo () {
        return titulo;
    }

    public void setTitulo (String titulo) {
        this.titulo = titulo;
    }

    public int getHorasEstimadas () {
        return horasEstimadas; 
    }

    public void setHorasEstimadas (int horasEstimadas) {
        this.horasEstimadas = horasEstimadas;
    }

    public String getGenero () {
        return genero;
    }

    public void setGenero (String genero) {
        this.genero = genero;
    }

    public String getcompañia () {
        return compañia;
    }

    public void setcompañia (String compañia) {
        this.compañia = compañia;
    }

    public void entregar () {
        entregado = true;
    }

    public void devolver () {
        entregado = false;
    }

    public boolean isEntregado () {
        if (entregado) {
            return true;
        }
        return false;
    }
  

    public int compareTo (Object a) {
        int estado = MENOR;
  
     //Para usar el metodo get ->
        
        Videojuego ref = (Videojuego) a;
        if (horasEstimadas > ref.getHorasEstimadas ()) {
            estado = MAYOR;
        }else if (horasEstimadas == ref.getHorasEstimadas ()) {
            estado = IGUAL;
        }
  
        return estado;
    }
 
    public String toString () {
        return "Informacion del videojuego: \n" +
                "\tTitulo: "+titulo+"\n" +
                "\tHoras estimadas: "+horasEstimadas+"\n" +
                "\tGenero: "+genero+"\n" +
                "\tcompañia: "+compañia;
    }

    public boolean equals (Videojuego a) {
        if (titulo.equalsIgnoreCase (a.getTitulo ()) && compañia.equalsIgnoreCase(a.getcompañia ())) {
            return true;
        }
        return false;
    }
  
   // c) Constructores

    public Videojuego () {
        this ("",HORAS_ESTIMADAS_DEF, "", "");
    }

    public Videojuego (String titulo, String compañia) {
        this (titulo, HORAS_ESTIMADAS_DEF, "", compañia);
    }

    public Videojuego (String titulo, int horasEstimadas, String genero, String compañia) {
        this.titulo = titulo;
        this.horasEstimadas = horasEstimadas;
        this.genero = genero;
        this.compañia = compañia;
        this.entregado = false;
    }
 
  
}

--------------------------------- CLASE ENTREGABLE ----------------------------------
//PUNTO #3 Cesar Eduardo Gomez Angel AP02

public interface Entregable {
  
    public void entregar();
  
    public void devolver();
  
    public boolean isEntregado();
  
    public int compareTo(Object a);
    
}




----------------------------- CLASE EJECUTABLE --------------------------------------------

//PUNTO #4 Cesar Eduardo Gomez Angel AP02

public class Ejecutable {
  
    public static void main (String[] args) {
  
      // a) Arrays
    	
        Serie listaSeries[] = new Serie[5];
        Videojuego listaVideojuegos[] = new Videojuego[5];
  
      // b) Valores que desee
        
        listaSeries[0] = new Serie ();
        listaSeries[1] = new Serie ("Peaky Blinders", "Otto Bathurst");
        listaSeries[2] = new Serie ("Stranger Things", 4, "Thriller", "Matt Duffer");
        listaSeries[3] = new Serie ("Dahmer", 1 ,"Thriller", "Ryan Murphy");
        listaSeries[4] = new Serie ("Breaking Bad", 5, "Thriller", "Vince Gilligan");
  
        listaVideojuegos[0] = new Videojuego ();
        listaVideojuegos[1] = new Videojuego ("Final fantasy X", 200, "Rol", "Square Enix");
        listaVideojuegos[2] = new Videojuego ("Super Mario 3DS", 30, "Plataforma", "Nintendo");
        listaVideojuegos[3] = new Videojuego ("God of war 3", "Santa Monica");
        listaVideojuegos[4] = new Videojuego ("Assasin creed 2", 30, "Aventura", "EA");
     
      // c) Entrega
        
        listaSeries[1].entregar ();
        listaSeries[4].entregar ();
        listaVideojuegos[0].entregar ();
        listaVideojuegos[3].entregar ();
  
      // d) Cuantas series y videojuegos entregados hay
  
        int entregados = 0;
  
        for (int i = 0; i < listaSeries.length; i++) {
            if (listaSeries[i].isEntregado ()) {
                entregados += 1;
                listaSeries[i].devolver ();
  
            }
            if (listaVideojuegos[i].isEntregado ()) {
                entregados += 1;
                listaVideojuegos[i].devolver ();
            }
        }
  
        System.out.println("Hay "+entregados+" articulos entregados");
  
        Serie serieMayor = listaSeries[0];
        Videojuego videojuegoMayor = listaVideojuegos[0];
  
        for (int i = 1; i < listaSeries.length; i++) {
            if (listaSeries[i].compareTo (serieMayor) == Serie.MAYOR) {
                serieMayor=listaSeries[i];
            }
            if (listaVideojuegos[i].compareTo (videojuegoMayor) == Videojuego.MAYOR) {
                videojuegoMayor = listaVideojuegos[i];
            }
  
        }
  
      // e) Mostramos
        
        System.out.println (videojuegoMayor);
        System.out.println (serieMayor);
        
    }
  
}
