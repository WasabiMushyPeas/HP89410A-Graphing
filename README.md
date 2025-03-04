# Setup 

## 1. Intall Python 
This project was developed using [Anaconda](https://www.anaconda.com/download) distribution of Python (Version 3.12) 

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
> Driver: You also need to install the VISA driver for your instrument. This can be found [here](https://www.ni.com/en/support/downloads/drivers/download/packaged.ni-488-2.559044.html)

## 3. Code

Run the Jupyter Notebook

look at the output of cell 2 to see if the instrument is connected. If it is not, a GPIB address won't be printed. The output should look like this:

```python
('ASRL4::INSTR', 'GPIB0::19::INSTR')
```

Using the output from cell 2, change the VISA address in the code to match the address of your instrument (This should be at the top of cell 5):

```python
...
# initial setup 
fftkey = "GPIB0::19::INSTR"

rm = visa.ResourceManager()
fft = set_fftconnect(fftkey)
...
```

Change the n_avgs variable to the number of averages you want to take. Change the decades_min variable to the minimum number of decades you want to sweep. Change the decades variable to the maximum number of decades you want to sweep. This is all at the top of cell 6:

```python
n_avgs = 10
decades_min = 2
decades = 7
```

> [!TIP]
> Code by: [Parth Patel](https://github.com/ranchop)