# ga_worms
Here I will keep the results of some experiments in evolution, using genetic algorithms. My genomes represent 2D proteins, built from 4 amino acids. These amino acids have have distinct torsion angles. They resemble the instructions in the snake programming language (0=a= straight, 1=t=reverse, 2=c=left, 3=g= right). The fittness of a genome is the pixel enclosed by it's protein. For graphical purposes, the 1st aminoacid is always placed at position (74,74) of a 149x149 grid. Since the lenght of a proteins is 72, no amino acids can ever fall outside of the grid. The first amino acids determines the the initial direction of the path. An **a** points right (increasing x), a **t** points left (decreasing x), a **c** points up (increasing y) and a **g** points down (decreasing y). The path of a protein can cross itself. After the path of the protein si traced on the grid, the enclosed pixels are counted. For a region of pixels to be enclosed, it has to be surrounded by the protein in all 4 directions (diagonals do no count). In theory there can be several such regions. The fittness is the sum of them all.

The optimal fittness is 289, which is a bounded square 17x17. For this to happen, the genome should specify 4 straight lines (len=17) and 4 corners. If one corner coincides with the origin (the first amino acid of the protein) there will be either 3 left turns, or 3 right turns (3 c's or 3 g's); if not, there will be 4 left turns or 4 right turns (4 c's or for g's). There are exactly 4 x 17 x 2 = 136 optimal solutions (4 directions for the first amino acid, 17 positions for the initial amino acid in a side, and 2 orientations: clockwise or anti-clockwise). 
