<!-- LOGO -->
<br />
<h1 align="center">
  <img src="https://github.com/fahaihi/NNLCB/blob/master/LOG.png" alt="Logo" width="722" height="189">
</h1>
<p align="center">
  A Holistic Benchmark Evaluation for Neural-Network-Based Lossless Universal Compression Algorithms.
</p>

In our benchmark, we performed examinations on general-purpose lossless compressors, including 7 NN-based and 6 traditional compressors, using 19 datasets with differing type. Each loss-less compressor was evaluated on 13 performance measures, including compression robustness, compression strength, as well as time and peak memory required for compression and decompression.



## Benchmark DataSets

We benchmark on 19 widely studied datasets. These datasets contain various types of text, images, audio, genomic data, etc. Please refer to our paper for detailed information about the data, and the details of how to obtain each dataset are given below.
The detailed link address of the benchmark datasets are as follows:

D1~12:  [https://sun.aei.polsl.pl//~sdeor/index.php?page=silesia](https://sun.aei.polsl.pl//~sdeor/index.php?page=silesia)

D13~14: [https://mattmahoney.net/dc/text.html](https://mattmahoney.net/dc/text.html)

D15: https://storage.googleapis.com/huggingface-nlp/datasets/bookcorpus/bookcorpus.tar.bz2

D16: [https://github.com/karolpiczak/ESC-50](https://github.com/karolpiczak/ESC-50)

D17: [https://image-net.org/challenges/LSVRC/2012/2012-downloads.php](https://image-net.org/challenges/LSVRC/2012/2012-downloads.php)

D18: https://drive.google.com/file/d/1-hWz1fQFo5Y0KqzTNhslkbaJkKz-qnaN/view?usp=sharing

D19: https://tinyurl.com/DNAcorpus

## Algorithms Details
In our comparison examinations, we benchmarked 7 advanced general-purpose NN-based compressors Cmix, NNCP, Lstm-compress, DeepZip, DZip, TRACE, and PAC, and 6 traditional methods Gzip, PBzip2, XZ, BSC, Lzma2, and PPMD. 

All experiments were conducted on a GPU server equipped with 4 * Intel Xeon Silver 4310 CPUs (2.10 GHz, 48 cores in total), 4* NVIDIA GeForce RTX 4090 GPUs (16,384 CUDA cores, 24 GB of GPU memory), and 128 GB of DDR4 RAM. The server runs the operating system Ubuntu 20.04.6 LTS.

## Algorithms Commands

1.  ### NN-based  Compressor

Cmix is a neural network based lossless compression algorithm aimed at optimizing compression ratio at the cost of high CPU/memory usage, and it uses thousands of context models followed by an NN-based mixer. We used Cmix V19 to finish the experiments.

```
# compression
cmix -c file file.cmix
# decompression
cmix -d file.cmix file.cmix.out
```

LSTM-compressor is an LSTM-based lossless compression algorithm that uses the same LSTM module and preprocessing code as CMIX. LSTM-compress currently only supports compression of a single file. In this manuscript, we used LSTM-compress V3. The detailed commands are as follows.

```
# compression
lstm-compress -c file file.lstm
# decompression
lstm-compress -d file.lstm file.lstm.out
```

NNCP is a lossless compression algorithm based on LSTM and supports multi-GPU parallel processing. NNCP is an experiment to build a practical lossless data compressor with neural networks. The latest version uses a Transformer model. In this manuscript, we used NNCP V2021-06-01 to finish the experiments. The detailed commands are as follows.

```
# compression
nncp c file file.nncp -T 16 --cuda
# decompression
nncp d file.nncp file.nncp.out -T 16 --cuda
```

DeepZIp is a general-purpose compression algorithm based on recurrent neural networks. It belongs to the static pre-training method. The detailed commands for using DeepZip are shown below.

```
# compression
sh ./compress.sh file file.deepzip bs model
# decompression
sh ./decompress.sh file.deepzip file.deepzip.out bs model
```

DZip is an upgraded version of DeepZip, with an extra deeper network added to DeepZip to improve compression. DZip includes two compression modes, combined mode and bootstrap mode.  The detailed commands of DZip are as follows.

```
# compression
sh ./compress.sh file file.dzip com model
# decompression
sh ./decompress.sh file.dzip file.dzip.out com model
```

TRACE is a lossless compression algorithm based on Performer (a Transformer variant.) TRACE uses byte grouping and shared FFNs, and therefore has better execution efficiency. Since the original TRACE puts compression and decompression processes into simultaneous execution, in order to test the performance of compression and decompression separately, we have modified the source files to test the performance of compression or decompression separately.

```
# compression
python compressor.py --source file --comp file.trace
# decompression
python compressor.py --comp file.trace --decomp file.trace.out
```

PAC is a deep learning based compression algorithm fusing MLP and Ordered Mask. Due to the use of MLP, PAC has a lower computational cost. Again, we separate the compression-decompression process of PAC as shown in the command line below.

```
# compression
python compressor.py --source file --comp file.pac
# decompression
python compressor.py --comp file.pac --decomp file.pac.out
```

2. ### Traditional  Compressor

Gzip is a popular early general-purpose lossless compression program originally written by Jean-loup Gailly for the GNU project. The commands for Gzip are shown below.

```
# compression
gzip -c file > file.gz -9
# decompression
gzip file.gz -9
```

PBzip2 is a parallel implementation of the Bzip2 block-sorting file compression algorithm that uses pthreads and achieves near-linear speedup on SMP devices. PBzip2 utilizes the Burrows-Wheeler block sorting algorithm for compressing files, along with Huffman coding for efficient text compression. This manuscript uses parallel Bzip2 V1.1.13  to compress data.

```
# compression
pbzip2 -9 -m2000 -p16 -c file > file.bz2
# decompression
pbzip2 -dc -9 -p16 -m2000 file.bz2
```

XZ Utils is free general-purpose data compression software with a high compression ratio. XZ Utils were written for POSIX-like systems, but also work on some not-so-POSIX systems. XZ Utils are the successor to LZMA Utils. In our experiments, we used XZ V5.5.0. The compression and decompression commands are as follows.

```
# compression
pbzip2 -9 -m2000 -p16 -c file > file.bz2
# decompression
pbzip2 -dc -9 -p16 -m2000 file.bz2
```

BSC is a high-performance file compressor based on lossless block-ordered data compression algorithm, block-ordered data compression algorithm, high-performance file compressor. This manuscript uses BSC V3.3.2 to compress and decompress data.

```
# compression
bsc e file file.bsc -e2
# decompression
bsc d file.bsc file.bsc.out
```

LZMA2 improves the multi-threading capability and performance of the LZMA algorithm and better handles incompressible data, so the compression performance is slightly improved. We also used the built-in LZMA2 algorithm in the 7-Zip application.

```
# compression
7zz a -m0=lzma2 -mx9 -mmt16 file.7z file
# decompression
7zz x -y -mx9 -mmt16 file.7z
```

PPMD is a context-based compressor, and its core idea is the Partial Matching Prediction (PPM) algorithm proposed by Cleary and Witten. PPM is a statistical modeling technique that uses a set of previous symbols in the input to predict the next symbol to reduce the output data’s entropy. PPM differs from a dictionary because PPM predicts the next symbol instead of trying to find the next symbol in the dictionary to encode. We utilized the PPMD in the 7-Zip to compress data.

```
# compression
7zz a -m0=ppmd -mx9 -mmt16 file.7z file
# decompression
7zz x -y -mx9 -mmt16 file.7z
```



## Experimental Configuration

All experiments were conducted on a GPU server equipped with 4 * Intel Xeon Silver 4310 CPUs (2.10 GHz, 48 cores in total), 4* NVIDIA GeForce RTX 4090 GPUs (16,384 CUDA cores, 24 GB of GPU memory), and 128 GB of DDR4 RAM. The server runs the operating system Ubuntu 20.04.6 LTS.


## Acknowledgements
- Thanks to [@NCBI](https://www.freelancer.com/u/Ostokhoon) for all available datasets.

## Additional Information
**Source-Version-Date**   2024.03.13.

**Latest-Version-Date**   2024.10.07.

**Authors:**     NBJL-AIGrop.

**Contact us:**  https://nbjl.nankai.edu.cn, sunh@nbjl.naikai.edu.cn or mahd@nbjl.naikai.edu.cn
