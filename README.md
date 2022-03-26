# hse_hw3_chromhmm

## Список анализируемых меток

**Клеточная линия:** A549

**Контроль:** ControlEtoh02AlnRep1 (ControlEtoh02AlnRep1.bam)

Гистоновая метка | Имя файла    | Оригинальный файл
:---------------:|:------------:|:-----------------:
H3k09me3         | H3k09me3.bam | wgEncodeBroadHistoneA549H2azDex100nmAlnRep1.bam
H3k04me2         | H3k04me2.bam | wgEncodeBroadHistoneA549H3k27acDex100nmAlnRep1.bam
H3k04me1         | H3k04me1.bam | wgEncodeBroadHistoneA549H3k27me3Dex100nmAlnRep1.bam
H2az             | H2az.bam     | wgEncodeBroadHistoneA549H3k36me3Dex100nmAlnRep1.bam
H3k04me3         | H3k04me3.bam | wgEncodeBroadHistoneA549H3k04me1Dex100nmAlnRep1.bam
H3k36me3         | H3k36me3.bam | wgEncodeBroadHistoneA549H3k04me2Dex100nmAlnRep1.bam
H3k27ac          | H3k27ac.bam  | wgEncodeBroadHistoneA549H3k04me3Dex100nmAlnRep1.bam
H3k09ac          | H3k09ac.bam  | wgEncodeBroadHistoneA549H3k79me2Dex100nmAlnRep1.bam
H3k27me3         | H3k27me3.bam | wgEncodeBroadHistoneA549H3k09acEtoh02AlnRep1.bam
H3k79me2         | H3k79me2.bam | wgEncodeBroadHistoneA549H3k09me3Etoh02AlnRep1.bam

**cellmarkfiletable.txt:**

![cellmarkfiletable](pictures/cellmarkfiletable.png)

## Работа с ChromHMM

