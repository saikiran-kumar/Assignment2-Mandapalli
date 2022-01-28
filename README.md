# Assignment2-Mandapalli
# Saikiran Kumar Mandapalli
#### Kensas City

It is a Most ***Beautiful*** place  to visit, we can find a parks at corners of each street and we can find a lot of restaurants on either side of road at 8232 Mission Road,***Prairie*** Village.

***
### Directions to Favourite place
kansas international Airport is nearest airport to this location
1. Book a car from Kansas International airport to Prairie village.
   1. Go to Address 8232 Mission Road where u can find the this famous restaurant.
2. Book a car from Missouri to kansas city
   1. From there go to address 8232 Mission Road where u can find this Restaurant.


* List of Food Items
  * Checken
  * Mutton
  * Noodles
  * Fish  

 Please click on this link to find about Me [About Me](https://github.com/saikiran-kumar/Assignment2-Mandapalli/blob/main/AboutMe.md)

***
### Sport Activities which i recommend
In this Table i recommed some sport activities to try and Location where you can find it and about the Equipment cost per person if needed for that sport/Activity.

|Name of Sport/activity|Location|Cost|
| --- | --- | --- |
|Cricket|Bearcat Ground|10$|
|Badminton|Recreation center|5$|
|Basket ball|Recreation Center|0$|

***

###  Some famous Quotes
> "The journey of a thousand miles begins with one step."-*Lao Tzu* .<br>
> "You only live once, but if you do it right, once is enough. ."-*Mae West*.

***
### Minimum Spanning Tree Algorithm
> A minimum spanning tree (MST) or minimum weight spanning tree is a subset of the edges of a connected, edge-weighted undirected graph that connects all the vertices together, without any cycles and with the minimum possible total edge weight.[1] That is, it is a spanning tree whose sum of edge weights is as small as possible.[2] More generally, any edge-weighted undirected graph (not necessarily connected) has a minimum spanning forest, which is a union of the minimum spanning trees for its connected components.<br>
> Quick Link  <https://en.wikipedia.org/wiki/Minimum_spanning_tree>


```
int n;
vector<vector<int>> adj; // adjacency matrix of graph
const int INF = 1000000000; // weight INF means there is no edge

struct Edge {
    int w = INF, to = -1;
};

void prim() {
    int total_weight = 0;
    vector<bool> selected(n, false);
    vector<Edge> min_e(n);
    min_e[0].w = 0;

    for (int i=0; i<n; ++i) {
        int v = -1;
        for (int j = 0; j < n; ++j) {
            if (!selected[j] && (v == -1 || min_e[j].w < min_e[v].w))
                v = j;
        }

        if (min_e[v].w == INF) {
            cout << "No MST!" << endl;
            exit(0);
        }

        selected[v] = true;
        total_weight += min_e[v].w;
        if (min_e[v].to != -1)
            cout << v << " " << min_e[v].to << endl;

        for (int to = 0; to < n; ++to) {
            if (adj[v][to] < min_e[to].w)
                min_e[to] = {adj[v][to], v};
        }
    }

    cout << total_weight << endl;
}

```
Quick Link for Code <https://cp-algorithms.com/graph/mst_prim.html>


