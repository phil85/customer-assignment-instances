<a href="http://www.unibe.ch/">
    <img src="https://www.unibe.ch/media/logo_unibern@2x.png" alt="UniBern Logo" title="University Bern" align="right" width="12%" height="70%"  /> </a>

<br>
<br>

# Customer assignment instances

<p align="justify">
The repository contains all generated problem instances described in the paper <i>A matheuristic for a large-scale customer assignment problem in direct marketing</i>. This documentation describes how the instances are structured and explains how to download the instances on a standard PC or Mac.
</p>

## Table of contents

- [Download instances](#download-instances)
- [Overview instances](#overview-instances)
- [Data description](#data-description)
- [Attribution](#attribution)

<br>
<br>

## Download instances
<p align="justify">
The  generated problem instances are hosted on <a href="https://github.com/" target="_blank"> GitHub. </a> To download the instances to your machine you can either download the code as a zip file or clone the repository using Git. 
</p>

---

### Option 1: Download code as ZIP-file
**Step 1:** Go to the website <a href="https://github.com/phil85/customer-assignment-instances" target="_blank"> https://github.com/phil85/customer-assignment-instances. </a>

**Step 2:** Select the tab 'Code' and click on 'Download ZIP'. The instances are downloaded as a zip file. Unzip the file and select your desired target location.

---

### Option 2: Clone repository from GitHub using [Git Large File Storage (LFS)](https://git-lfs.github.com/)
**Step 1:** Go to the website <a href="https://github.com/phil85/customer-assignment-instances" target="_blank"> https://github.com/phil85/customer-assignment-instances. </a>

**Step 2:** Select the tab 'Code' and copy the HTTPS URL.

**Step 3:** Navigate to the desired location and open Git in terminal (Mac) or with Git Bash (Windows) and type the following command.
``` git
git lfs install
git clone https://github.com/phil85/customer-assignment-instances.git
```
--- 
<br>
<br>

## Overview instances

<p align="justify">
The table below provides an overview of all 24 generated instances. These instances include small (GS1-GS8), medium (GM1-GM8), and large (GL1-GL8) instances. The small instances comprise up to 20,000 customers and 75 activities, the medium instances comprise up to 200,000 customers and 125 activities, and the large instances comprise up to 1,000,000 customers and 175 activities. We generated for each combination of customers and activities four instances by varying the eligibility fraction (small/large) and the number of eligibility patterns (few/many). The eligibility fraction specifies the percentage of activities a customer is eligible for on average. The eligibility fraction in this table might slightly differ from the actual eligibility fraction of the instance as a consequence of the randomized generation process.
</p>

<br>

| ID  | Customers  | Activities     | Eligibility fraction [%]| Eligibility patterns | 
| :-- |        --: |            --: | :--                            | :-- 		              |
| GS1 | 10,000     | 50		        | small  (5)    		         | few (50)		          |
| GS2 | 10,000     | 50		        | large (15)   		             | few (50)		          |
| GS3 | 10,000     | 50 	        | small  (5)  		             | many (100)	          |
| GS4 | 10,000     | 50 	        | large (15)	                 | many (100)	          |
| GS5 | 20,000     | 75 	        | small  (5)   	                 | few (50)		          |
| GS6 | 20,000     | 75 	        | large (15) 	                 | few (50)		          |
| GS7 | 20,000     | 75 	        | small  (5)  	                 | many (100)	          |
| GS8 | 20,000     | 75 	        | large (15)  		             | many (100)	          |
| GM1 | 100,000    | 100 	        | small  (5) 		             | few (300)	          |
| GM2 | 100,000    | 100 	        | large (15) 	                 | few (300)	          |
| GM3 | 100,000    | 100 	        | small  (5) 	                 | many (800)	          |
| GM4 | 100,000    | 100 	        | large (15) 	                 | many (800)	          |
| GM5 | 200,000    | 125 	        | small  (5) 	                 | few (300)	          |
| GM6 | 200,000    | 125 	        | large (15) 	                 | few (300)	          |
| GM7 | 200,000    | 125            | small  (5) 	                 | many (800)	          |
| GM8 | 200,000    | 125	        | large (15) 	                 | many (800)	          |
| GL1 | 500,000    | 150 	        | small  (5) 	                 | few (300)	          |
| GL2 | 500,000    | 150 	        | large (15)        	         | few (300)	          |
| GL3 | 500,000    | 150 	        | small  (5)                     | many (1,000)	          |
| GL4 | 500,000    | 150 	        | large (15) 	                 | many (1,000)	          |
| GL5 | 1,000,000  | 175 	        | small  (5) 	                 | few (300)	          |
| GL6 | 1,000,000  | 175 	        | large (15) 	                 | few (300)	          |
| GL7 | 1,000,000  | 175 	        | small  (5) 	                 | many (1,000)	          |
| GL8 | 1,000,000  | 175 	        | large (15)	                 | many (1,000)	          |
---

<br>
<br>

## Data description
<p align="justify">
The information that is required to generate the sets and parameters used in the matheuristic and the mixed-binary linear programming formulations for a specific instance can be derived from four tables. These tables are presented and briefly described below.
</p>

---

#### Table 1

Table 1 provides information on the activities. It is structured as follows:

| Activity  | Day  | Channel | Target products |  Cost |
| :--: 	    |  :--:|  :--:   |       :--:      |  :--: |
| ... 	    |  ... |  ...    | ...             |  ...  |

<p align="justify">
The table shows for each activity the day on which it takes place, the channel over which customers are contacted, the target products that are promoted, and the cost per assignment.
</p>

---

#### Table 2

Table 2 provides information on each possible assignment. It is structured as follows:

| Customer  | Activity  | Expected profit  | Response probability |
| :--: 	    |  :--:		|  :--: 	       |       :--:  		  |
| ... 	    |  ...      |  ...  	       | ...           		  |

<p align="justify">
The table specifies the expected profit and the response probability for each possible assignment.
</p>

---

#### Table 3

Table 3 provides information on the business constraints and the contact rules. It is structured as follows:

| Index  | Type  |  Start day | End day |  Channels |  Target products |  Bound |
| :--: 	 |  :--: |  :--:      |   :--:  |  :--: 	|  :--: 	       |  :--: 	|
| ... 	 |  ...  |  ...       | ...     |  ...      | ...   		   | ...    |

<p align="justify">
The table specifies for the business constraints and the contact rules the index, the type, the start day, the end day, the channels, the target products, and the bound associated with the respective constraint or rule. The activities that are associated with a business constraint or contact rule are defined according to the information in this table.
</p>

---

#### Table 4

Table 4 provides information on the conflict rules. It is structured as follows:

| Index  |  Channel 1   | Target product 1 |  Channel 2 |   Target product 2 |  Lag |
| :--: 	 |  :--: 	    |  :--: 		   |     :--:   |  :--:		   	     |  :--:|
| ... 	 |  ...  		|  ...  		   | ...        |  ...    		     |  ... |

<p align="justify">
The table indicates the combinations of channels and target products that lead to a conflict and the time lag associated with a conflict rule.
</p>

## Attribution

<p align="justify">
Please cite the following paper to use these instances: Bigler, T., Kammermann, M., Baumann, P., 2020. A matheuristic for a large-scale customer assignment problem in direct marketing. Manuscript submitted for publication.
</p>
