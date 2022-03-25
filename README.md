# hse_hw3_chromhmm

## Список анализируемых меток

**Клеточная линия:** HUVEC

**Контроль:** wgEncodeBroadHistoneHuvecControlStdAlnRep1.bam (Control.bam)

Гистоновая метка | Имя файла
:---------------:|:-----------:
H3k36me3         | H3k36me3.bam
H3k4me2          | H3k4me2.bam
H4k20me1         | H4k20me1.bam
Ctc              | Ctc.bam
H3k9me1          | H3k9me1.bam
Pol2b            | Pol2b.bam
H3k27ac          | H3k27ac.bam
H3k4me3          | H3k4me3.bam
H3k27me3         | H3k27me3.bam
H3k9ac           | H3k9ac.bam

**cellmarkfiletable.txt:**

![cellmarkfiletable](pictures/cellmarkfiletable.png)

## Работа с ChromHMM

[Ссылка на Colab](https://colab.research.google.com/drive/1Ki-ptRA6R1crE_Sd1NHeyil1JRGmtOry?usp=sharing)

## Отчет ChromHMM

overlap                                             | emissions
:--------------------------------------------------:|:--------------------------------:
![img](results/HUVEC_15_overlap.png)                | ![img](results/emissions_15.png)

RefSeqTSS_neighborhood                              | RefSeqTES_neighborhood                              | transitions
:--------------------------------------------------:|:---------------------------------------------------:|:----------:
![img](results/HUVEC_15_RefSeqTSS_neighborhood.png) | ![img](results/HUVEC_15_RefSeqTES_neighborhood.png) | ![img](results/transitions_15.png)

## UCSC GenomeBrowser

Участки генома и соответствующие эпигенетические типы (и, желательно, профили эпигенетических меток).
 № | Название        | Полное изображение                        | Дополнительный фрагмент                   | Наблюдения
:-:|:---------------:|:-----------------------------------------:|:-----------------------------------------:|:---------:
1  | Enhancer        | ![1](pictures/UCSC_GenomeBrowser/1.png)   |                                           | Сильный сигнал и состояние попало на интрон.
2  | Repressed       | ![2](pictures/UCSC_GenomeBrowser/2.png)   |                                           | Не попадает на гены, сильный сигнал.
3  | Transcriptional | ![3](pictures/UCSC_GenomeBrowser/3.png)   |                                           | Ассоциируется с RefSeqGene. Попадает на интрон и показывает слабый сигнал.
4  | Repressed       | ![4](pictures/UCSC_GenomeBrowser/4.png)   |                                           | Ассоциируется с RefSeqTES, RefSeqGene, RefSeqExon
5  | Heterochromatin | ![5](pictures/UCSC_GenomeBrowser/5.png)   |                                           | Показывает слабый сигнал и попадает на участок репрессированного гетерохроматина и интроны генов.
6  | Heterochromatin | ![6](pictures/UCSC_GenomeBrowser/6.png)   | ![6](pictures/UCSC_GenomeBrowser/6_2.png) | Самые частые и длинные отрезки помечены как 6-е состояние. Аналогично с 5-м состоянием : показывает слабый сигнал и попадает на участок репрессированного гетерохроматина и интроны генов.
7  | Heterochromatin | ![7](pictures/UCSC_GenomeBrowser/7.png)   |                                           | Показывает слабый сигнал и попадает на участок репрессированного гетерохроматина и интрон гена.
8  | Enhancer        | ![8](pictures/UCSC_GenomeBrowser/8.png)   |                                           | Частично попало на экзон, попадает на интрон. Сигнал не очень, но сильный. Ассоциируется с CpGIsland, RefSeqTSS, RefSeqTSS2kb
9  | Promoter        | ![9](pictures/UCSC_GenomeBrowser/9.png)   |                                           | Ассоциируется с CpGIslands, RefSeqExon, RefSeqTSS, RefSeqTSS2kb; попадает на экзон, сильный сигнал.
10 | Enhancer        | ![10](pictures/UCSC_GenomeBrowser/10.png) |                                           | Сильный сигнал и состояние попало на интрон, также состояние ассоциируется с RefSeqGene.
11 | Enhancer        | ![11](pictures/UCSC_GenomeBrowser/11.png) |                                           | Ассоциируется с RefSeqGene, попадает на интрон, слабый сигнал.
12 | Transcriptional | ![12](pictures/UCSC_GenomeBrowser/12.png) |                                           | Ассоциируется с RefSeqGene, попадает на интрон, слабый сигнал (на H3K4m2 и H3K27ac видно, что становится сильнее, но там начинается 11-е состояние).
13 | Enhancer        | ![13](pictures/UCSC_GenomeBrowser/13.png) |                                           | Ассоциируется с RefSeqGene, попадает на интрон, сильный сигнал.
14 | Enhancer        | ![14](pictures/UCSC_GenomeBrowser/14.png) |                                           | Ассоциируется с RefSeqGene, попадает на интрон, сильный сигнал.
15 | Transcriptional | ![15](pictures/UCSC_GenomeBrowser/15.png) |                                           | Ассоциируется с RefSeqGene, попадает на интрон, слабый сигнал.

## Бонус

Полученный *HUVEC_15_dense.bed* был модифицирован вручную и записан в *HUVEC_15_dense_upd.bed* с помощью добавления 15-ти состояний (соответствие номер-название установлено в табличке выше, при работе с *UCSC GenomeBrowser*):

![key](pictures/key.png)

Фрагмент полученного файла:

![HUVEC_15_dense_upd_part](pictures/HUVEC_15_dense_upd_part.png)

Просмотр с выполненной разметкой:

![upd_view](pictures/UCSC_GenomeBrowser/upd_view.png)
