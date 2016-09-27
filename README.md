## Essential Details for IJSEKE2016
@[paper]


This page is to support our paper titled "Research Notes: A Proof of Concept Study for Criminal Network Analysis with Interactive Strategies(116)" revised at IJSEKE 2016.

Here are the some links for our works.
- [View on Github](https://github.com/Tongjidomainmodeling/Criminal-Network-Analysis)
- [View full version for IJSEKE2016](https://tongjidomainmodeling.github.io/Criminal-Network-Analysis/papers/seke_zhou.pdf)
- [View paper on SEKE2016](https://tongjidomainmodeling.github.io/Criminal-Network-Analysis/papers/seke_zhou.pdf)

>This paper was submitted to IJSEKE Special Issue on selected papers from SEKE2016 as research notes. Due to that research notes are limited to ten pages including figures, references and appendices, so we here provide some details that can't be fully described in the paper. We hope this can make our readers more easier to understand the process proposed in our paper and the case study with a real world criminal dataset.




[toc]

---

### Introduction
Communication data are widely used in criminal network analysis to understand direct relationships and identify implicit connections. Many efforts have been devoted to leverage those data in criminal community detection, connection strength evaluation, microstructure discovery, and suspect identification. However, the skill set required for criminal network analysis (CNA) is complex and diverse, such as the application of empirical study and domain knowledge  into the data preprocessing, criminal investigation knowledge, intelligence analysis experience, network visualization layout technique in different network scale, and social network analysis knowledge, which leads mismatching of expectation and reality on the power of data analytics. 

We proposed an interactive analysis process by observing practical workflows which involving detectives, intelligence officers, data engineers, data scientist, and domain experts, combined with the technique of social network analysis and machine learning. This process is divided into three phases according to important results in each phase, namely, 

 1.  network construction: the generation of network structure; 
 2.  metric design: the core nodes and relations;
 3.  structure observation: structures extraction in different levels. 

In each phase, the process adopted interactive strategies in order to formulate and assess hypotheses in a rapid, iterative manner---thus supporting exploration Criminal Networks (CN) with the pace of human thought.

The interactive analysis process is our chosen way to explore the CN with a case study using the mobile call log.
In the construction phase, we build the CN by data preprocessing, data cleaning and data extraction, which contains 7840 nodes and 103043 links, and then three layout are introduced to configure and depict the CN. Metric analysis phase illustrated the adoption of some classic metrics in social network analysis seeking to identify the key group members,  and the evaluation of these metrics with corresponding result. Finally, in the structure analysis phase, Fast Unfolding is used as our detection algorithm to analyse CN interactively and rapidly. Additionally, we proposed a strategy --- label supervision to control the level of the structure extracted. 
 
**Our contributions contain:**
1) suggesting a generical analytical process for Criminal Network Analysis. It can be divided into three phases.
2) proposing interactive strategies to the analytical process, such as using various visualization layouts to configure the network, reinterpreting different measures from the social network domain to the criminal network domain, and controlling the community structure level with label supervision strategy.
3) conducting a proof of concept study using mobile call logs.


### Related Work
In this section, we first provide an overview of previous works in the domain of criminal network analysis, then <span style="color:red;"> the concept of community structure and structure detection method </span> is introduced. Finally, we present a comprehension on the two relevant works about its advantages and limits.
 
 ***A.Criminal Networks Analysis***
In the last thirty years, many efforts have been used in order to analysis the Criminal Networks in a more intelligent way. 
One of the most important research in the CNA domain is due to Malcolm Sparrow, who summarized four features of the Criminal Network, namely,  
- 1) limited dimension --- CNs are often composed of few thousands entities; 
- 2) incomplete information --- criminal networks are unavoidably incomplete and erroneous;
- 3) undefined border --- it is difficult to pick out all the relations of each entity; 
- 4) dynamism --- new relations always indicate constant evolution of network structure. 

Fortunately, this contribution lead to a trend that researchers tried to analyze Criminal Networks with the techniques in the domain of the social network analysis. For instance, Baker and Faulkner studied illegal networks in the field of electric plants and Klerks concentrated on criminal organizations in the Netherlands. Silke and Brannan et al. acknowledged a slow growth in the terrorism network and examined state of the art in criminal network analysis. Arquilla and Ronfeldt summarized previous researches and proposed the concept of Netwar with its application to terrorism. 

