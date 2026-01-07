---
author: Arya Lyngdoh Lakshmanan
pubDatetime: 2025-12-31T18:31:15Z
title: CV-pdf
slug: cv-pdf
featured: false
draft: true
tags:
  - Personal
description: An in depth description of my qualifications and experiences
---
# Arya Lyngdoh Lakshmanan
- Location: Brooklyn, NY
- Links: 
	- Email: mailto:arya.l.lakshmanan@gmail.com
	- LinkedIn: http://linkedin.com/in/arya-lyngdoh-lakshmanan
	- Personal Website: https://arya-ll.github.io/
	- GitHub: https://github.com/Arya-LL/
# Overview
I am an M.S. Scientific Computing student at NYU specializing in High-Performance Computing (HPC), GPU Architecture, and Financial Modeling. My background in Astrophysics and Financial Economics, and I have prior experience in architecting low-latency ML pipelines and parallelized simulation engines using Rust, CUDA, and C++.

This document provides a detailed overview of my technical background, research experience, and leadership roles, with an emphasis on systems engineering, GPU computing, and applied machine learning. The sections most relevant to my current skills and goals are [[#Education|Education]], [[#AI and Large Language Model Consultant - Dec 2023 to Apr 2024, May 2025 to Aug 2025|AI and Large Language Model Consultant]], [[#Research Assistant - Sep 2021 to May 2023|Undergraduate Research Project]], [[#Multi-GPU Performance Analytical Model - Sep 2025 to Dec 2025|Multi-GPU Performance Analytical Model]], and  [[#Rust/CUDA Simulation Engine - Sep 2025 to Present|Rust/CUDA Simulation Engine]].

For some other relevant documents, please see
- My resume as a PDF: https://arya-ll.github.io/assets/Arya-Lakshmanan-Resume.pdf
- This CV as a PDF: https://arya-ll.github.io/assets/Arya-Lakshmanan-CV.pdf
- My resume as a webpage: https://arya-ll.github.io/posts/resume/
# Education
## New York University - May 2024 to May 2026

- Master's in scientific computing
- GPA: 3.45/4.00
- Completed Coursework: Machine Learning, GPU Architecture and Programming, Numerical Methods I/II, Fluid Dynamics, Methods of Applied Mathematics, Fundamental Algorithms, Programming Languages, Computer Graphics
## Rutgers University - Sep 2019 to May 2023

- Bachelor of Science - BS
- GPA: 3.75/4.00 - Magna Cum Laude
- Majors: Astrophysics and Economics
- Minor: Math
- Certificate in Financial Economics
- Awards: [[#Henry Rutgers Scholar Award - May 2023|Henry Rutgers Scholar Award]],  [[#Highest Honors in Astrophysics - May 2023|Highest Honors in Astrophysics]],  [[#Aryabhata Endowed Award in Astronomy - May 2023|Aryabhata Endowed Award in Astronomy]],  [[#Robert L. Sells Scholarship - May 2022|Robert L. Sells Scholarship]],  [[#SAS Paul Robeson Scholar - May 2023|Paul Robeson Scholar]],  [[#SAS Excellence Award - May 2021, May 2022|Excellence Award]]
# Experience

## AI and Large Language Model Consultant - Dec 2023 to Apr 2024, May 2025 to Aug 2025
*Wordsworth Tech Inc. (StreamAlive)*

As an AI and LLM Consultant, I proposed and developed the integration of generative AI into WordsworthTech's StreamAlive(https://www.streamalive.com/) product, focusing on enhancing functionality while managing costs effectively. 
- **Core API Development:** I developed a NodeJS API to seamlessly integrate cost-efficient LLM models (Gemini/OpenAI) into the existing development stack. To handle the variability of AI outputs, I built custom validation logic and parsers to ensure the data used by the application was consistent and reliable.
- **Performance & Strategy**: I established metrics to track token usage and response quality. Using these, I implemented caching and prompt-tuning strategies that reduced operational costs while maintaining model performance.
- **Tooling Expansion**: I created custom plugins for Stream Deck and Google Slides, allowing users to access the platform's generative AI features directly from their existing workflows.
## Research Assistant - Sep 2021 to May 2023
*Rutgers University | Advisor: Dr. Kristen McQuinn*

I researched the impact that time-periods with heightened star deaths/bursts have on the dark matter distributions within nearby dwarf galaxies. I led this project with the guidance of Dr. Kristen McQuinn - NASA Roman Space Telescope Mission Head. This project dovetails into a larger (unpublished as of Dec 2025) investigation.
- **Data Validation:** I gathered archival images from the Spitzer and Hubble space telescopes, and I developed data cleaning Python scripts to identify and interpolate over contaminants. I validated the cleaning process by sampling and analyzing the data distributions over the interpolated regions.
- **Data Analysis and Modeling:** I created best-fit models using Python to represent the data accurately. I analyzed the impact of varying initial guesses/hyper-parameters on the resulting models and ensured that the models were stable.
- **Outcomes**: I presented my findings as an undergraduate thesis, earning me [[#Highest Honors in Astrophysics - May 2023|Highest Honors in Astrophysics]].
## Teaching Assistant - Sep 2021 to May 2023
*Rutgers Learning Center*

- **Instruction**: I taught and mentored over 80 undergraduate students through recitations for an upper-level course focused on formal-based logic and set theory.
- **Content Creation**: I developed and tailored teaching materials and exercises to meet diverse student group needs, translating complex mathematical proofs into digestible algorithmic concepts. 

# Projects
## Multi-GPU Performance Analytical Model - Sep 2025 to Dec 2025
*Technologies: CUDA, C++, Python*

I formulated and validated a predictive framework to analyze parallel scaling efficiency across multi-GPU clusters. The project focused on quantifying the trade-offs between raw computation throughput and interconnect latency (PCIe) to identify hardware bottlenecks in high-performance computing workloads.
- **Hardware Calibration:** I implemented low-level micro-benchmarks in CUDA to measure hardware specific timing costs, such as PCIe throughput and peak FLOPs. This allowed me to generalize the model to arbitrary Nvidia architectures/devices.
- **Validation Strategy:** I validated the analytical model against standard bottlenecked algorithms, such as N-Body simulations (compute-bound) and Conjugate Gradient solvers (memory-bound), successfully identifying hardware saturation points.
- **Scaling Optimization:** By analyzing synchronization overhead versus computation time, I developed a set of heuristics to recommend optimal scaling strategies for parallelized algorithms.

## Rust/CUDA Simulation Engine - Sep 2025 to Present
*Technologies: Rust, wgpu, CUDA, C*

I architected a high-performance Newtonian gravitational model using finite differences to model sci-fi solar systems, migrating the project from a legacy WebGL/JavaScript stack to Rust, CUDA, and wgpu.
- **Parallel Texture Synthesis:** I engineered specialized CUDA kernels to generate high-resolution planetary textures. By offloading procedural noise algorithms to the GPU, I achieved real-time synthesis speeds that allow for a fluid user experience.
- **Deterministic Physics:** I implemented a parametric modeling pipeline based on Keplerian orbital mechanics and realistic planet compositions. This ensured that that procedurally generated systems—including frost lines and atmospheric compositions—strictly adhered to physical laws and deterministic bounds.
- **Systems Architecture:** The migration to Rust and wgpu allowed for a unified graphics backend that reduced runtime overhead and guaranteed handling of edge cases.
## Rust-Based Deep Learning Audio Classifier - Aug 2024 to Present
*Technologies: Rust, Burn, Tokio*

I engineered an asynchronous, multi-threaded deep learning inference pipeline using the Burn framework to classify complex audio features. The system was designed to handle high-throughput data ingestion without blocking the main event loop, utilizing Rust's ownership model to guarantee thread safety.
- **Transformer Architecture:** I deployed Transformer-based attention mechanisms to process sequential audio data, implementing a custom classification batcher.
- **Memory Optimization:** I developed dynamic padding masks to efficiently handle variable-length audio sequences. This eliminated redundant computation during inference and significantly optimized GPU memory usage.
- **Concurrency:** Using Tokio, I designed a non-blocking data ingestion layer capable of managing concurrent API requests, ensuring the system could scale to handle high-frequency input streams.
# Organizations

## Rutgers Astronomical Society Treasurer and President - May 2021 to May 2023

I led the Rutgers Astronomical Society (RAS)(https://ras.physics.rutgers.edu/), a student organization dedicated to public outreach and education. As treasurer and president, I made RAS one of the top 5 most attended student organizations in Rutgers by developing several lasting programs and securing funding for the organization's expansions.
- **Leadership:** I orchestrated weekly public observing nights and astronomy seminars for 100+ attendees. I created lasting programs by expanding volunteer roles and developing a merchandise program, resulting in sustainable funding and manpower.
- **Initiatives and Expansion:** I created and organized two annual special projects to widen the organization's reach - a state park trip for naked-eye nighttime observing and an engineering/physics showcase. I also founded an astrophotography program, creating access to education and tooling without barriers to entry.
- **Public Speaking**: I delivered presentations in both weekly meetings  and science fairs on complex topics like classical astronomy, dark matter, and cosmology to audiences ranging from elementary school students to astronomy professors.
- **Community and Inclusivity:** I spearheaded RAS's position as an LGBTQ+ safe space through collaboration with minority advocacy groups.

## Yam-Studios; Game Development

- Founded and led a five-person team (Yam Studios) in a three-month indie game project using Unreal Engine 5.
- Managed project logistic, directed game design, and coordinated a diverse team of specialists.

# Honors and Awards

## Henry Rutgers Scholar Award - May 2023

- Issued by Rutgers School of Arts and Sciences.
- The Henry Rutgers Scholar Award of the School of Arts and Sciences recognizes graduating seniors who have completed outstanding independent research projects leading to an interdepartmental thesis or a thesis in their major field of study. The awards are offered across all departments of the School of Arts and Sciences, and so represent only the very finest achievements of our students.

## Highest Honors in Astrophysics - May 2023

- Issued by Rutgers Physics & Astronomy Department.
- This honor was only given to myself and one other graduating senior among all graduating seniors in astrophysics. It was given for an excellent academic record and my research project

## Aryabhata Endowed Award in Astronomy - May 2023

- Issued by Rutgers Physics & Astronomy Department.
- The Aryabhata Endowed Award in Astronomy is given annually to a physics and astronomy undergraduate who, in the judgment of the physics faculty, has demonstrated outstanding academic performance in astronomy.

## Robert L. Sells Scholarship - May 2022

- Issued by Rutgers Physics & Astronomy Department.
- The Robert L. Sells Scholarship is awarded annually to two Rutgers physics majors who, in the judgment of the physics faculty, have demonstrated outstanding academic excellence.

## SAS Paul Robeson Scholar - May 2023

- Issued by Rutgers School of Arts and Sciences(SAS).
- Award recognizing all students within SAS who complete a department-based honors thesis.

## SAS Excellence Award - May 2021, May 2022

- Issued by Rutgers School of Arts and Sciences(SAS).
- Awardees are invited to apply for an excellent academic record. They are then awarded contingent on a strong record of service to the university and/or the community and outstanding essay.

# Test Scores

## General GRE - Sep 2022

- Quantitative Reasoning: 170/170, 96th percentile
- Verbal Reasoning: 163/170, 92nd percentile
- Analytical Writing: 4/6, 54th percentile
## Physics Subject GRE - Oct 2022

- Physics: 840, 70th percentile
- Classical Mechanics: 088, 79th percentile
- Electromagnetism: 083, 71st percentile
- Quantum Mechanics & Atomic Physics: 088, 79th percentile
## ACT - Dec 2017
- 36/36
# Volunteering

## Scio Virtual - Apr 2021 to Jul 2021

I taught a class of 14 students on the fundamentals of astronomy and physics. The students ranged from elementary to high school, and I developed my own syllabus and activities to engage accross this age range. I taught the class virtually and utilized the subject to expose the students to data analysis and thinking with physical models. The proceeds from my class went towards COVID-19 relief through foodbanks connected with ScioVirtual.
## Leap for Lungs - Jan 2019 to Jun 2019

Leap for Lungs built the world’s largest hopscotch course to raise funds for lung cancer research. I created marketing materials and organized transportation for the organization.
## Raptor Trust - Feb 2017 to May 2017

I volunteered at a bird hospital and sanctuary where I fed and cared for 40 or so recovering birds, maintained 10 enclosures, restocked food and infirmary supplies, and cleaned towels and beds