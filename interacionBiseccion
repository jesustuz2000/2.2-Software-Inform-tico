package Unidad2;

import java.util.ArrayList;
public class csMetodos {
    public ArrayList<IteracionBiseccion> Biseccion(double xi, double xs, double errorDeseado, int iteraciones) {
        double fxi, fxs;
        fxi = this.funcion(xi);
        fxs = this.funcion(xs);
        double errorCalculado = 1;
        double xanterior;

        ArrayList<IteracionBiseccion> lista;
        int i = 1;

        if (fxi * fxs < 0) { //hay solución
            lista = new ArrayList<IteracionBiseccion>();

            while (i <= iteraciones && errorCalculado > errorDeseado) {
                IteracionBiseccion fila = new IteracionBiseccion();
                fila.setI(i);
                fila.setXi(xi);
                fila.setXs(xs);
                fila.setXr((xi + xs) / 2);
                
                fila.setFxr(this.funcion(fila.getXr()));
                fila.setFxi(this.funcion(fila.getXi()));
                fila.setFxs(this.funcion(fila.getXs()));

                fila.setSigno(fila.getFxi() * fila.getFxr());

                if (fila.getSigno() > 0) {
                    //mayor cambia xi
                    xanterior = xi;
                    xi = fila.getXr();
                } else {
                    //menor cambia xs;
                    xanterior = xs;
                    xs = fila.getXr();
                }
                if (i > 1) {
                    errorCalculado = Math.abs((fila.getXr()
                            - xanterior) / fila.getXr());
                    fila.setError(errorCalculado);
                } else {
                    fila.setError(errorCalculado);

                }
                lista.add(fila);

                i++;

            }
        } else {
            lista = null;
        }

        return lista;

    }
    private double getfx(double x){
        
        //return ((2500)*(x)/15)*(1-Math.exp(-(15/x)*9))-35;
        double x2=(1+x);
        
        double res=(double)Math.pow(x2,6);
        System.out.println("valor elevacion "+res);
       return 25000*(x*res/res-1)-5500;
        
    }
    private double errorRelativo(double xActual, double xAnterior){
        return Math.abs((xActual-xAnterior)/xActual);
        
    }

    private double funcion(double x) {//Formula de para hacer la operacion
        
               return ((9.8*68.1)/x)*(1-Math.exp(-(x/68.1)*10))-40;
        //return Math.pow(x, 3) + 4 * Math.pow(x, 2) - 10;
        // return Math.pow(x, 2)-0.9*x-1.52;
    }
}
