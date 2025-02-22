# Priority Matrix for Lead Molecule Selection
Lead Molecule Selection: Priority Score Visualization


This little program provides a 3D visualization of lead molecule selection based on key pharmacokinetic and pharmacodynamic properties. It uses a priority score model to rank molecules based on their potency, cytotoxicity, and microsomal stability. The results are displayed in a 3D scatter plot, where colors represent the normalized priority scores.

## Mathematical Framework

The prioritization of molecules is based on a weighted scoring system, defined as:

Score= (w1 * X1 + w2 * X2 + w3 * X3) * 100

Where:

X1 = Normalized pEC50 (Potency)

X2 = Normalized CC50 (Cytotoxicity, μM)

X3 = Normalized T1/2 (Microsomal Stability, min)


w1, w2, w3 are the assigned weights

## Normalization

Each parameter is normalized using MinMax Scaling: X(normalized) = (Xi - Xmin)/ (Xmax - Xmin)

where Xmax and Xmin are the minimum and maximum observed values, respectively.

## Weights:

w1, Potency (pEC50): 0.4

w2, Cytotoxicity (CC50): 0.3

w3, Stability (T1/2): 0.3


These weights reflect the relative importance of each parameter in prioritizing lead molecules.

## Data

The dataset consists of:

pEC50: Represents potency (higher values are better)

CC50: Represents cytotoxicity (higher values are better)

T1/2: Represents microsomal stability (higher values are better)


## Visualization

The 3D scatter plot is generated with:

X-axis: Normalized pEC50 (Potency)

Y-axis: Normalized CC50 (Cytotoxicity, μM)

Z-axis: Normalized T1/2 (Microsomal Stability, min)


Color mapping: Molecules are colored based on their normalized priority score using the Viridis colormap.

## How It Works

Normalization: Raw data is transformed into a 0-1 scale using MinMaxScaler.

Score Calculation: A weighted sum formula is applied.

Sorting: Molecules are sorted based on their priority score.

3D Visualization: A scatter plot is generated with annotations.


## Output

3D Scatter Plot: lead_molecule_selection.svg

Ranked Table: Printed in the console, showing molecules sorted by priority score.

## Dependencies

Python 3.x

NumPy

Pandas

Matplotlib

Scikit-learn


## Usage
open in google colab, or
Run the script:

python lead_molecule_selection.py