However, in 2006, a popular work by Valdis Krebs applied network analysis in conjunction with network visualization theory to analyze the 2001-09-11 terrorist attacks. This work represents a starting point of a series of academic papers in which social network analysis methods become applied to a real-world case, differently from previous work where mostly toy models and fictitious networks were used. Krebs’ paper inspired further research in network analysis for the design of better SNA applications to support intelligence agencies in the fight against terror, and law enforcement agencies in their quest fighting crime.

***B.Community Structure and Community Detection***
Community structure is one of the most common characteristics in the study of networks, which refers to the occurrence of groups of nodes in a network that are more densely connected internally than with the rest of the network. There is one widely adopted concept to investigate the quality of this structures in the network called network modularity, which can be expressed as follows: let consider a network, represented by $G=(V,E)$, which has been partitioned into $m$ communities; its corresponding value $Q$ of network modularity is defined as:
\begin{equation*}
Q= \sum _{s=1}^m\left [\frac{l_s}{|E|} - (\frac{d_s}{2|E|})^2 \right ]
\end{equation*}
assuming $l_s$ the number of links between nodes belonging to the $s_{th}$ community and $d_s$ is the sum of the degrees of the nodes in the $s_{th}$ community. High values of $Q$ indicate high values of $l_s$ for each discovered community, yielding to communities internally densely connected and weakly coupled among each other. The process of detecting community structures in a network called community detection, and it still is regarded as a computationally difficult task. However, several methods for community detection have been proposed and applied with varying extents of success. Such as minimum-cut method, hierarchical clustering, Girvan-Newman algorithm, modularity maximization and clique based methods. 

<span style="color:red;"></span>
<span style="color:red;">Lots of works shown that community detection is proved as a powerful tool to analyze the structure in the criminal networks. Emilio et al. employed Girvan-Newman algorithm and a variant based on modularity optimization called Newman’s algorithm to detect and explore the community structures in the CNs reconstructed from phone call logs. Hamed Sarvari et al. performed a large scale analysis with clique based methods to find patterns and substructures of that network based on a publicly leaked set of customer email addresses. However, these studies and early researches somehow neglected the importance of network visualization and the interactions during the analysis process, laying emphasis on aspects related more to statical network characterization. In our research, we stress these twofold by introducing various visualization layouts and adopting crucial interactive points. </span>



###Interactive Strategies	
At present, the task of analysing Criminal Networks can not be finished purely relying on the computational analysis  or manual analysis. We examined all the analytical process in these works and we found that almost all the processes about CNA are interactive process between humans and computers, but the interactive strategies are weak, limited and even not involved obviously and deeply.  In order to gain better understanding of the process with some strong interactive strategies during the CNA, we followed 5 investigations based on a real world criminal cases and also observed a general pattern of work shared by most police officers and intelligence analysts. 

***Interactive Analysis Process***
After doing induction and summary on the workflow, we concluded that the process of CNA is a human-interaction process, and proposed an interactive analytical process for CNA. As is shown on the Figure 1. the process can be mainly divided in to three phases according to each phase's promising results, namely, **1) network construction:** the generation of network structure, **2) metric design:** the core nodes and relations, **3) structure observation:** the extraction of organization structure. And this process is supposed to assist investigator to analysis Criminal Network in an interactive way. 

![@Figure1|center](./interactive_process_927.png)


