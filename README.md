Download Link: https://assignmentchef.com/product/solved-cs436-assignment-2-inducing-decision-trees
<br>
<h1>Inducing Decision Trees</h1>

In this homework you will implement and test the decision tree learning algorithm (See Mitchell, Chapter 3).

<ul>

 <li>Download the two datasets available on myCourses. Each data set is divided into three sets: the <em>training set</em>, the <em>validation set </em>and the <em>test set</em>. Data sets are in CSV format. The first line in the file gives the attribute names. Each line after that is a training (or test) example that contains a list of attribute values separated by a comma. The last attribute is the class-variable. Assume that all attributes take values from the domain {0,1}.</li>

 <li><strong>(60 points) </strong>Implement the decision tree learning algorithm. As discussed in class, the main step in decision tree learning is choosing the next attribute to split on. Implement the following two heuristics for selecting the next attribute.

  <ol>

   <li>Information gain heuristic (See Class slides, Mitchell Chapter 3).</li>

   <li>Variance impurity heuristic described below.</li>

  </ol></li>

</ul>

Let <em>K </em>denote the number of examples in the training set. Let <em>K</em><sub>0 </sub>denote the number of training examples that have <em>class </em>= 0 and <em>K</em><sub>1 </sub>denote the number of training examples that have <em>class </em>= 1. The variance impurity of the training set <em>S </em>is defined as:

Notice that the impurity is 0 when the data is pure. The gain for this impurity is defined as usual.

<em>Gain</em>(<em>S,X</em>) = <em>V I</em>(<em>S</em>) − <sup>X </sup>Pr(<em>x</em>)<em>V I</em>(<em>S<sub>x</sub></em>)

<em>x</em>∈<em>V alues</em>(<em>X</em>)

where <em>X </em>is an attribute, <em>S<sub>x </sub></em>denotes the set of training examples that have <em>X </em>= <em>x </em>and Pr(<em>x</em>) is the fraction of the training examples that have <em>X </em>= <em>x </em>(i.e., the number of training examples that have <em>X </em>= <em>x </em>divided by the number of training examples in <em>S</em>).

<ul>

 <li><strong>(40 points) </strong>Implement reduced error post pruning algorithm on the tree from Question 1. The steps in the algorithm are given below. (See also Mitchell, Chapter 3).</li>

</ul>

<ol>

 <li>Consider each node for pruning.</li>

 <li>Pruning = removing the subtree at that node, make it a leaf andassign the most common class at that node.</li>

 <li>A node is removed if the resulting tree performs no worse then theoriginal on the <em>validation </em></li>

 <li>Nodes are removed iteratively choosing the node whose removalmost increases the decision tree accuracy on the graph.</li>

 <li>Pruning continues until further pruning is harmful.</li>

</ol>

<strong>Your implementations should be called from the command line to get complete credit. Points will be deducted if it is not possible to run all the different versions of your implementation from the command line.</strong>

<ul>

 <li>Implement a function to print the decision tree to standard output. We will use the following format.</li>

</ul>

wesley = 0 : | honor = 0 :

| | barclay = 0 : 1

| | barclay = 1 : 0 | honor = 1 :

| | tea = 0 : 0 | | tea = 1 : 1 wesley = 1 : 0

According to this tree, if wesley = 0 and honor = 0 and barclay = 0, then the class value of the corresponding instance should be 1. In other words, the value appearing before a colon is an attribute value, and the value appearing after a colon is a class value.

<ul>

 <li>Once we compile your code, we should be able to run it from the command line. Your program should take as input the following five arguments:</li>

</ul>

.program &lt;training-set&gt; &lt;validation-set&gt; &lt;test-set&gt; &lt;to-print&gt; to-print:{yes,no} &lt;prune&gt; prune:{yes, no}

It should output the accuracies on the test set for decision trees constructed using the two heuristics. If to-print equals yes, it should print the decision tree in the format described above to the standard output. • A README.txt file with detailed instructions on compiling the code.

<ul>

 <li>A document containing the accuracy on the training, validation, and test set in both datasets for decision trees constructed using the two heuristics mentioned above, with and without pruning.</li>

</ul>