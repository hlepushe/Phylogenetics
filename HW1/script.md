Создание окружения и установка пакетов:
``` bash
conda create -n phylo
conda activate phylo
conda install bioconda::mafft
conda install bioconda::fasttree
```
Объединение исходных файлов в один и выравнивание:
```bash
 cat * >> merged.fasta
 mafft --auto merged.fasta > aligned
```
Построение дерева с помощью FastTree:
```bash
 FastTree -nt aligned.fasta > tree1.newick
```
Добавлеине неандертальцев и денисовцев в выборку, выравнивание и построение нового дерева
```bash
cat Denisova1.fasta Denisova2.fasta Denisova3.fasta Neanderthal1.fasta Neanderthal2.fasta Neanderthal3.fasta Neanderthal4.fasta  Neanderthal5.fasta > merged2.fasta
cat merged.fasta merged2.fasta > all.fasta
mafft --auto all.fasta > aligned_all.fasta
FastTree -nt aligned_all.fasta > tree_all.newick
```