In the first phase, we clean data interactively depending on the empirical rules suggested by intelligence officers and data engineers, extract the edge table from those data, provide a format of intermediate result storage and finally perform network visualization based on the layouts selected by visualization experts. In the second phase, some metrics are introduced by SNA experts from the domain of SNA into the domain of  CNA. And there is also need to reinterpret them before employing in the context of CN, after which we might be able to obtain the ranking results. Additionally, we perform various configurations on network with each entity’s corresponding metric value. At the end of this phase, a certain evaluation is defined to suit for our CN to examine the quality of different metrics in consultation with investigation officers. The crucial point related to interaction in this phase is twofold, one is metrics selection which can measure different centrality and influence of each node, another is that we need to configure many kinds of layouts in consideration of the scale of the CN. The following phase is structure analysis of the CN. First, we need to choose a detection algorithm, taking the features of the CNs constructed during the phase one into consideration. For example, different scale might need different methods, different complexity likewise need different method. So we might need the support of SNA experts, other domain experts and programming developers. Then ascertain the extracting structure level to amplify or narrow down graph interests. Finally, a partition visualization results is produced enabling to examine the quality of the structure and even find out the hidden knowledge. Note that the three phase is an integrated whole. The previous stage outputs is regarded as the next phase of the input,  so each phase results would interfere with the next phase results. Consequently, we suggest another stage  --- feedback and optimization to ensure the effective communication between various domain experts and optimization of the whole interactive process.


### Data Set
For better illustrating the following works, here we present a brief introduction of the dataset. A brief description of the data set is shown in Table I. With a preliminarily discovery on the dataset, we find that the dataset contains 73 detailed phone call tickets, among them containing 25 known suspect and 48 persons involved with this investigation case. All phone call tickets are all in the period from 2014.6 to 2015.6 summing up all the phone call logs from all the call tickets, we got totally 1016833 logs.

对方号码,呼叫日期,呼叫时间,通话时长,呼叫类型,CGI,用户号码,姓名,身份证,地址,用户号码归属地,姓名,身份证,地址,对方号码归属地,IMEI,IMSI,用户号码通话所在地,交换机ID,位置区,小区,对方号码小区,经度,纬度,第三方号码
"	15987059080","	2014-12-02","	06:02:31","	13","	主叫","	上海市闵行区纪翟路200号","	13196779868","	","	","	","	江苏常州","	","	","	","	云南昭通","	86572802990698","	460014370046052",,,"	2188","	34653",,,,

![@edge extraction | center](./1474987154814.png)

| No      |     date |  	time   | period | from_cgi | to_cgi | source | target | name | flag
| :-------- | --------:| :------: |
| 1   |   15/3/15 |  12:10:27  | 29 | null | null | 130****8318 | 183****5959 | null | 13042138318,18318655959,2015-03-15	

![@mediate results | center](./mediate results.png)




### Network Construction
In order to assure the quality of the network construction, we proposed a generical interactive workflow to support this phase task. This workflow shows how the phone call logs are preprocessed, transformed, extracted and constructed into a network. 
Performing a good preprocessing on the dataset can get rid of the noise as much as possible, and it permits the network structure to be constructed easily without cost of quality. It allows the network metrics to depict a member more exactly and make visualization closer to the nature of the criminal communication network.  Additionally, it likewise can reduce the following analytical errors and the workload of the structure analysis phase.
Owing to the great importance of data preprocessing, we think highly of this stage. 

### Visualization Layouts
![@fisheys layout | center ](./fisheye_layout.png)

![@FR layout | center](./fr_layout.png)


### Metric Design
In order to exactly capture the influence of core members and its roles playing in the criminal organizations, we introduce a series of measures from the domain of Social Network Analysis and interpret them in the context of our certain CN. After calculating these metrics, we render the network view with different color intensity and size based upon the metric value of each entity and spotlight certain nodes. 

***A.Network Measures Reinterpretation in CNs***
<span style="color:red">**Degree centrality** measures the activity and influence by calculating the number of direct relations a node has. It is convinced that a call number with a high degree could be regarded as a hub which act as an import information channel in the communication network and a node with high activity. </span> It is defined as:
\begin{equation*}
{Dgr}_i = \frac{{d}_i} {S-1} = \frac{\sum\limits_{i\in M}m_{ij}} {S-1}
\end{equation*}
where $d_i$ is the directly links to other call numbers of a call number $i$, and $m_{ij}$ is the $ij_{th}$ element of the adjacency matrix $M$ and $S$ is the sum of the whole call numbers. $S-1$ is the normalization factor. 

