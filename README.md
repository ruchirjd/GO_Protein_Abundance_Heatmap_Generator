# GO Protein Abundance Heatmap Generator

A Python-based tool for analyzing and visualizing protein abundance data based on Gene Ontology (GO) terms. This tool processes proteomics data, extracts proteins matching specific GO IDs, and generates publication-quality heatmaps comparing protein abundance across different samples.

## Features

- Extract proteins based on specified GO IDs from proteomics data
- Process and normalize protein abundance data
- Generate high-resolution heatmaps (PNG and PDF formats)
- Compare protein abundance between different samples (e.g., Adult vs. Larva)
- Support for both single-sample and comparative analysis
- Automatic protein column detection
- Flexible GO term matching
- Data normalization and scaling
- Detailed output logging and statistics

## Requirements

```
pandas
numpy
seaborn
matplotlib
typing
```

## Installation

1. Clone this repository or download the script
2. Install required packages:
```bash
pip install pandas numpy seaborn matplotlib
```

## Usage

Run the script from the command line:
```bash
python GO_Protein_Abundance_Heatmap_Generator.py
```

The script will interactively prompt you for:

1. Input CSV file paths (one or two files)
2. GO IDs of interest
3. Optional custom title for the heatmap

### Input File Format

The input CSV files should contain:
- A column containing protein names (with "protein" in the column name)
- One or more columns containing GO terms
- Columns containing average abundance values (with "average" in the column name)

Example input files in your workspace:
- `HB_adult_proteins.csv`
- `HB_larval_proteins.csv`

### Output Files

The tool generates several output files:
- `normalized_average_value_heatmap.png`: High-resolution heatmap visualization
- `normalized_average_value_heatmap.pdf`: Vector format heatmap
- `merged_results.csv`: Processed and merged data
- `extracted_*.csv`: Filtered results for each input file
- `go_comparison_results.txt`: Statistical comparison (when comparing two files)

## Heatmap Features

The generated heatmaps include:
- Normalized protein abundance values (scaled ×10⁴)
- Protein names with associated GO terms
- Color-coded abundance visualization (YlOrRd color scheme)
- Horizontal colorbar
- Grid lines for better readability
- Custom or default titles
- Publication-ready resolution (600 DPI)

## Example Usage with Sample Data

Using files from your current workspace:

```python
# Example input files
file1 = "HB_adult_proteins.csv"
file2 = "HB_larval_proteins.csv"

# Example GO IDs for immune-related proteins
go_ids = [
    "GO:0006955",  # immune response
    "GO:0045087"   # innate immune response
]
```

## Data Processing Details

1. **GO Term Extraction**:
   - Flexible matching of GO terms
   - Handles various GO ID formats
   - Supports multiple GO terms per protein

2. **Data Normalization**:
   - Handles missing and zero values
   - Scales abundance values (×10⁴)
   - Supports comparative analysis between samples

3. **Visualization**:
   - Automatically adjusts figure dimensions based on protein count
   - Optimizes label placement and readability
   - Provides clear protein annotations with GO terms

## Troubleshooting

Common issues and solutions:

1. **No GO columns found**: 
   - Ensure GO terms are present in the input file
   - Check column naming conventions (should contain 'GO', 'go', or 'Gene Ontology')

2. **Missing abundance values**: 
   - Verify "average" columns exist in your CSV files
   - Check data format in CSV files
   - Ensure numeric values are properly formatted

3. **Visualization issues**:
   - Ensure sufficient memory for large datasets
   - Check input data formatting
   - Verify file permissions for output generation

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License

See license.md file

## Acknowledgments

This tool was developed for analyzing proteomics data with a focus on comparing protein abundance between different biological samples (Adult vs. Larva) while leveraging Gene Ontology annotations for meaningful biological interpretation.
