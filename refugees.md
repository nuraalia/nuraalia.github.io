## Refugee Movement around the World

**Project description:** In this project, we used Neo4j, a graph database management system, as a platform for data on refugee movement around the world between 2010-2022. Countries were represented as nodes, which were connected to each other by “weights,” which reflected numbers of refugees moving to and from each node. Since Neo4j depicted the data in graphical format, mimicking a geographical web of countries, we were easily able to visualize how countries played a role in either producing refugees or welcoming them, and how individual countries were connected to other countries, even indirectly, in the flow of refugee movement. 

### Graph depicting refugee "emigration" (movement out of countries):

<img src="images/neo4j_slide_graph1.png?raw=true"/>

We used Neo4j’s Graph Data Science Library to apply three different algorithms to data–PageRank, Degree Centrality, and Betweenness Centrality. The Degree Centrality and Betweenness Centrality were most helpful in understanding connections between nodes; degree centrality indicated which countries had the highest number of connections to other countries, indicating either that refugees from diverse countries came there and/or refugees exited that country to many different other countries. We found that countries such as Syria and Somalia, which we knew were important refugee producers, were ranked highly by the Degree Centrality algorithm, likely because these countries had so many connections to other countries that their citizens escaped to. The Betweenness Centrality algorithm calculated which countries frequently were “bridges” between other countries, connecting them by refugee movement. While this calculation does not indicate that the same people coming in were the same leaving (and were therefore not strictly “bridges”) it did give us some sense of countries—such as Belgium and Iraq–that were highly connected to other countries by large numbers of exiting and entering refugees–and thus seemed to be attractive to some refugees but also had problems of its own, producing some refugees itself. These insights all came from being able to study data in graphical format, and apply algorithms that were written to process data in this format, which allowed us to easily discern refugee paths through the world. 

### Tables produced by algorithms: 

<img src="images/dummy_thumbnail.jpg?raw=true"/>

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
