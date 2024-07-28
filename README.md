
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

| **Algorithm** | ***WavgCR*** | ***AvgCR*** | ***WavgSSP*** | ***AvgSSP*** | ***CRP***  | ***TotalCT*** | ***TotalDT*** | ***AvgCPM*** | ***AvgDPM*** |
|:-------------:|:------------:|:-----------:|:-------------:|:------------:|:----------:|:-------------:|:-------------:|:------------:|:------------:|
|               | (bits/base)  | (bits/base) | (\%)          | (\%)         | (\%)       | (Hour)        | (Hour)        | (GB)         | (GB)         |
| NNCP          | **4.183**    | **2.521**   | **47.713**    | **68.476**   | 13.084     | 942.928       | 926.049       | 0.111        | 0.111        |
| PAC           | **4.327**    | **2.638**   | **45.912**    | **67.019**   | 12.720     | 74.398        | 116.868       | 6.102        | 6.295        |
| TRACE         | **4.411**    | 2.718       | **44.867**    | 66.032       | 12.486     | 69.128        | 131.110       | 6.106        | 6.449        |
| DZip          | 4.494        | **2.516**   | 43.819        | **68.545**   | 14.272     | 332.787       | 148.374       | 10.113       | 4.790        |
| DZip*         | 4.562        | 3.802       | 42.971        | 52.476       | 11.158     | 332.787       | 148.374       | 10.113       | 4.790        |
| Lstm-compress | 5.395        | 2.786       | 32.563        | 65.168       | 14.543     | 492.869       | 474.498       | **0.009**    | **0.009**    |
| DeepZip*      | 16.835       | 7.045       | -110.434      | 11.933       | 18.504     | 250.714       | 52.449        | 13.708       | 4.292        |
| DeepZip       | 16.865       | 5.760       | -110.811      | 28.003       | 24.092     | 250.714       | 52.449        | 13.708       | 4.292        |
| BSC           | 4.826        | 2.928       | 39.677        | 63.394       | 13.045     | 0.353         | 0.300         | 0.121        | 0.116        |
| Lzma2         | 4.912        | 3.122       | 38.590        | 60.967       | 12.289     | 0.584         | 0.030         | 1.264        | 0.427        |
| XZ            | 4.923        | 3.118       | 38.463        | 61.021       | 12.365     | 0.879         | 0.040         | 1.612        | 0.504        |
| PPMD          | 4.960        | 3.025       | 38.001        | 62.181       | 12.934     | 0.893         | 0.953         | 0.226        | 0.225        |
| PBzip2        | 5.052        | 3.275       | 36.845        | 59.062       | 11.798     | **0.024**     | **0.016**     | 0.115        | 0.084        |
| Gzip          | 5.351        | 3.862       | 33.113        | 51.728       | **10.342** | 0.451         | 0.026         | **0.002**    | **0.002**    |
| LZ4-multi     | 5.618        | 4.280       | 29.770        | 46.501       | **9.656**  | **0.064**     | **0.009**     | 0.116        | 0.025        |
| SnZip         | 5.981        | 5.100       | 25.235        | 36.244       | **7.473**  | **0.031**     | **0.021**     | **0.003**    | **0.003**    |




**Notes.** "*" : Consideration of NN Model Size; 
"Avg/WavgCR (bits/base)" : Average OR Weighted Average Compression Ratio; 
"TotalCT/DT (Hours)" : Total Compression OR Decompression Time;
"AvgCPM/DPM (GB)" : Average Compression OR Decompression Peak Memory;
"Avg/WavgSSP (%)" : Average OR Weighted Average Storage Saving Percentage;
"CRP (%)" : Compression Robust Performance (%).

## Benchmark Datasets

We benchmark on 28 widely studied datasets. 
These datasets contain various types of text, images, audio, genomic data, etc.
Please refer to our paper for detailed information about the data, and the details of how to obtain each dataset are given below.
The detailed link address of the benchmark datasets are as follows:

