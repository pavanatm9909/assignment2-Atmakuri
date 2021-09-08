# assignment2-Atmakuri

# Pavan Kumar Atmakuri

###### Guntur

The above **Guntur** was in **India**

### Travel Info
 
---
 
1. Get a cab in Maryville or Rent car to Kansas(MCI) Airport
    1. u will get best rental cars in Maryville
        1. Charge for Rental car around $150
    2. Cab charge to the airport will be $50
2. Take a flight from Kansas(MCI) to NewYork(JFK)
    1. Southwest Airlines are flexible with the timings
        1. Charge of the ticket will be $270+
    2. You can get cheap charges when you book before
3. From NewYork take flight to India Capital New Delhi
    * In Delhi Buy some Food/Drinks for Enjoyment
        * Food Needed
            * Panner Butter Masala
            * Rotis
            * Pani Puri
            * Dosa
        * Drinks Mandatory
            * Badham milk
            * Beers
            * Lassy
4. From Newdelhi go to the  Agra by car

 [About Me](AboutMe.md)

The following table describes the 4 types of food/drinks that everyone should try.<br>
It describes the food/drink item name, location and amount of money.
 
### FOOD & Drink Table
 
---
 
| Food/Drink Item | Location | Amount |
|   ----------    |  -----   |   ---- | 
| Dosa | Hyderabad | 75 |
| Corona Extra | Texas | 90 |
|BBQ | BBQ Nation| 10 |
| Punugulu | Vijayawada ST food | 20 |

### Quotes
 
---
 
> A dream is not that which you see while sleeping, it is something that does not let you sleep. - *A.P.J ABDUL KALAM*

> Folks are usually about as happy as they make their minds up to be. - *ABRAHAM LONCOLN*

### Minimum spanning tree

---

> There may be several minimum spanning trees of the same weight; in particular, if all the edge weights of a given graph are the same, then every spanning tree of that graph is minimum.<br>

> If the weights are positive, then a minimum spanning tree is in fact a minimum-cost subgraph connecting all vertices, since subgraphs containing cycles necessarily have more total weight.

``
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
``
<br>
Let's know about more about Minimum spanning tree <https://cp-algorithms.com/graph/mst_prim.html>