<span style="color:red">**Betweenness centrality** is another indicator to measure node’s centrality which equals the number of the shortest paths from all nodes to all other nodes which pass through that node. In the context of CN, a call number with high betweenness can be regarded as broker of messages, indicating the great importance of this call number in the information transfer. Most importantly, this kind of call numbers usually connects two or more densely call number clusters, removal of them might lead to the destabilization, abruption and even destroy of the CNs.</span>
The betweenness centrality of a call number $(i)$ is redefined as:
\begin{equation*}
{Btw}_i = \frac{\sum\limits_{ j<k\in N}\frac{p_{jk}(i)}{p_{jk}}}    {(S-1)(S-2)}
\end{equation*}
where $p_{jk}$ is the total number of the shortest paths from call number $j$ to call number $k$ and the $p_{jk}(i)$ is the number of those paths that pass through call number $i$, the $(S-1)(S-2)$ is the normalization factor.

<span style="color:red">**Closeness centrality** is the reciprocal of the sum of the shortest paths between that node and all other nodes in the network. In the analysis of our CN, a high closeness indicates this call number can reach majority of the other nodes easier and faster.</span> The closeness centrality of a call number $(i)$ is redefined by the expression:
\begin{equation*}   
{Clsn}_i = (H_i)^{-1} = \frac {S-1} {\sum\limits_{j\in N}d_(i,j)}    
\end{equation*}
where $d_(i,j) $ is the distance between node $i$ with node $j$, $H_i$ is the normalized distance.

<span style="color:red">**Eigenvector centrality** defines another centrality with the consideration of the importance of their neighbours. In the framework of our CN, a call number with high eigenvector centrality means that this call number can reach a group of other call numbers easily and quickly.</span> The eigenvector centrality of a node $(i)$ is redefined as:
\begin{equation*}
{Eign}_i = \frac{1}{\alpha  } \sum\limits_{j\in L(i)}m_j = \frac{1}{\alpha} \sum\limits_{j\in N} a_{ij}x_j
\end{equation*}
where $L(i)$ is the direct link set of call number $i$, $\alpha$ is a constant, and $a_{ij}$ is the $ij_{th}$ element of the adjacency matrix $M$.

<span style="color:red">**Clustering coefficient** is a measure of the degree to the aggregation of nodes in a graph. In the context of our CN, a call number with high clustering coefficient means a high likelihood of that the direct links of the given call number can reach each other.</span> It is redefined as:
\begin{equation*}
{Clst}_i = \frac{ |{e_{jk}}|  }   {l_i(l_i-1)}
\end{equation*}
where $e_{jk}$ is the link existing in the neighbours of call number $i$ and $l_i$ is the number of direct links of the call number $i$.

<span style="color:red">**PageRank** is a variant of the eigenvector centrality measure in some degree. Our work employ this measure to the importance of a certain call number globally.</span>
It is redefined as:
\begin{equation*}
Page(i) = (1-f) + f * \sum\limits_{j \in H(i)}\frac{P_i(j)}{L_j}
\end{equation*}
where $H(i)$ are the set of call numbers directly linking to the call number $i$ , $L_j$ is the number of outgoing links in $j$ and $f$ is the damping factor. 

![@different metrics|center](./metrics.png)


***Metrics Visualization and Ranking Interpretation***
Our visualization results with the combination view of Fruchterman Reingold layout and Fisheye layout was shown on the Figure 4, and the color intensity and the size of the nodes both are rendered by their corresponding metric value. To check the usability of different metrics, we defined the hit rate of the known burglary suspect in the top 25 and top 100 rank as:

\begin{equation*}
h = \frac{n}{K} * 100\%
\end{equation*}

where $n$ is the number of known suspect in the top $K$ ranking of the corresponding metric.	
The hit rate results were shown on the Table III.

![Alt text](./table2.png)

To begin with, we can found that the degree, betweenness, eigenvector and PageRank have a similar and excellent layout view. After checking the hit rate of these metrics, it indicated that 96% of suspect belongs to the top 25 of the degree, 88% to betweenness, 84% to eigenvector, 96% to PageRank. Therefore in the top 100 ranking, they consequently got 100%. These four metrics were proved a valid measure for burglary group CN. But the remaining two metrics were not good enough and even no one suspect was ranked in the top 25 of closeness metric.  Although the hit rate of clustering coefficient only got 60% in the top 25. After we performed a manual check on the top 100, it works well. But for closeness centrality, it still got 0% in the top 100. The most likely factor resulting in this phenomenon is the way of data collection.

