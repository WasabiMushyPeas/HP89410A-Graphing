# Setup 

## 1. Install Python 
This project was developed using [Anaconda](https://www.anaconda.com/download) distribution of Python (Version 3.12).

This project also uses Jupyter Notebooks.

## 2. Install the dependencies:

Python Libraries:
```bash
pip install pyvisa
```
```bash
pip install numpy
```
```bash
pip install matplotlib
```

> [!WARNING]
> You also need to install the VISA driver for your instrument. This can be found [here](https://www.ni.com/en/support/downloads/drivers/download/packaged.ni-488-2.559044.html)

## 3. Code

1) [Download](https://github.com/WasabiMushyPeas/HP89410A-Graphing/archive/refs/heads/main.zip) the code and open the Jupyter Notebook.

2) Run the Jupyter Notebook

3) look at the output of the "Get Address" section to see if the instrument is connected. If it is not connected, a GPIB address will not be printed. The output should look similar to this:

```python
('ASRL4::INSTR', 'GPIB0::19::INSTR')
```

4) Using the output from the "Get Address" section, change the address in the code to match the address of your instrument (This should be under the "Initialize the spectrum analyzer"):

```python
# initial setup 
fftkey = "GPIB0::19::INSTR"
```


# Usage

## Customization

Change the variables in the "Variables" section to customize the graph and data. The variables are:

```python
# This determines the number of plots that will be taken (change as needed)
plots = 3;
# This determines the number of averages that will be taken (change as needed)
n_avgs = 10
# These determine the frequency range that will be plotted (change as needed)
decades_min = 2
decades = 7
# These determine the size of the graph (change as needed)
graphHeight = 10
graphWidth = 15
```

> [!TIP]
> Any plot name that has "Noise Floor" or "Seed" in it will have some transparency in the graph.

## Running the code

1) Run the Jupyter Notebook
2) The Program will ask you for the names of the plots. Enter the names of the plots in the order that you want them to be displayed on the graph.
3) The Program will save each plot to a txt file in the data folder. The naming convention is "1&(the name you entered).txt", "2&(the name you entered).txt", etc.

> [!NOTE]
> Original Code by: [Parth Patel](https://github.com/ranchop)
