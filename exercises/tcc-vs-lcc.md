# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

A refresher on TCC and LCC is available in the [course notes](https://oscarlvp.github.io/vandv-classes/#cohesion-graph).

## Answer

TCC : % de connections directes sur le nombre de connections possibles  
LCC : % de connections indirectes sur le nombre de connections possibles

TCC et LCC produisent le même résultat si toutes les connections présentes entre les noeuds sont des connections directes, s'il n'y a aucune connection.

Exemple :
```
class Point {

    private double x, y;

    public Point(double x, double y) {
        this.x = x;
        this.y = y;
    }

    public double getX() {
        return this.x;
    }

    public double getY() {
        return this.y;
    }

    public Point add(Point p) {
        return new Point(x + p.x, y + p.y);
    }

    public Point sub(Point p) {
        return add(new Point(-p.x, -p.y));
    }

}
```
Ici TCC = LCC = 6/6.

LCC ne peut pas être inférieur à TCC, car les connections directes comptées pour TCC seront forcément comptabilisées dans LCC donc LCC >= TCC.

#### TCC and LCC definitions
NP = maximum number of possible connections
= N * (N − 1) / 2 where N is the number of methods
NDC = number of direct connections (number of edges in the connection graph)
NID = number of indirect connections
Tight class cohesion TCC = NDC / NP
Loose class cohesion LCC = (NDC + NIC) / NP

Source : https://www.aivosto.com/project/help/pm-oo-cohesion.html

