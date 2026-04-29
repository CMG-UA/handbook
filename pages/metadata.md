---
title: Metadata
nav_order: 1
parent: LTS (long term storage)  # optional grouping
---

# Metadata 

Adding metadata to your directory is so important! \
Because now you know what the data is about or what you did with it, but will you still remember this in tree years?? 

To help with this we have made two options: 

[Script for generating metadata file](https://github.com/CMG-UA/handbook/blob/master/assets/files/automated_METADATA.sh)

[Input of metadata txt file you can copy](https://raw.githubusercontent.com/CMG-UA/handbook/refs/heads/master/assets/files/METADATA_teste_metadata_script.txt)

## Content of the files
* Script that you can run 
    ````
    #!/bin/bash

    # Prompt for location and define the metadata file path
    read -p "Enter location: " LOCATION
    mkdir -p  "$LOCATION"

    # Collecting project name
    read -p "Fill in the Project Name (without spaces): " PROJECT_NAME
    METADATA_FILE="${LOCATION}/METADATA_${PROJECT_NAME}.txt"
    echo "Metadata file: ${METADATA_FILE}"
    # Project Information
    echo "| Field                   | Description                                                                          |" >> $METADATA_FILE
    echo "|-------------------------|--------------------------------------------------------------------------------------|" >> $METADATA_FILE
    echo "| Project Name            | ${PROJECT_NAME}" >> $METADATA_FILE

    read -p "Give a small project description:  " PROJECT_DESCRIPTION
    echo "| Project Description     | ${PROJECT_DESCRIPTION}" >> $METADATA_FILE

    read -p "Start date of the project: "  PROJECT_START_DATE
    echo "| Start Project Date      | ${PROJECT_START_DATE}" >> $METADATA_FILE

    read -p "Current status of the project (e.g., submitted, in progress, completed): " PROJECT_STAT
    echo "| Project Status          | ${PROJECT_STAT}" >> $METADATA_FILE

    # User Information
    read -p "Name of the user requesting the service: " USER_NAME
    echo "| User Name               | ${USER_NAME}" >> $METADATA_FILE

    read -p "Email address of the user requesting the service: " USER_EMAIL
    echo "| User Email              | ${USER_EMAIL}" >> $METADATA_FILE

    read -p "Principal investigator: " PRI_INV
    echo "| Principal Investigator  | ${PRI_INV}" >> $METADATA_FILE

    read -p "Collaborator: "  COLLAB
    echo "| Collaborator            | ${COLLAB}" >> $METADATA_FILE

    # Service Request Information
    read -p "Type of bioinformatics service requested (e.g., sequencing, analysis, consultation): " SERVICE_TYPE
    echo "| Service Type            | ${SERVICE_TYPE}" >> $METADATA_FILE

    # Sample Information
    read -p "Type of biological sample (e.g., DNA, RNA, whole genome, exome): " SAMPLE_TYPE
    echo "| Sample Type             | ${SAMPLE_TYPE}" >> $METADATA_FILE

    read -p "Organism from which the sample was obtained: " ORGANISM
    echo "| Organism                | ${ORGANISM}" >> $METADATA_FILE

    read -p "Cell line (if applicable): " CELL_LINE
    echo "| Cell Line               | ${CELL_LINE}" >> $METADATA_FILE

    # Sequencing Information
    read -p "Library prep (if applicable): " LIBRARY_PREP
    echo "| Library  prep           | ${LIBRARY_PREP}" >> $METADATA_FILE

    read -p "Sequencing technology used (e.g., Illumina, PacBio, Oxford Nanopore): " SEQ_PLAT
    echo "| Sequencing Platform     | ${SEQ_PLAT}" >> $METADATA_FILE

    read -p "Specific sequencing instrument used (e.g., HiSeq 2500, NovaSeq 6000): " SEQ_INSTR
    echo "| Sequencing Instrument   | ${SEQ_INSTR}" >> $METADATA_FILE

    read -p "Length of the sequencing reads (e.g., 100 bp, 150 bp): " READ_LENGTH
    echo "| Read Length             | ${READ_LENGTH}" >> $METADATA_FILE

    read -p "Indicates whether the sequencing was paired-end or single-end: " PAIRED_OR_SINGLE
    echo "| Paired or Single-End    | ${PAIRED_OR_SINGLE}" >> $METADATA_FILE

    read -p "Average sequencing depth or coverage: " SEQ_DEPT
    echo "| Sequencing Depth        | ${SEQ_DEPT}" >> $METADATA_FILE

    # Data Information
    read -p "Format of the input data (e.g., FASTQ, BAM, VCF): " DATA_FORMAT
    echo "| Data Format             | ${DATA_FORMAT}" >> $METADATA_FILE

    read -p "Location where the input data is stored: " DATA_LOCATION
    echo "| Data Location           | ${DATA_LOCATION}" >> $METADATA_FILE

    # Analysis Information
    read -p "Type of bioinformatics analysis requested (e.g., alignment, variant calling, RNA-seq): " ANA_TYPE
    echo "| Analysis Type           | ${ANA_TYPE}" >> $METADATA_FILE

    read -p "Specific parameters or settings used for the analysis: " ANA_PARAMS
    echo "| Analysis Parameters     | ${ANA_PARAMS}" >> $METADATA_FILE

    read -p "Reference genome used for the analysis (e.g., hg38, mm10): " REF_GENOME
    echo "| Reference Genome        | ${REF_GENOME}" >> $METADATA_FILE

    read -p "Format of the output data (e.g., BAM, VCF, CSV): " OUT_FORMAT
    echo "| Output Format           | ${OUT_FORMAT}" >> $METADATA_FILE

    read -p "Location where the output data will be stored: " OUT_LOCATION
    echo "| Output Location         | ${OUT_LOCATION}" >> $METADATA_FILE

    # Billing Information
    read -p "Funding: " FUNDING
    echo "| Funding                 | ${FUNDING}" >> $METADATA_FILE

    # Analyst Information
    read -p "Name of the bioinformatician or analyst working on the service: " ANA_NAME
    echo "| Analyst Name            | ${ANA_NAME}" >> $METADATA_FILE

    read -p "If published, link to publication: "  PUB_LINK
    echo "| Publication Link        | ${PUB_LINK}" >> $METADATA_FILE

    read -p "If data in public repository, link to repository: "   PUB_REPO
    echo "| Public Repository Link  | ${PUB_REPO}" >> $METADATA_FILE

    # Additional Information
    read -p "Additional comments or special instructions: " COMMENTS
    echo "| Comments                | ${COMMENTS}" >> $METADATA_FILE

    echo "Metadata collection complete. The details have been saved to ${METADATA_FILE}."
    ````
* A text file that you can copy 
    ````
    | Field                   | Description                                                                          |
    |-------------------------|-----------------------------------------------------------|
    | Project Name            | teste_metadata_script
    | Project Description     | testing the metadatascript
    | Start Project Date      | 29/04/2026
    | Project Status          | in progress
    | User Name               | Marie Hannaert
    | User Email              | marie.hannaert@uantwerpen.be
    | Principal Investigator  | Arvid
    | Collaborator            | Lauren Moons
    | Service Type            | analysis
    | Sample Type             | DNA
    | Organism                | human
    | Cell Line               | /
    | Library  prep           | /
    | Sequencing Platform     | Oxford Nanopore
    | Sequencing Instrument   | /
    | Read Length             | /
    | Paired or Single-End    | PE
    | Sequencing Depth        | 10x
    | Data Format             | FASTQ
    | Data Location           | LTS hopefully
    | Analysis Type           | variant calling
    | Analysis Parameters     | /
    | Reference Genome        | hg38
    | Output Format           | BAM
    | Output Location         | here needed LTS
    | Funding                 | none
    | Analyst Name            | Lauren Moons
    | Publication Link        | /
    | Public Repository Link  | not EGA
    | Comments                | test test  
    ````