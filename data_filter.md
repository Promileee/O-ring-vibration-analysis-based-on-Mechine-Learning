# Data Filtering

In the previous section *Data Loading and Plotting*, I identified an issue: some signals exhibited distortion, making it impossible to use the data directly. This section aims to address this problem.

## Fast Fourier Transform (FFT)

The Fast Fourier Transform (FFT) is an efficient algorithm for computing the Discrete Fourier Transform (DFT). It transforms a time-domain signal into a frequency-domain signal, thereby allowing analysis of the signal in the frequency spectrum. The formula and examples have been detailed in another repository named *FFT-Learning*.

## Application of FFT

In the uploaded file `data_file.ipynb`, I selected a typical example from the **fourth parallel experiment**: the y-axis signal representing the mass response at a compression ratio of 15%, with a rotation speed of 20,000 RPM.

I plotted the graph of this time-domain signal, which is the first graph in the `Data_filter.ipynb` file.

Next, I applied the FFT to convert the time-domain signal into a frequency-domain signal and then plotted it, as shown in the second graph within the file.

An issue was present in the original data where the time would reset to zero after a certain period, resulting in a **sawtooth pattern** when plotting time against sample index.

To address this, I recalculated the time array to ensure a continuous progression.

Following that, I implemented a high-pass filter as introduced in the *FFT-Learning* repository.

After applying the filter to the data, I used the Inverse FFT (IFFT) to transform the frequency-domain signal back into the time domain.

The result was remarkable; the filtering process effectively eliminated the distortion present in the original signal.
