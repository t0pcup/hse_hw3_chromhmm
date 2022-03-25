# hse_hw3_chromhmm

## Список анализируемых меток

**Клеточная линия:** A549

**Контроль:** ControlEtoh02AlnRep1 (ControlEtoh02AlnRep1.bam)

Гистоновая метка | Имя файла
:---------------:|:-----------:
H3k09me3         | H3k09me3.bam
H3k04me2         | H3k04me2.bam
H3k04me1         | H3k04me1.bam
H2az             | H2az.bam
H3k04me3         | H3k04me3.bam
H3k36me3         | H3k36me3.bam
H3k27ac          | H3k27ac.bam
H3k09ac          | H3k09ac.bam
H3k27me3         | H3k27me3.bam
H3k79me2         | H3k79me2.bam

## Работа с ChromHMM

[Ссылка на Colab](https://colab.research.google.com/drive/1llVs1T7x1bb0oZD-fxRHMYG6F-CQfdNV?usp=sharing)

## Отчет ChromHMM

overlap                                             | emissions
---------------------------------------------------:|:---------------------------------
![img](pictures/A549_15_overlap.png)                | ![img](pictures/emissions_15.png)

RefSeqTSS_neighborhood                              | RefSeqTES_neighborhood                              | transitions
---------------------------------------------------:|:---------------------------------------------------:|:-------------------------
![img](pictures/A549_15_RefSeqTSS_neighborhood.png) | ![img](pictures/A549_15_RefSeqTES_neighborhood.png) | ![img](pictures/transitions_15.png)

## UCSC GenomeBrowser

![A549_Genome_Browser](pictures/A549_Genome_Browser.png)

## Бонус

Полученный *A549_15_dense.bed* был модифицирован в *A549_15_dense_upd.bed* с помощью добавления 15-ти состояний:

![key](pictures/key.png)

Фрагмент полученного файла:

![key](pictures/A549_15_dense_upd_part.png)