![Alt text](./table3.png)


### Structure Observation
After the metric design phase, we have got the core entities and important relations, but the interaction of these members is still unknown. So this section is focusing on the structure analysis of the CN and is expected to select a suitable algorithm to finish the task of community extraction rapidly and interactively.

#### Fast Unfolding with Label Supervision Strategy
In the consideration of the scale of our burglary CN, which contains 7840 nodes and 103043 links, and the demands for interactive point mentioned in the section III, Fast Unfolding has been adopted to detect the communities structure in burglary CN. Besides, we provide a  label supervision strategy to put priori knowledge and evidence into the structure extraction. Thus, the level of the community structure can be well controlled. Finally, we visualize our community results with combination of FR layout and fisheye layout. <span style="color:red"> Besides the extremely high speed, another reason why we choose Fast Unfolding algorithm is that this heuristic method provides a parameter of resolution to control the scale of the communities detected. In most situations the default value of the resolution is 1, if the value is lower, then the size of the  communities detected would become smaller, which also means that it will produce more communities. </span> If we set a higher value than the default, it means bigger communities structure and less communities. Therefore, in this way, our process can gradually increase or decrease the value of resolution in order to extract subgroups with appropriate scales in the burglary CN.

According to the analysis of the workflow shared by most police officer, we simulate the process of putting the evidence obtained into the following investigation and combined with the philosophy of supervision in machine learning technique. However, it is unknown when we should stop reduction or increasements of the resolution to gain the appropriate structure level.
we proposed a general method based on label supervision to solve this question which can be suitable for all the detection algorithm. According to detection algorithm initial stage, it can be divided into forward and reverse strategy. If the detection is start from one community to appropriate mounts of community, it means that the process of the detection is one to more, and the label supervision should inspect the partition of the nodes labeled in the same level, we called this type forward strategy; but if the algorithm is from more to less, the label supervision should inspect the mergence of the nodes in the same level. this type called reverse strategy.
The following steps describe the process of <span style="color:red"> the FU with the reverse label supervision strategies: </span>

1.  assign each node to a different community, for each node $i$,  consider the neighbours $j$ of $i$, put node $i$ to its neighbour $j$ when reaching the maximum positive gain of modularity .
2.  check the nodes labeled in the same level whether be assign into the same structure.
3.  take the communities found during the step 1 as a nodes and build a new network, then back to step 1.



In the context of the CNA, when we know several entities in a same structure level, then we label this node and examine them after each phase of the Fast Unfolding working on the network till that they are arranged into different communities. and this detection can be seen as an effective analysis.


Structure Partition Results
Three figures below descript three key procedures in the processing of the application fast unfolding based label-supervision on the burglary gang.
The Figure 5 (a) has shown the result after performing FU on the burglary criminal network with the default resolution value, where the modularity value $Q$ is 0.813 and the number of the communities is 22. The network was partitioned into different substructures and each communities, including nodes and edges, were rendered by different colors and the size of the node varies with the community scale. In order to gain a appropriately structural levels, then we marked the known suspects call number 136\*\*\*\*9699 and 182\*\*\*\*1359 shown on the Figure 6 (a) and put this knowledge into each iteration of the Fast Unfolding algorithm with a step of 0.1 reduction of the resolution. After 83 iterations, we examined these call numbers were assigned into different communities shown on the Figure 6 (b), where the resolution is 0.18, modularity is 0.778 also a high value and the number of communities is 41. This partition result is shown on the Figure 5 (b).

An another goal of this phase is to find out potential suspects in burglary gang. In the Figure 6 (c), we can find the entity with phone number of 152\*\*\*\*0099 which was rendered by brown kept large amounts of relation with top ranking criminal entities, which are 150\*\*\*\*8662, 186\*\*\*\*7777, 133\*\*\*\*2223, 133\*\*\*\*9250. Consequently this entity maybe a another member of the burglary group, we recommend such entities to officer for support the following investigation.
