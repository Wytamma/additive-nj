# Additive Neighbor-Joining Tree

A modern web-based tool for constructing phylogenetic trees using the Neighbor-Joining algorithm with additivity diagnostics.

## Features

- **Multiple Distance Models**
  - SNP distance (raw count of mutations)
  - p-distance (proportion of differing sites)
  - Kimura 2-parameter model (accounts for transition/transversion bias)

- **Interactive Tree Visualization**
  - Powered by Phylocanvas.gl for smooth, interactive trees
  - Zoom, pan, and explore your phylogenetic relationships
  - Toggle branch length labels

- **Additivity Diagnostics**
  - Residual analysis comparing observed vs. tree distances
  - Four-point condition testing for all quartets
  - Statistical summaries (SSE, MAE, pass rates)

- **Flexible Gap Handling**
  - Pairwise exclusion of gap/N sites
  - Treat gaps as mismatches

## Usage

1. **Input Data**: Paste your FASTA alignment into the text area
2. **Choose Model**: Select your preferred distance calculation method
3. **Configure Settings**: Adjust gap handling, decimals, and diagnostics options
4. **Compute Tree**: Click "Compute NJ tree" to generate results

## Example

Click "Load example" to see the tool in action with sample sequences.

## Output

- **Newick Format**: Standard phylogenetic tree format for use in other tools
- **Distance Matrix**: Pairwise distances between all sequences
- **Interactive Tree**: Explore relationships with Phylocanvas visualization
- **Additivity Diagnostics**: Assess how well your data fits a tree model

## Technical Details

### Distance Models

- **SNP Distance**: Counts the number of single nucleotide polymorphisms between sequences. Best for closely related sequences where you want discrete mutation counts.

- **p-Distance**: Calculates the proportion of sites where sequences differ. Simple and widely used for moderate divergences.

- **Kimura 2-Parameter (K2P)**: Accounts for the higher rate of transitions (A↔G, C↔T) vs transversions (A/G↔C/T). More accurate for sequences with moderate to high divergence.

### Additivity Diagnostics

The tool evaluates how well your distance data conforms to a tree structure:

- **Residuals**: Differences between observed distances and tree-implied (patristic) distances
- **Four-Point Condition**: Tests whether all quartets of sequences satisfy the additivity requirement for tree-like evolution

### Self Tests

Built-in validation ensures the algorithms work correctly:
- Tests additive quartet reconstruction
- Validates four-point condition detection
- Verifies FASTA parsing

## Privacy

This tool runs entirely in your browser - no data is sent to external servers.

## Browser Compatibility

Requires a modern browser with WebGL support for optimal tree visualization.

## Credits

- Neighbor-Joining algorithm implementation
- Phylocanvas.gl for tree visualization
- Built with vanilla JavaScript and modern web standards