|ID|Name|Data Type|Size (Bytes)|Description|
|:---:|:---:|:---:|:---:|:---:|
|D1|[xml](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|text|5345280 |Files in xml format|
|D2|[ooffice](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|heterogeneous|6152192 |Files consisting of Office programs|
|D3|[reymont](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|text|6627202 |A pdf file with the contents of Reymont's book|
|D4|[sao](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|homogeneous|7251944 |Files containing information of 258,996 stars|
|D5|[x-ray](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|image|8474240 |12-bit grayscale scaled x-ray medical image of a child's hand|
|D6|[mr](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|image|9970564 |A magnetic resonance medical image of the head|
|D7|[osdb](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|heterogeneous|10085684 |Open source database files for testing|
|D8|[dickens](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|text|10192446 |Text file consisting of multiple novels by Dickens|
|D9|[samba](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|heterogeneous|21606400 |An collected open source project|
|D10|[nci](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|homogeneous|33553445 |Files in SDF format|
|D11|[webster](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|heterogeneous|41458703 |An English dictionary stored in HTML format|
|D12|[mozilla](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|homogeneous|51220480 |The executable file Mozilla|
|D13|[enwik8](https://mattmahoney.net/dc/enwik8.zip)|text|100000000 |First $2^8$ bytes of the English Wikipedia dump on 2006|
|D14|[text8](https://mattmahoney.net/dc/text8.zip)|text|100000000 |First $2^8$ bytes of the English Wikipedia (only text) dump on 2006|
|D15|[MNIST](http://yann.lecun.com/exdb/mnist/)|image|54880032 |A widely studied dataset containing handwritten digital images|
|D16|[CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz)|image|186213868 |A standard dataset of images with multiple categories|
|D17|[ImageNet](https://image-net.org/data/ILSVRC/2012/ILSVRC2012_img_train_t3.tar)|image|745823247 |Training datasets in task3 from ISLVRC on 2012|
|D18|[ImageTest](http://imagecompression.info/test_images/rgb8bit.zip)|image|470611702 |A new 8-bit benchmark dataset for image compression evaluation|
|D19|[Silesia](https://sun.aei.polsl.pl//~sdeor/corpus/silesia.zip)|heterogeneous|211938580 |A heterogeneous corpus of 12 documents with various data types|
|D20|[Backup](https://drive.google.com/file/d/18qvfbeeOwD1Fejq9XtgAJwYoXjSV8UaC/view?usp=sharing)|heterogeneous|1000000000 |$2^9$ bytes random extract from the disk backup of TRACE|
|D21|[enwik9](https://mattmahoney.net/dc/enwik9.zip)|text|1000000000 |First $2^9$ bytes of the English Wikipedia dump on 2006|
|D22|[Book](https://storage.googleapis.com/huggingface-nlp/datasets/bookcorpus/bookcorpus.tar.bz2)|text|1000000000 |First $2^9$ bytes of BookCorpus|
|D23|[ESC](https://codeload.github.com/karolpiczak/ESC-50/zip/refs/heads/master)|audio|220522000 |First 500 audio files of the ESC|
|D24|[Command](http://download.tensorflow.org/data/speech_commands_v0.01.tar.gz)|audio|327759206 |First 10,000 audio files of the Google Speech Commands Dataset|
|D25|[LibriSpeech](https://openslr.trmal.net/resources/12/dev-clean.tar.gz)|audio|359034309 |Development set ("clean" speech) of LibriSpeech ASR corpus|
|D26|[LJSpeech](https://data.keithito.com/data/speech/LJSpeech-1.1.tar.bz2)|audio|293847664 |First 10,000 audio files of  the LJ Speech Dataset|
|D27|[DNACorpus](https://sweet.ua.pt/pratas/datasets/DNACorpus.zip)|genome|685597124 |A corpus of DNA sequences from 15 different species|
|D28|[ERR7091247](https://www.ncbi.nlm.nih.gov/sra/ERR7091247)|genome|1926041160 |A collection of genomics sequencing dataset with FastQ format|

## Algorithms Details
In our comparison examinations, we benchmarked 8 advanced general-purpose NN-based compressors Cmix, NNCP, Lstm-compress, DeepZip, DZip, TRACE, PAC, LLMZip and 8 traditional methods Gzip, PBzip2, XZ, BSC, SnZip, Lzma2, and PPMD, LZ4. 

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

### [LLMZip](https://github.com/vcskaushik/LLMzip?tab=readme-ov-file)
LLMZip uses LLaMA as probabilistic predictor in combination with entropy coding (zlib, Token-by-Token and arithmetic coding) to achieve general-purpose lossless compression. The compression and decompression commands of LLMZip are as follows.

```sh
# compression
torchrun --nproc_per_node 1 LLMzip_run.py --ckpt_dir llama2/llama-2-7b --tokenizer_path llama2/tokenizer.model --win_len 511 --text_file file --compression_folder file --encode_decode 0
# decompression
torchrun --nproc_per_node 1 LLMzip_run.py --ckpt_dir llama2/llama-2-7b --tokenizer_path llama2/tokenizer.model --win_len 511 --text_file file --compression_folder file --encode_decode 1
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


### [SnZip](https://github.com/kubo/snzip)
SnZip is a traditional general-purpose lossless compression algorithm based on snappy. It supports a wide range of file formats including framing-format, old framing-format and so on. The default is framing-format. The command line to run SnZip is as follows.

```sh
# compression
snzip -k -t snzip file
# decompression
snzip -kd -t snzip file.snz
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

### [LZ4-multi](https://github.com/lz4/lz4)
LZ4 is a lossless compression algorithm with compression speeds greater than 500 MB/s per kernel (greater than 0.15 bytes/cycle). Its decoder is extremely fast, up to several GB/s (1 byte/cycle) per kernel. The latest lz4 algorithm supports multi-threaded versions.
```sh
# compression
lz4 -12 -T16 file file.lz4
# decompression
lz4 -12 -T16 -d file.lz4 file.lz4.reads
\end{lstlisting}
```

## Experimental Configuration

All experiments were conducted on a GPU server equipped with 4 * Intel Xeon Silver 4310 CPUs (2.10 GHz, 48 cores in total), 4* NVIDIA GeForce RTX 4090 GPUs (16,384 CUDA cores, 24 GB of GPU memory), and 128 GB of DDR4 RAM. The server runs the operating system Ubuntu 20.04.6 LTS.


<!-- ## Acknowledgements
- Thanks to [@NCBI](https://www.freelancer.com/u/Ostokhoon) for all available datasets.
-->

## Additional Information
**Source-Version-Date**   2024.03.08. 2024.03.10.

**Latest-Version-Date**   2024.7.28.

**Authors:**     NBJL-AIGroup.

**Contact us:**  https://nbjl.nankai.edu.cn, sunh@nbjl.naikai.edu.cn or mahd@nbjl.naikai.edu.cn
