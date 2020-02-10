# The pipeline of finding motifs based on deep learning framework.
# Method A
Now, there is novel deep learning model named DEESO (Yang, 2019), which has some specificities about motif prediction. The DESSO model is the first tool to use the structure shape of DNA to find motifs, and obtain the best performance compared to the existed deep learning tools,such as Deepbind, Basset, etc.
![Desso](https://bmbl.bmi.osumc.edu/downloadFiles/downloadFiles/figures/desso_workflow.png)

<center> Figure 1. Schematic overview of DESSO framework. </center>
A.The CNN model for optimizing motif detectors; B.Determination of optimal motif instances recognized by each motif detector; C. Construction of the optimized motif profile.  

If the DESSO model are utilized in your research, please cite this paper.  
[1] Jinyu Y , Anjun M , Hoppe A D , et al. Prediction of regulatory motifs from human Chip-sequencing data using a deep learning framework[J]. Nucleic Acids Research(15):15.


# Method B
The Basset model can be also used to find motifs from the genomics data, and we have located the Basset model for each transcription factor.we have selected 185 cancers related transcription factors, and compared to the existed 19 deep learning models about peaks classification. Finally, our experimental results show that the Basset model obtained the highest score for peaks prediction.

![Desso](https://bmbl.bmi.osumc.edu/downloadFiles/downloadFiles/figures/basset_workflow.png) 

<left>First, we convert the sequence to a “onehot code” representation, where each position has a four-element vector with one nucleotide’s bit set to one. Convolution layers proceed by scanning
weight matrices across the input matrix to produce an output matrix
with a row for every convolution filter and a column for every position in the
input. We apply a rectified linear unit (ReLU) nonlinear transformation to the convolution output and pool by taking the
maximum across a window of adjacent positions. The first convolution layer
operates directly on the one hot coding of the input sequence, making
the convolution filters akin to the common bioinformatics tool position
weight matrices. Subsequent convolution layers consider the orientations
and spatial distances between patterns recognized in the previous layer.
Fully connected layers perform a linear transformation of the input vector
and apply a ReLU. The final layer performs a linear transformation to a vector
of 164 elements that represents the target cells. A sigmoid nonlinearity
maps this vector to the range zero to one, where the elements serve as
probability predictions of DNase I hypersensitivity, to be compared via a loss function to the true hypersensitivity vector.
</left>

## What is DNA motif
Gene regulation mechanism is an important biological field, the gene expression is controlled by transcription factors, which is regulatory protein and bind to DNA. Each transcription factor (TF) has a specific binding site (TFBS), and each kind of TFBS also has a unique binding model, named motif.
A DNA motif is a region of DNA that regulates the expression of downstream genes located on that same molecule of DNA, i.e., a chromosome. This concept is equivalent to a DNA cis-regulatory element or cis-element. It contains the transcription factor binding sites (TFBSs) and other conserved functional elements in the 5 intergenic regions of genes. 


## What can this server do in motif analyses.
> Our server has a number of novel capabilities:  
(i) find TFs are related to cancer types</br> 
(ii) identifying the binding sites</br>
(iii) finding DNA motifs from chip-seq peaks</br>
(iv) match denovo motifs to the existed motifs</br>
(v) motif scanning</br>
(vi) annotation genes to TFs binding sites</br> 

## What kinds of formats of input sequences are suitable for this server to find motifs.
Currently we accept three kinds of motif formats, shown as follows,  
(i) bed file 
<div><pre>

</pre></div> 
(ii) fasta file 
<div><pre>

</pre></div>  
(iii) sequences
<div><pre>

</pre></div>
## What kinds of formats of motifs can be used to analysis.
Currently we accept three kinds of motif formats, shown as follows,  
(i)bed file
<div><pre>

</pre></div>
(ii) meme 
<div><pre> 
</pre></div>  
(iii) fasta  
<div><pre> 
</pre></div>
(vi) pwm
 <div><pre> 
</pre></div>
#Tutorial



### 1. For each transcription factor, preparing the input data as the bed format including peaks or sequences.

<pre><code>
CMD1:
CMD2:
CMD3:
</code></pre>  
### 2. Select the deep learning model is usded to find motifs from datasets you provide. 
<pre><code>
CMD1:
CMD2:
CMD3:
</code></pre>  

### 3. Select the output format of motifs, such as MEME, JARSPAR etc. 
<pre><code>
CMD1:
CMD2:
CMD3:
</code></pre> 
### 4. Motif analysis
<pre><code>
CMD1:
CMD2:
CMD3:
</code></pre> 


## Cite us.
[1]  
[2]



