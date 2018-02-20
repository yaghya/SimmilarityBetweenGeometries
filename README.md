## **SimmilarityBetweenGeometries**
## (Implemented the following as the competency test for **Boost.Geometry** Gsoc '18)

# Pseudo code for finding Coupling Distance <br />
(frechet distance for curve formed by discrete points)
Function dF(P, Q): real;<br />
input:polygonal curves P= (u1, . . . , up) and Q= (v1, . . . , vq).<br />
return:δdF(P, Q)<br />
ca:array[1..p,1..q] of real;<br />
function c(i, j): real;<br />
	begin<br />
		if ca(i, j)>−1 then return ca(i, j)<br />
		elsif i= 1 and j= 1 then ca(i, j) :=d(u1, v1)<br />
		elsif i >1 and j= 1 then ca(i, j) := max{c(i−1,1), d(ui, v1)}<br />
		elsif i= 1 and j >1 then ca(i, j) := max{c(1, j−1), d(u1, vj)}<br />
		elsif i >1 and j >1 then ca(i, j) :=max{min(c(i−1, j), c(i−1, j−1), c(i, j−1)), d(ui, vj)}<br />
		else ca(i, j)=∞<br />
		return ca(i, j);<br />
	end;<br />
/* function c */<br /><br />
begin<br />
	for i = 1 to p do for j= <br />1 to q do ca(i, j) :=−1.0;<br />
	return c(p, q);<br />
e.<br />

# How to use this header: 
  1. Clone/Download this directory (or the file "FrechetDistance.hpp")
  1. Include the header in your code by specifying the absolute or relative path **( #include"/file_path/FrechetDistance.hpp")**