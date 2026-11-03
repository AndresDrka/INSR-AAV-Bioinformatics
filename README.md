# INSR-AAV-Bioinformatics
### Análisis Bioinformático y Diseño In Silico del Gen INSR para Terapia Génica (AAV)

Este proyecto comprende un pipeline bioinformático robusto para la adquisición, control de calidad, alineamiento, análisis estructural y diseño de oligonucleótidos dirigidos al gen **INSR** (Receptor de Insulina). El enfoque simula un flujo de trabajo computacional para optimizar constructos terapéuticos basados en Vectores Adenoasociados (AAV). 

###  Pipeline Bioinformático e Integración de Herramientas

### 1. Adquisición de Datos y Curaduría Ómica

* **NCBI Gene & Nucleotide:** Extracción y descarga automatizada de secuencias de referencia genómicas, transcritos de ARN y secuencias de aminoácidos del gen INSR.
* **UniProt:** Mapeo y análisis de anotaciones funcionales, dominios estructurales y variantes de splicing alternativo de la proteína.

### 2. Procesamiento de Secuencias Masivas (NGS - Illumina Reads)

* **Control de Calidad (QC):** Simulación y preprocesamiento de lecturas crudas indexadas (Illumina Reads) evaluando la calidad por base (Phred score) y remoción de adaptadores técnicos.
* **Alineamiento y Mapeo:** Flujo de alineamiento de lecturas contra la secuencia de referencia. Manejo y cuantificación de **GAPs (indels)** y variantes de un solo nucleótido (SNVs) para evaluar la homogeneidad.

### 3. Alineamiento de Secuencias Múltiples (MSA) y Evolución Molecular

* **EMBL-EBI (Clustal Omega / MUSCLE):** Ejecución de alineamientos múltiples de la secuencia del gen INSR entre diferentes especies de homínidos y modelos murinos.
* **Análisis de Conservación:** Identificación de regiones altamente conservadas y huecos lógicos (**GAPS**) en las alineaciones moleculares.

### 4. Diseño In Silico de Primers y Validación Termodinámica

* **Primer-BLAST (NCBI):** Modelado y optimización de iniciadores (primers) específicos para la amplificación y verificación del gen terapéutico, minimizando la hibridación inespecífica en el genoma humano.
* **OligoAnalyzer (IDT):** Análisis termodinámico riguroso de los oligos diseñados: 

  * Cálculo exacto de temperaturas de fusión (Tm).
  * Evaluación del porcentaje de contenido GC (rango óptimo 40%-60%).
  * Predicción y filtrado de estructuras secundarias deletéreas (auto-dímeros, dímeros de primer y horquillas/hairpins).

###  Estructura de Datos Computacional del Proyecto

El entorno de trabajo mantiene una arquitectura limpia basada en buenas prácticas de reproducibilidad científica: 

* raw_sequences/: Archivos FASTA crudos provenientes de bases de datos globales.
* metadata/: Datos tabulares de anotación, coordenadas de exones e información clínica del gen.
* analyses/: Scripts de alineamiento, logs de ejecución de algoritmos y archivos de salida (BAM/SAM/VCF).
* figures/: Matrices de conservación molecular, histogramas de calidad NGS y diagramas termodinámicos.
* docs/: Reportes de validación de cebadores e informes técnicos del diseño del vector.

*Estudio computacional avanzado enfocado en la convergencia de la Ingeniería de Software y la Biotecnología Médica.*