[Ссылка на Colab](https://colab.research.google.com/drive/1llVs1T7x1bb0oZD-fxRHMYG6F-CQfdNV?usp=sharing)

## Отчет ChromHMM

overlap                                             | emissions
:--------------------------------------------------:|:--------------------------------------:
![img](pictures/ChromHMM/overlap.png)               | ![img](pictures/ChromHMM/emissions.png)

RefSeqTSS_neighborhood            | RefSeqTES_neighborhood            | transitions
:--------------------------------:|:---------------------------------:|:----------------------------------------:
![img](pictures/ChromHMM/TSS.png) | ![img](pictures/ChromHMM/TES.png) | ![img](pictures/ChromHMM/transitions.png)

## UCSC GenomeBrowser

Участки генома и соответствующие эпигенетические типы (и, желательно, профили эпигенетических меток).

 № | Название        | Полное изображение
:-:|:---------------:|:-----------------------------------------:
1  | Repressed       | ![1](pictures/UCSC_GenomeBrowser/1.png)
2  | Heterochromatin | ![2](pictures/UCSC_GenomeBrowser/2.png)
3  | Repressed       | ![3](pictures/UCSC_GenomeBrowser/3.png)
4  | Repressed       | ![4](pictures/UCSC_GenomeBrowser/4.png)
5  | Transcriptional | ![5](pictures/UCSC_GenomeBrowser/5.png)
6  | Transcriptional | ![6](pictures/UCSC_GenomeBrowser/6.png)
7  | Transcriptional | ![7](pictures/UCSC_GenomeBrowser/7.png)
8  | Enhancer        | ![8](pictures/UCSC_GenomeBrowser/8.png)
9  | Enhancer        | ![9](pictures/UCSC_GenomeBrowser/9.png)
10 | Enhancer        | ![10](pictures/UCSC_GenomeBrowser/10.png)
11 | Promoter        | ![11](pictures/UCSC_GenomeBrowser/11.png)
12 | Promoter        | ![12](pictures/UCSC_GenomeBrowser/12.png)
13 | Promoter        | ![13](pictures/UCSC_GenomeBrowser/13.png)
14 | Promoter        | ![14](pictures/UCSC_GenomeBrowser/14.png)
15 | Enhancer        | ![15](pictures/UCSC_GenomeBrowser/15.png)

### Рассуждения и списки гистоновых модификаций, на которые состояния попадают чаще всего

1. **Repressed.**
   - Слабый сигнал, попадает на интрон.
   - Ассоциируется с laminB1lads.
   - Гистоновые модификации:
     - H3k27me3
2. **Heterochromatin.**
   - Наиболее распространенное состояние. Самые частые и длинные отрезки помечены как 2-е состояние.
   - Показывает слабый сигнал и попадает на участок репрессированного гетерохроматина и интроны генов.
   - Ассоциируется с laminB1lads.
3. **Repressed.**
    - Слабый сигнал (кроме H3k09me3), ассоциируется с ядерной ламиной, может не попадать на ген или попадать на интрон.
    - Ассоциируется с laminB1lads.
    - Гистоновые модификации:
      - H3k09me3
4. **Repressed.**
    - Попадает на интроны и экзоны генов.
    - Сильный сигнал.
    - Ассоциируется с: RefSeqGene, RefSeqTES.
    - Гистоновые модификации:
      - H3k36me3
      - H3k09me3
5. **Transcriptional.**
   - Ассоциируется с: RefSeqTES, RefSeqGene.
   - Попадает на интрон.
   - Сильный сигнал для H3k36me3, средний для H3k09me3, в остальном слабый.
   - Гистоновые модификации:
     - H3k36me3
6. **Transcriptional.**
    - Ассоциируется с: RefSeqGene.
    - Гистоновые модификации:
      - H3k79me2
7. **Transcriptional.**
    - Ассоциируется с: RefSeqGene.
    - Низкий сигнал.
    - Гистоновые модификации:
      - H3k79me2
      - H3k04me1
8. **Enhancer**
   - Ассоциируется с: RefSeqTES, RefSeqGene.
   - Сильный сигнал.
   - Гистоновые модификации:
     - H3k04me1
9. **Enhancer.**
    - Ассоциируется с: RefSeqTES, RefSeqGene.
    - Сильный сигнал.
    - Гистоновые модификации:
      - H3k04me1
      - H3k04me2
10. **Enhancer**
    - Ассоциируется с: RefSeqTES, RefSeqTSS2kb.
    - Сильный сигнал.
    - Гистоновые модификации:
      - H3k04me1
      - H3k04me2
      - H3k27ac
      - H3k09ac
11. **Promoter**
    - Ассоциируется с: CpGIsland, RefSeqExon, RefSeqTSS, RefSeqTSS2kb.
    - Попадает на экзон.
    - Сильный сигнал для H2az, H3k04me2, H3k04me3, H3k09ac. Средней силы сигнал для H3k27ac.
    - Гистоновые модификации:
      - H3k27ac
      - H3k09ac
      - H3k04me3
12. **Promoter.**
    - Ассоциируется с: RefSeqTSS.
    - Высокий сигнал для H3k04me2, H3k04me3, H3k27me3.
    - Гистоновые модификации:
      - H3k27ac
      - H3k04me2
      - H3k04me3
13. **Promoter.**
    - Ассоциируется с: RefSeqTES, RefSeqGene.
    - Сильный сигнал кроме H2az, H3k09me3, H3k27me3.
    - Гистоновые модификации:
      - H3k04me2
      - H3k79me2
      - H3k09ac
14. **Promoter.**
    - Ассоциируется с: CpGIsland, laminB1lads.
    - Сильный сигнал.
    - Гистоновые модификации:
      - H2az
      - H3k04me2
      - H3k04me3
15. **Enhancer.**
    - Ассоциируется с laminB1lads.
    - Попадает на интрон гена.
    - Сильный сигнал.
    - Гистоновые модификации:
      - H2az
      - H3k04me1

## Бонус

Полученный *A549_15_dense.bed* был модифицирован вручную (Ctrl+F и "Заменить все") в *A549_15_dense_upd.bed* с помощью добавления 15-ти состояний по примеру:

![key](pictures/key.png)

Состояния соотносились с их названиями по табличке с работой в **UCSC GenomeBrowser**.

Фрагмент полученного файла:

![A549_15_dense_upd_part](pictures/A549_15_dense_upd_part.png)

### Просмотр с выполненной разметкой

![upd_view](pictures/UCSC_GenomeBrowser/upd_view.png)
