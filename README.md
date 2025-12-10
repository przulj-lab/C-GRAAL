# C-GRAAL: Common-Neighbors-Based Global GRAph ALignment

A global graph alignment algorithm for biological networks based on common neighbors.

## Authors

- Vesna Memisevic
- Natasa Przulj

**Corresponding Author:** Prof. Natasa Przulj  
📧 natasa.przulj@mbzuai.ac.ae

## Publication

V. Memišević and N. Pržulj, "C-GRAAL: Common-Neighbors-Based Global GRAph ALignment of Biological Networks," *Integr. Biol.*, 4:734-743, 2012. PMCID: 22234340

## Resources

### Executables
- **[C-GRAAL Unix64 version](link-to-executable)**

### Supplementary Material
- **[Supplementary Material PDF](link-to-pdf)**

### Networks
- **[Yeast-Human](link)**
- **[Human-Pathogen](link)**
- **[Bacteria](link)**
- **[Herpesviruses](link)**

### Alignments
- **[Best Alignments](link)**

### Predictions
- **[Yeast-Human](link)**
- **[F. tularensis - H. sapiens](link)**
- **[B. anthracis - H. sapiens](link)**
- **[Y. pestis - H. sapiens](link)**
- **[C. jejuni - E. coli](link)**
- **[Mesorhizobium loti - Synechocystis sp PCC6803](link)**

*Note: If download links don't work when clicked, copy and paste the URLs directly into your browser's address bar.*

## Installation

```bash
# Download and unpack C-GRAAL
git clone https://github.com/przulj-lab/C-GRAAL/
cd CGRAAL_unix64
chmod +x CGRAAL_unix64
```

## Requirements

- Unix/Linux 64-bit system
- Networks in LEDA `.gw` format
- Node similarity file

## Usage

### Basic Command

```bash
./CGRAAL_unix64 net1.gw net2.gw similarity.file output1.file output2.file
```

### Parameters

- `net1.gw` - First network (LEDA .gw format)
- `net2.gw` - Second network (LEDA .gw format)
- `similarity.file` - Node similarity scores in format: `nodeXNet1 nodeYNet2 similarity`
- `output1.file` - Alignment output with node numbers: `node_Net1 node_Net2`
- `output2.file` - Alignment output with node names: `node_Net1 node_Net2`

### Important Note

⚠️ **The number of nodes in the first network must not be greater than the number of nodes in the second network!**

### Example

```bash
./CGRAAL_unix64 yeast.gw human.gw blast_scores.txt alignment_numbers.txt alignment_names.txt
```

## Input File Formats

### Network Format

C-GRAAL accepts networks in LEDA `.gw` format.

### Similarity File Format

```
nodeA_net1 nodeB_net2 0.95
nodeC_net1 nodeD_net2 0.87
nodeE_net1 nodeF_net2 0.76
```

## Converting Edge Lists to LEDA Format

If your network is in edge list format:
```
node1 node2
node3 node4
...
```

Use the provided `list2leda` script:

```bash
./list2leda edgelist.txt >> graph.gw
```

**Note:** Self-loops, directionality, and double edges will be ignored during conversion.

## Help

Display usage directions:
```bash
./CGRAAL_unix64
```

## Visualization Results

C-GRAAL produces alignments visualized as largest common connected components for various species pairs:

- Yeast-Human alignment
- C. jejuni-E. coli alignment
- Mesorhizobium loti-Synechocystis sp PCC6803 alignment
- F. tularensis - H. sapiens alignment
- B. anthracis - H. sapiens alignment
- Y. pestis - H. sapiens alignment

## Other Network Alignment Algorithms

- **[GRAAL](http://www0.cs.ucl.ac.uk/staff/natasa/GRAAL/)** - GRaph ALigner
- **[MI-GRAAL](http://www0.cs.ucl.ac.uk/staff/natasa/MI-GRAAL/)** - Multi-species graph alignment
- **[IsoRank and IsoRankN](http://www.ncbi.nlm.nih.gov/pubmed/18506038)**
- **[PathBlast](http://www.ncbi.nlm.nih.gov/pubmed/14993207)**
- **[GraphM package](https://www.ncbi.nlm.nih.gov/pubmed/19648138)**
- **[Natalie](http://www.molgen.mpg.de/~natalie/)**

## Important Notes

### P-value Calculations

All p-values presented in the paper were calculated using **MATLAB 2007**. Newer MATLAB versions use a different output precision format, which may result in slightly different p-values:

- MATLAB 2007 format: `1.7E-9`
- Newer versions format: `0.0`

This is due to precision differences, not algorithmic changes.

## Citation

If you use this code or data in your research, please cite:

```
V. Memišević and N. Pržulj
C-GRAAL: Common-Neighbors-Based Global GRAph ALignment of Biological Networks
Integrative Biology, 4:734-743, 2012
PMCID: 22234340
```

## Contact

For questions or issues, please contact Prof. Natasa Przulj at natasa.przulj@mbzuai.ac.ae
