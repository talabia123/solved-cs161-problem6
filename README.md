Download Link: https://assignmentchef.com/product/solved-cs161-problem6
<br>



<ol>

 <li><strong> </strong>Consider the graph below:</li>

</ol>

Step through the Floyd-Warshall algorithm on this graph (using the order suggested by the vertex labels), and write down what your tables <em>D</em><sup>(<em>i</em>) </sup>look like for <em>i </em>= 0<em>,</em>1<em>,</em>2<em>,</em>3. (You may either code this up or do it by hand).

If it helps, here is the L<sup>A</sup>TEXcode for one such table:

begin{tabular}{c|c|c|c|}

$D^{(i)}$ &amp; 1 &amp; 2 &amp; 3 \ hline

<ul>

 <li>&amp; – &amp; – &amp; – \ hline</li>

 <li>&amp; – &amp; – &amp; – \ hline</li>

 <li>&amp; – &amp; – &amp; – \ hline</li>

</ul>

end{tabular}

<strong>[We are expecting: Your filled-in tables. No explanation is required.]</strong>

<ol start="2">

 <li><strong> </strong>Let <em>A </em>be an array of length <em>n </em>containing real numbers. A <em>longest increasing subsequence </em>(LIS) of <em>A </em>is a sequence 0 ≤ <em>i</em><sub>1 </sub><em>&lt; i</em><sub>2 </sub><em>&lt; …i<sub>` </sub>&lt; n </em>so that <em>A</em>[<em>i</em><sub>1</sub>] <em>&lt; A</em>[<em>i</em><sub>2</sub>] <em>&lt; </em>·· <em>&lt; A</em>[<em>i<sub>`</sub></em>], so that <em>` </em>is as long as possible. For example, if <em>A </em>= [6<em>,</em>3<em>,</em>2<em>,</em>5<em>,</em>6<em>,</em>4<em>,</em>8], then a LIS is <em>i</em><sub>0 </sub>= 1<em>,i</em><sub>1 </sub>= 3<em>,i</em><sub>2 </sub>= 4<em>,i</em><sub>3 </sub>= 6 corresponding to the subsequence 3<em>,</em>5<em>,</em>6<em>,</em>8. (Notice that a longest increasing subsequence doesn’t need to be unique).</li>

</ol>

In the following parts, we’ll walk through the recipe that we saw in class for coming up with DP algorithms to develop an <em>O</em>(<em>n</em><sup>2</sup>)-time algorithm for finding an LIS.

<ul>

 <li><strong> (Identify optimal sub-structure and a recursive relationship). </strong>We’ll come up with the sub-problems and recursive relationship for you, although you will have to justify it. Let <em>D</em>[<em>i</em>] be the length of the longest increasing subsequence of [<em>A</em>[0]<em>,…,A</em>[<em>i</em>]] that ends on <em>A</em>[<em>i</em>].</li>

</ul>

Explain why

<em>D</em>[<em>i</em>] = max({<em>D</em>[<em>k</em>] + 1 : 0 ≤ <em>k &lt; i,A</em>[<em>k</em>] <em>&lt; A</em>[<em>i</em>]} ∪ {1})<em>.</em>

<strong>[We are expecting: A short informal explanation. It is good practice to write a formal proof, but this is not required for credit.]</strong>

<ul>

 <li><strong> (Develop a DP algorithm to find the value of the optimal solution) </strong>Use the relationship about to design a dynamic programming algorithm returns the <em>length </em>of the longest increasing subsequence. Your algorithm should run in time <em>O</em>(<em>n</em><sup>2</sup>) and should fill in the array <em>D </em>defined above.</li>

</ul>

<strong>[We are expecting: Pseudocode. No justification is required.]</strong>

<ul>

 <li><strong> (Adapt your DP algorithm to return the optimal solution) </strong>Adapt your algorithm above to return an actual LIS, not just its length. Your algorithm should run in time <em>O</em>(<em>n</em><sup>2</sup>).</li>

</ul>

<strong>[We are expecting: Pseudocode and a short English explanation.]</strong>

<strong>Note: </strong>Actually, there is an <em>O</em>(<em>n</em>log(<em>n</em>))-time algorithm to find an LIS, which is faster than the DP solution in this exercise!

<h1>Problems</h1>

You may talk with your fellow CS161-ers about the problems. However:

<ul>

 <li>Try the problems on your own <em>before </em></li>

 <li>Write up your answers yourself, in your own words. You should never share your typed-up solutions with your collaborators.</li>

 <li>If you collaborated, list the names of the students you collaborated with at the beginning of each problem.</li>

</ul>

<ol>

 <li><strong> </strong>Consider the following problem:</li>

</ol>

Let <em>S </em>be a set of positive integers, and let <em>n </em>be a non-negative integer. Find the minimal number of elements of <em>S </em>needed to write <em>n </em>as a sum of elements of <em>S </em>(possibly with repetitions).

For example, if <em>S </em>= {1<em>,</em>4<em>,</em>7} and <em>n </em>= 10, then we can write <em>n </em>= 1 + 1 + 1 + 7 and that uses four elements of <em>S</em>. The solution to the problem would be “4.”

Your friend has devised a divide-and-conquer algorithm for to find the minimum size. Their pseudocode is below.

def minimumElements(n, S): if n == 0:

return 0

if n &lt; min(S):

return None candidates = [] for s in S:

cand = minimumElements( n-s, S ) if cand is not None: candidates.append( cand + 1 ) return min(candidates)

<ul>

 <li><strong> </strong>Prove that your friend’s algorithm is correct.</li>

</ul>

<strong>[We are expecting: A proof by induction. Make sure to state your inductive hypothesis, base case, inductive step, and conclusion.]</strong>

<ul>

 <li><strong> </strong>Argue that for <em>S </em>= {1<em>,</em>2}, your friend’s algorithm has exponential running time. (That is, running time of the form 2<sup>Ω(<em>n</em>)</sup>).</li>

</ul>

<strong>[We are expecting: An short but convincing justification, which involves the recurrence relation that the running time of your friend’s algorithm satisfies when </strong><em>S </em>= {1<em>,</em>2}<strong>.]</strong>

<ul>

 <li><strong> </strong>Turn your friend’s algorithm into a top-down dynamic programming algorithm. Your algorithm should take time <em>O</em>(<em>n</em>|<em>S</em>|).</li>

</ul>

<strong>[We are expecting: Pseudocode, and a short English description of the idea of your algorithm. You should also informally justify the running time.]</strong>

<ul>

 <li>Turn your friend’s algorithm into a bottom-up dynamic programming algorithm. Your algorithm should take time <em>O</em>(<em>n</em>|<em>S</em>|).</li>

</ul>

<strong>[We are expecting: Pseudocode, and a short English description of the idea of your</strong>

<strong>algorithm. You should also informally justify the running time.]</strong>

<ol start="2">

 <li><strong> </strong>You arrive at a river where there is a population of extremely antisocial beavers. There are <em>n </em>sites along the river that are appropriate for beaver dams, arranged linearly.</li>

</ol>

Each site has a quality, which is a real number. The higher the quality, the better the dam. However, because the beavers are antisocial, no two adjacent sites can be developed into dams. You want to find a way to assign beavers to sites<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> in order to maximize the total quality of dams built: that is, if <em>Q</em>[<em>i</em>] is the quality of site <em>i</em>, you want to maximize

{there is a dam at site <em>i</em>} · <em>Q</em>[<em>i</em>]<em>,</em>

subject to never placing dams at adjacent sites <em>i </em>and <em>i </em>+ 1.

For example, if the qualities <em>Q </em>were given by <em>Q </em>= [21<em>,</em>4<em>,</em>6<em>,</em>20<em>,</em>2<em>,</em>5], then the optimal solution would be for three beavers to build dams, at sites 0<em>,</em>3 and 5, with a total of 21 + 20 + 5 = 46 quality.

Design a dynamic programming algorithm to find the optimal locations to build dams, in the sense that it maximizes the quantity <em>X</em>. Your algorithm should take <em>Q </em>as an input, output a list of locations to build dams, and should run in time <em>O</em>(<em>n</em>) and use <em>O</em>(<em>n</em>) space.

<strong>[We are expecting: Pseudocode, and an English description of the idea of your algorithm. (In particular, what are the sub-problems you are using?) You should also give an informal argument that your algorithm is correct and has the desired running time and space.]</strong>

<ol start="3">

 <li>Once a beaver has an <em>n</em>-foot by <em>m</em>-foot site to call their own, they have to build the most excellent dam they can on that site. Billy the Beaver wants to build a <strong>rectangular </strong>dam on his site. The <em>n</em>×<em>m </em>site is divided into <em>n</em>·<em>m </em>one-foot by one-foot squares. As above, each square has a quality, which is a real number. Notice that the qualities might be negative (that is, it costs more to build on that square than the utility gained).</li>

</ol>

Billy the Beaver’s goal is to find the rectangular dam that maximizes the total quality; he doesn’t care about the size, just that it is a rectangle. If the best quality that Billy can achieve is negative, then he will choose not to build a dam at all.

<strong>For example</strong>, if <em>n </em>= 3 and <em>m </em>= 4 and the qualities on the site were as depicted below, Billy would choose to build a 2 × 3 dam with total utility 16, which is highlighted below.

In the following parts, you’ll help Billy the Beaver achieve his goal in a few different settings.

<ul>

 <li><strong> </strong>Suppose that <em>m </em>= 1. That is, the site is a <em>n</em>×1 strip, and the qualities can be represented as an array <em>B </em>of length <em>n</em>.</li>

</ul>

Design an algorithm that takes <em>B </em>as input and returns two indices <em>a,b </em>∈ {0<em>,…,n </em>− 1} so that [<em>B</em>[<em>a</em>]<em>,B</em>[<em>a </em>+ 1]<em>,…,B</em>[<em>b</em>]] is the optimal dam site. That is, <em>a </em>and <em>b </em>are numbers so that

is as large as possible. Your algorithm should run in time <em>O</em>(<em>n</em>).

<strong>[We are expecting: Pseudocode, as well as an English explanation of what your algorithm does. Also, an informal justification of the running time.]</strong>

<ul>

 <li><strong> </strong>Now suppose that <em>m </em>= <em>n</em>. That is, the site is square. Let <em>A </em>be the <em>n </em>× <em>n </em>array of qualities.</li>

</ul>

In order to be thorough, Billy the Beaver wants to compute the score he will get for <strong>every </strong>possible dam he could build. That is, he wants to make an <em>n</em>×<em>n</em>×<em>n</em>×<em>n </em>array <em>D </em>so that for all <em>x </em>≤ <em>i </em>and all <em>y </em>≤ <em>j</em>,

<em>i         j</em>

<em>D</em>[<em>x</em>][<em>y</em>][<em>i</em>][<em>j</em>] = <sup>XX</sup><em>A</em>[<em>s</em>][<em>t</em>]<em>.</em>

<em>s</em>=<em>x t</em>=<em>y</em>

The interpretation of the above is the total quality of the rectangle with lower-left corner (<em>x,y</em>) and upper-right corner (<em>i,j</em>). For other tuples (<em>x,y,i,j</em>) that don’t satisfy <em>x </em>≤ <em>i,y </em>≤ <em>j</em>, it doesn’t matter what <em>D </em>has in it.

Give an algorithm that takes <em>A </em>as input, and outputs an array <em>D</em>, in time <em>O</em>(<em>n</em><sup>4</sup>).

<strong>[We are expecting: Pseudocode, as well as an English explanation of what your algorithm does. Also, an informal justification of the running time.]</strong>

<ul>

 <li>Use your algorithm above to design an algorithm for Billy the Beaver to find the optimal rectangular dam in an <em>n </em>× <em>n </em>grid in time <em>O</em>(<em>n</em><sup>4</sup>). Your algorithm should take <em>A </em>as an input and should output <em>x,y,i,j </em>so that the rectangle {<em>x,…,i</em>}×{<em>y,…,j</em>} corresponds to an optimal dam.</li>

</ul>

(<em>x,y</em>) = (1<em>,</em>0)<em>,</em>(<em>i,j</em>) = (2<em>,</em>2)

<strong>[We are expecting: Pseudocode and a brief explanation.]</strong>

<ul>

 <li><strong> </strong>Give an algorithm that solves part (c) (finding the optimal rectangle in an <em>n </em>× <em>n </em>grid) in time <em>O</em>(<em>n</em><sup>3</sup>).</li>

</ul>

<strong>[We are expecting: Pseudocode and an English explanation of the main idea. What are the subproblems that you are using?]</strong>

<h1>Optional problem</h1>

This problem is completely optional. It’s not worth any points (not even bonus points) and we won’t grade it. However, it might be fun!

<ol start="4">

 <li>In this optional problem we’ll see how to compute Fibonacci numbers <em>even faster!</em></li>

</ol>

(a) In class, we saw the following bottom-up algorithm to compute Fibonacci numbers:

def fasterFibonacci(n): F = [1 for i in range(n+1)] for i in range(2,n+1):

F[i] = F[i-1] + F[i-2] return F[n]

This was much faster than the naive divide-and-conquer approach. But what actually is the runtime of this? Your friend says it’s <em>O</em>(<em>n</em>): we have <em>n </em>iterations of the loop and we’re just adding two numbers inside the loop. But when we look at the running times for really large <em>n</em>, it looks like this:

That doesn’t look linear! Your friend’s argument seems pretty reasonable, at least by the standards we’ve been using in this class. So what’s going on? (Note: We haven’t really been formal enough in this class to give you the tools to argue this formally. The point of this optional problem is just to get you to think a bit.) <strong>[HINT: How large is </strong><em>F</em>[<em>n</em>]<strong>? How many bits does it take to represent </strong><em>F</em>[<em>n</em>] <strong>in binary? How much time does it take to add </strong><em>F</em>[<em>n </em>− 2] + <em>F</em>[<em>n </em>− 1]<strong>?] </strong>(b) Let <em>M </em>be the matrix. Argue that

<em> .</em>

<ul>

 <li>Come up with an algorithm that uses <em>O</em>(log(<em>n</em>)) multiplications (of unbounded size) to compute <em>F</em>[<em>n</em>], when <em>n </em>is a power of 2.</li>

 <li>If you take into account how big the numbers you are multiplying are in the above, how long would your algorithm from the previous part take? What if you use a fast multiplication algorithm like Karatsuba? What if you use a multiplication algorithm which takes time <em>O</em>(<em>n</em>log(<em>n</em>)loglog(<em>n</em>)) to multiply <em>n</em>-bit numbers? (This latter thing exists, it’s called the <em>Schonhage-Strassen </em>algorithm).</li>

</ul>

<a href="#_ftnref1" name="_ftn1">[1]</a> Any beavers who don’t get sites at this river will go to another river and live happily ever after.