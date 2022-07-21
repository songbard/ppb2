# ppb2
__Collaborative Analysis and Reporting of Portland OR USA Police Department Data__

___Unless otherwise labelled, material in this repository is subject to copyright and licensed for free duplication and modification under the most recent version of the Replication Commons Public License, posted at www.replicationcommons.org.  In return for free access and the right to create downstream work from the licensed work, the Replication Commons Public License requires users to provide sufficient code and data for their downstream work to be replicated, and to require uses of their work to do the same.  In other words, the License sustains the norms and practices of high-quality public-domain science.  Copying or use of material from this repository's consitutes acceptance of this license.___ 

_UPDATE 20 JULY 2022:  J Brown uploaded 2 more quarters of PPB use of force data and added it to the existing FDCR dataset.  He went carefully through the original program, called ppb_force_notebook_3_initial_wrangling.Rmd, fixed bugs, made sure the program correctly processed the new data, and saved new output datasets.  The new program is called "script_1_ppbforce_thru_2022_q1.Rmd".    The new dataset is called "ppbforce_clean_q122.csv".

__UPDATE 14 June 2022: J Brown created this repository "ppb2" to replace the original repository "ppb".  The new ppb2 repo has the ability to hold, push, and pull large files like the datasets used and created in the project.  If you want to talk about  participating in this project, please email Dr. Brown at jonabrown@gmail.com.  Most or Dr. Brown's effort right now is focused on creating a scientific publication that reports and tests explanations for the findings reported per the 30 Apr update, below.__

__UPDATE 12 June 2022:  Here is an outline of the sequence of programs and datasets that we have generated so far. There are 4 large scripts (programs).  The scripts are written as RMarkdown Notebooks, so that the development of ideas, hypotheses, and understandings can be documented in real time--just like a laboratory notebook.  RMarkdown scripts bear the suffix, Rmd.  The output of each Rmd is an input or the input to the next.  The fifth major program will be the first scientific paper and it will be developed in Quarto, which is a new version of RMarkdown.  This will use datasets and code from the first 4 scripts and will evolve into a finished product rather than remain as a "Notebook."__

INPUT TO PROGRAM 1:  "raw_ppb_force_thru_q1_2022.csv"
		

PROGRAM 1: "script_1_ppbforce_thru_2022_q1.Rmd"
		# this program examines the raw PPB use of force dataset and cleans up missing data, weird data, and modifies variables to create permanent variables for use in later analysis.  After I inspected and cleaned, I gave each variable a permanent name.  The names group the vars by class, eg, forcen_xxxx refers to descriptors of each application of force, incid_xxxx denotes vars that describe the officer’s overall encounter with the civilian, civil_xxxx describes the civilian, etc.

OUTPUT OF PROGRAM 1:  "ppbforce_clean_q122.csv"
		# 
………………………
INPUT TO PROGRAM 2: "ppbforce_clean_q122.csv"

AS OF JULY 20 2022, UPDATING TO INCLUDE NEW DATA STOPS HERE.  THE PROGRAM NAMES AND DATASET NAMES BELOW APPLY TO DATA ENDED Q3 2021.

PROGRAM 2: create_incident_ds.Rmd
		# this is the program that converts the PPB use of force data into a dataset whose observations are INCIDENTS of use of force.  One incident can involve up to several officers.  The rows of the raw PPB dataset are individual Force Data Collection Reports, FDCRs, which only describe what one officer did.  

OUTPUT OF PROGRAM 2: ppbforce_incident_ds_321.csv
……………………….

INPUTS TO PROGRAM 3:    ppbforce_incident_ds_321.csv
				DispatchedCalls_OpenData_2021.csv
				DispatchedCalls_OpenData_2020.csv
				DispatchedCalls_OpenData_2019.csv
				DispatchedCalls_OpenData_2018.csv
				(The dispatch datasets are created by the Portland Bureay of Emergency Communication, primarily from calls to 911.)
        
PROGRAM 3:  ppb_dispatch.Rmd
		# this program combines the incident dataset with the raw annual dispatch files downloaded from PPB.  There is a pseudo-matching process because PPB does not allow the public to see the full calendar dates of force events.

OUTPUT OF PROGRAM 3:   ppbdispatch_incident_321.csv  (This is a VERY large dataset, most cell values are zero.)

…………………………
INPUT TO PROGRAM 4:  ppbdispatch_incident_321.csv

PROGRAM 4:  ppb_improvement_testing.Rmd
		# this is where I tested my prespecified hypotheses about reductions in use of force during dispatched events likely to involve mentally ill and substance using civilians.

OUTPUT OF PROGRAM 4:  tables and figures and stats, no new dataset.

………………………

__UPDATE 30 April 2022:  Based on work contained in this repository, Dr. Brown presented testimony to the US District Court for Oregon about changes since 2017 in the rate, burden, and severity of use of force against persons likely to be mentally impaired in Portland, Oregon.  See https://www.courthousenews.com/wp-content/uploads/2022/04/Force-is-Up.pdf.__

This GitHub repository is a space for collaboration and documentation of analyses of policing, and particularly of the use of force by the Portland Police Bureau (PPB).  The work may eventually expand to other bureaus and multi-city analyses.

The now publicly released PPB data were developed as part of a Settlement Agreement between the US Dept of Justice and the Portland Police Bureau to reduce illegal and unconstitutional use of force against persons with mental illness, including persons with substance abuse disorder.  In addition to providing raw data, PPB publishes its own quarterly reports on use of force by its officers and provides an interactive dashboard that allows simple cross-tabulation of these and other data on the Bureau's website, www.https://www.portland.gov/police/open-data.  A "court monitor," the Compliance Officer/Community Liaison (COCL) also posts quarterly reports based on data provided by PPB.  The City of Portland contracts with Rosenbaum and Associates LLC to act as the COCL.

The initial focus of the work is to measure and explain changes in use of force against persons with mental illness and substance use disorder.    

We have so far used the powerful free and open-source data-handling and statistical software, R.  However, any statistical software can be used in the GitHub environment.  Initial, interim, and final datasets are posted in this repo as csv files so that any program can be applied to the data.  

Each R script (program) indicates which R packages must be loaded and used to run that script, and each contains the code and links to source datasets necessary to run that script.  So far, R scripts have been written with the RMarkdown package, which allows one to produce a pdf or other document to document ones thinking and work and/or to draft a formal publication that is easy to revise.

Papers and reports for publication are being drafted using QUARTO, which is a new and improved Markdown environment that allows many languages and IDEs to be produce a document, and that makes it easier to "see what you make" during the writing/coding process.  We are using ZOTERO, a free open-source reference manager to handle the citations, at least for the first scientific paper, which is targetted for the journal, PLOS One, and therefore must be submitted in MS WORD.

The work was started by Jonathan Betz Brown, MPP, PhD, working with the Portland Mental Health Alliance, of which he is a member.  There is no financial or institutional sponsorship. Participants are volunteers.  Dr. Brown pays for the GitHub hosting and is the initial administrator of the site.  For additional information, please contact Dr. Brown at jonabrown@gmail.com.

What is asked of participants?:  honesty, an unbiased scientific approach, commitment to open access and transparency, responsible behavior, and shared authorship if academic papers are submitted based on collaborative work.  Users of our code and data do not need to post your work to this repository but we hope you want to work with us.



