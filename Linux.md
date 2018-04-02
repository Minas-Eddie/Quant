## Linux command

* env
  * ```bash
    source activate c-env
    ```
  
* cont-G
  * ```bash
    du -ah
    ```

* cont-num
  * ```bash
    ls -lR CFY/test|grep "^-"|wc -l
    ```linux
  
## pipeline

* fasq-dump
  * ```bash
    fastq-dump -O new3_unzip --split-files SRR1294493 SRR1294495 &
    ```
    
 * fastqc
   * ```bash
     fastqc -o ./FastQC/fastqc_result/ -t 1 ./FastQC/fastqc_raw_data/*.fastq#trimAdapterRemoval --file1 reads_1.fq --file2 reads_2.fq --basename output_paired --trimns --trimqualities --collapse
     ```
    
 * STAR
   * ```bash
     mkdir indices
     mkdir indices/STAR
     nohup srun STAR --runThreadN 4 --runMode genomeGenerate --genomeDir indices/STAR --genomeFastaFiles hg19_index/hg19.fa --sjdbGTFfile hg19_index/hg19.gtf &
     
     STAR --runThreadN 4 --genomeDir indices/STAR --readFilesIn CFY/new3_unzip/SRR*.fastq --outFileNamePrefix results/STAR/
     ```

    
   



