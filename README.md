
<!-- LOGO -->
<br />
<h1 align="center">
  <img src="https://fahaihi.github.io/NNLCB/LOG.png" alt="Logo" width="821" height="350">
</h1>

# A Holistic Benchmark Evaluation for Neural-Network-Based Lossless Universal Compressors


## Overview
NNLCB is a general-purpose (Universal) lossless compression algorithms benchmark test for multi-source data with deep neural networks.
Currently, in our benchmark, we performed examinations on general-purpose lossless compressors, including 7 NN-based and 6 traditional compressors, using 19 datasets with differing type. Each loss-less compressor was evaluated on 13 performance measures, including compression robustness, compression strength, as well as time and peak memory required for compression and decompression.

## Benchmark Results
#### Performance comparison of different universal lossless compression tools on benchmark datasets

|Algorithm | *WavgCR* | *AvgCR* | *WavgSSP* | *AvgSSP* | *CRP* | *TotalCT* | *TotalDT* | *AvgCPM* | *AvgDPM* |
| -------- | --------- | -------- | ------- | --------- | -------- | ----- | --------- | --------- | -------- | 
| Cmix     | 1.602     | 1.481    | 79.972    | 81.482   | 19.698  | 108.201 | 108.3     | 19.174    | 19.175   |
| NNCP     | **4.173** | **2.237**| **47.826**| **72.028**| 15.42   | 497.734 | 508.632   | 0.111     | 0.111    |
| PAC      | **4.346** | **2.356**| **45.674**| **70.546**| 15.169  | 41.064  | 67.807    | 5.506     | 5.731    |
| TRACE    | **4.508** | 2.437    | **43.656**| 69.533   | 14.917  | 40.215  | 79.973    | 5.557     | 5.799    |
| DZip     | 4.6       | **2.165**| 42.499   | **72.936**| 17.731  | 173.759 | 86.659    | 8.507     | 4.616    |
| DZip*    | 4.666     | 3.982    | 41.677   | 50.221   | **13.254**| 173.759 | 86.659    | 8.507     | 4.616    |
| Lzma2    | 4.984     | 2.752    | 37.697   | 65.597   | 15.075  | 0.297   | **0.015** | 1.047     | 0.358    |
| XZ       | 4.988     | 2.748    | 37.647   | 65.643   | 15.182  | 0.413   | 0.019     | 1.346     | 0.418    |
| BSC      | 4.99      | 2.591    | 37.619   | 67.603   | 16.365  | **0.182**| 0.156     | **0.103** | 0.101    |
| PPMD     | 5.136     | 2.664    | 35.789   | 66.688   | 16.274  | 0.499   | 0.526     | 0.212     | 0.211    |
| PBzip2   | 5.232     | 2.927    | 34.597   | 63.412   | **14.675**| **0.014** | **0.010** | 0.106     | **0.073**|
| Gzip     | 5.369     | 3.491    | 32.889   | 56.367   | **12.373**| **0.200** | **0.005** | **0.002** | **0.002**|
| Lstm-compress | 5.392 | 2.672    | 32.595   | 66.596   | 16.573  | 303.245 | 293.965   | **0.009** | **0.009**|
| DeepZip* | 17.017    | 5.69     | -112.708 | 28.874   | 22.376  | 127.937 | 31.943    | 7.639     | 4.008    |
| DeepZip  | 17.097    | 3.873    | -113.71  | 51.589   | 34.715  | 127.937 | 31.943    | 7.639     | 4.008    |

**Notes.** "*" : Consideration of NN Model Size; 
"Avg/WavgCR (bits/base)" : Average OR Weighted Average Compression Ratio; 
"TotalCT/DT (Hours)" : Total Compression OR Decompression Time;
"AvgCPM/DPM (GB)" : Average Compression OR Decompression Peak Memory;
"Avg/WavgSSP (%)" : Average OR Weighted Average Storage Saving Percentage;
"CRP (%)" : Compression Robust Performance (%).

## Benchmark Datasets

We benchmark on 19 widely studied datasets. 
These datasets contain various types of text, images, audio, genomic data, etc.
Please refer to our paper for detailed information about the data, and the details of how to obtain each dataset are given below.
The detailed link address of the benchmark datasets are as follows:

D1~12:  [Silesia data compression porpus](https://sun.aei.polsl.pl//~sdeor/index.php?page=silesia)

D13~14: [ English wikipedia datasets](https://mattmahoney.net/dc/text.html)

D15: [A BookCorpus](https://storage.googleapis.com/huggingface-nlp/datasets/bookcorpus/bookcorpus.tar.bz2)

D16: [First 500 audio files of the ESC](https://github.com/karolpiczak/ESC-50)

D17: [Training datasets in task3 from ISLVRC on 2012](https://image-net.org/challenges/LSVRC/2012/2012-downloads.php)

D18: [Random extracted disk backup](https://drive.google.com/file/d/1-hWz1fQFo5Y0KqzTNhslkbaJkKz-qnaN/view?usp=sharing)

D19: [A corpus of DNA sequences from 15 different species](https://tinyurl.com/DNAcorpus)

## Algorithms Details
In our comparison examinations, we benchmarked 7 advanced general-purpose NN-based compressors Cmix, NNCP, Lstm-compress, DeepZip, DZip, TRACE, and PAC, and 6 traditional methods Gzip, PBzip2, XZ, BSC, Lzma2, and PPMD. 

All experiments were conducted on a GPU server equipped with 4 * Intel Xeon Silver 4310 CPUs (2.10 GHz, 48 cores in total), 4* NVIDIA GeForce RTX 4090 GPUs (16,384 CUDA cores, 24 GB of GPU memory), and 128 GB of DDR4 RAM. The server runs the operating system Ubuntu 20.04.6 LTS.

## Algorithms details and commands

### [Cmix](https://github.com/byronknoll/cmix)
Cmix is a neural network based lossless compression algorithm aimed at optimizing compression ratio at the cost of high CPU/memory usage, and it uses thousands of context models followed by an NN-based mixer. We used Cmix V19 to finish the experiments.
```sh
# compression
cmix -c file file.cmix
# decompression
cmix -d file.cmix file.cmix.out
```
### [LSTM-compress](https://github.com/byronknoll/lstm-compress)
LSTM-compressor is an LSTM-based lossless compression algorithm that uses the same LSTM module and preprocessing code as CMIX. LSTM-compress currently only supports compression of a single file. In this manuscript, we used LSTM-compress V3. The detailed commands are as follows.

```sh
# compression
lstm-compress -c file file.lstm
# decompression
lstm-compress -d file.lstm file.lstm.out
```

### [NNCP](https://bellard.org/nncp)
NNCP is a lossless compression algorithm based on LSTM and supports multi-GPU parallel processing. NNCP is an experiment to build a practical lossless data compressor with neural networks. The latest version uses a Transformer model. In this manuscript, we used NNCP V2021-06-01 to finish the experiments. The detailed commands are as follows.

```sh
# compression
nncp c file file.nncp -T 16 --cuda
# decompression
nncp d file.nncp file.nncp.out -T 16 --cuda
```
### [DeepZip](https://github.com/mohit1997/DeepZip)
DeepZip is a general-purpose compression algorithm based on recurrent neural networks. It belongs to the static pre-training method. The detailed commands for using DeepZip are shown below.

```sh
# compression
sh ./compress.sh file file.deepzip bs model
# decompression
sh ./decompress.sh file.deepzip file.deepzip.out bs model
```
### [DZip](https://github.com/mohit1997)
DZip is an upgraded version of DeepZip, with an extra deeper network added to DeepZip to improve compression. DZip includes two compression modes, combined mode and bootstrap mode.  The detailed commands of DZip are as follows.

```sh
# compression
sh ./compress.sh file file.dzip com model
# decompression
sh ./decompress.sh file.dzip file.dzip.out com model
```
### [TRACE](https://github.com/mynotwo/A-Fast-Transformer-based-General-Purpose-LosslessCompressor)
TRACE is a lossless compression algorithm based on Performer (a Transformer variant.) TRACE uses byte grouping and shared FFNs, and therefore has better execution efficiency. Since the original TRACE puts compression and decompression processes into simultaneous execution, in order to test the performance of compression and decompression separately, we have modified the source files to test the performance of compression or decompression separately.

```sh
# compression
python compressor.py --source file --comp file.trace
# decompression
python compressor.py --comp file.trace --decomp file.trace.out
```

### [PAC](https://github.com/mynotwo/Faster-and-Stronger-Lossless-Compression-with-Optimized-Autoregressive-Framework)
PAC is a deep learning based compression algorithm fusing MLP and Ordered Mask. Due to the use of MLP, PAC has a lower computational cost. Again, we separate the compression-decompression process of PAC as shown in the command line below.

```sh
# compression
python compressor.py --source file --comp file.pac
# decompression
python compressor.py --comp file.pac --decomp file.pac.out
```

### [Gzip](https://www.gnu.org/software/gzip/)

Gzip is a popular early general-purpose lossless compression program originally written by Jean-loup Gailly for the GNU project. The commands for Gzip are shown below.

```sh
# compression
gzip -c file > file.gz -9
# decompression
gzip file.gz -9
```
### [PBzip2](https://launchpad.net/pbzip2)
PBzip2 is a parallel implementation of the Bzip2 block-sorting file compression algorithm that uses pthreads and achieves near-linear speedup on SMP devices. PBzip2 utilizes the Burrows-Wheeler block sorting algorithm for compressing files, along with Huffman coding for efficient text compression. This manuscript uses parallel Bzip2 V1.1.13  to compress data.

```sh
# compression
pbzip2 -9 -m2000 -p16 -c file > file.bz2
# decompression
pbzip2 -dc -9 -p16 -m2000 file.bz2
```

### [XZ](https://xz.tukaani.org/xz-utils/)
XZ Utils is free general-purpose data compression software with a high compression ratio. XZ Utils were written for POSIX-like systems, but also work on some not-so-POSIX systems. XZ Utils are the successor to LZMA Utils. In our experiments, we used XZ V5.5.0. The compression and decompression commands are as follows.

```sh
# compression
pbzip2 -9 -m2000 -p16 -c file > file.bz2
# decompression
pbzip2 -dc -9 -p16 -m2000 file.bz2
```

### [BSC](https://github.com/IlyaGrebnov/libbsc)
BSC is a high-performance file compressor based on lossless block-ordered data compression algorithm, block-ordered data compression algorithm, high-performance file compressor. This manuscript uses BSC V3.3.2 to compress and decompress data.

```sh
# compression
bsc e file file.bsc -e2
# decompression
bsc d file.bsc file.bsc.out
```

### [LZMA2](https://www.7-zip.org/)
LZMA2 improves the multi-threading capability and performance of the LZMA algorithm and better handles incompressible data, so the compression performance is slightly improved. We also used the built-in LZMA2 algorithm in the 7-Zip application.

```sh
# compression
7zz a -m0=lzma2 -mx9 -mmt16 file.7z file
# decompression
7zz x -y -mx9 -mmt16 file.7z
```

### [PPMD](https://www.7-zip.org/)
PPMD is a context-based compressor, and its core idea is the Partial Matching Prediction (PPM) algorithm proposed by Cleary and Witten. PPM is a statistical modeling technique that uses a set of previous symbols in the input to predict the next symbol to reduce the output data’s entropy. PPM differs from a dictionary because PPM predicts the next symbol instead of trying to find the next symbol in the dictionary to encode. We utilized the PPMD in the 7-Zip to compress data.

```sh
# compression
7zz a -m0=ppmd -mx9 -mmt16 file.7z file
# decompression
7zz x -y -mx9 -mmt16 file.7z
```



## Experimental Configuration

All experiments were conducted on a GPU server equipped with 4 * Intel Xeon Silver 4310 CPUs (2.10 GHz, 48 cores in total), 4* NVIDIA GeForce RTX 4090 GPUs (16,384 CUDA cores, 24 GB of GPU memory), and 128 GB of DDR4 RAM. The server runs the operating system Ubuntu 20.04.6 LTS.


<!-- ## Acknowledgements
- Thanks to [@NCBI](https://www.freelancer.com/u/Ostokhoon) for all available datasets.
-->

## Additional Information
**Source-Version-Date**   2024.03.08. 2024.03.10.

**Latest-Version-Date**   2024.03.22.

**Authors:**     NBJL-AIGroup.

**Contact us:**  https://nbjl.nankai.edu.cn, sunh@nbjl.naikai.edu.cn or mahd@nbjl.naikai.edu.cn
