# ![Icon](images/TypeLoader_32.png)  Colors, Icons and Status

Target alleles in TypeLoader have two kinds of status:

  * the **Allele Status** designates the overall status of the allele
  * the **Lab Status** designates the status of the allele within the wet lab workflow

Both have designated values, and each status value belongs to a category.

##  Status categories and colors 
Status values are grouped into categories, which signify whether there is currently anything that needs to be done with this allele.

Each category has an assigned color and icon:

| Category | Color      | Meaning | Icon|
|----------|------------|---------|-----|
| ToDo     | **yellow** | To proceed with this allele, the user must do something. | ![todo](images/icon_todo.png | width=16) |
| Pending  | **grey**   | This allele has been submitted to ENA or IPD and is awaiting their response. | ![todo](images/icon_pending.png | width=16) |
| Done     | **green**  | All work on this allele has been finished. | ![todo](images/icon_done.png | width=16) |
| Error    | **red**    | Something is wrong with this allele. | ![todo](images/icon_error.png | width=16)|
| Unknown  | **white**  | TypeLoader does not know this status! | ![todo](images/icon_error.png | width=16)|

##  Allele Status 
The allele status designates the overall status of the allele. TypeLoader knows the following status values for the allele status (in the order in which they are usually encountered):

| Value                     | Category | Meaning |
| --- | --- | --- |
| detected                  | ToDo ![todo](images/icon_todo.png | width=16) | A novel allele was detected within the routine workflow and TypeLoader was notified of it;  lab work to characterize it has not yet begun. | 
| processing in lab         | ToDo ![todo](images/icon_todo.png | width=16) | Lab work to characterize the target allele is currently in progress. |
| lab process completed     | ToDo ![todo](images/icon_todo.png | width=16) | Lab work to characterize the target allele has been finished, the sequence can now be uploaded to TypeLoader. |
| ENA-ready                 | ToDo ![todo](images/icon_todo.png | width=16) | The sequence has been uploaded to TypeLoader and an ENA-file has been generated. This can now be submitted to ENA. |
| ENA submitted             | Pending ![pending](images/icon_pending.png | width=16) | The allele has been submitted to ENA and is awaiting their response with an accession number. |
| ENA-problem               | Error ![error](images/icon_error.png | width=16) | The allele was rejcted during ENA submission. Something in its ENA-file must be fixed. Then the allele can be resubmitted. |
| ENA accepted              | ToDo ![todo](images/icon_todo.png | width=16) | The allele has received an ENA accession number and can now be submitted to IPD. |
| IPD submitted             | Pending ![pending](images/icon_pending.png | width=16) | The allele has been submitted to IPD and is awaiting their response with an allele name and HWS number. |
| IPD-problem               | Error ![error](images/icon_error.png | width=16) | The allele was rejected by IPD. Something must be fixed. Then the allele can be resubmitted. |
| IPD accepted              | Done ![done](images/icon_done.png | width=16) | The allele was accepted by IPD and the response-data has been uploaded to TypeLoader. The workflow is now finished. |
| IPD released              | Done ![done](images/icon_done.png | width=16) | The allele has been released as part of an official IPD release. |
| abandoned                 | Done ![done](images/icon_done.png | width=16) | The user has decided not to pursue work on this allele any further. Reasons should be listed in the ``comment`` field. |
| original result corrected | Done ![done](images/icon_done.png | width=16) | The user has decided to correct a previous genotyping. This closes the workflow on this allele. |
Note that not all alleles will encounter every allele status during their workflow.

##  Lab Status 
The lab status designates the status of the allele within the wet lab workflow of characterizing this sequence. Changes in lab status usually occur alongside the allele status ``processing in lab``.

TypeLoader knows the following status values for the lab status (in the order in which they are usually encountered):


| Value               | Category | Meaning |
| not started         | ToDo ![todo](images/icon_todo.png | width=16) | Lab work to characterize this allele has not yet begun. |
| ongoing             | ToDo ![todo](images/icon_todo.png | width=16) | Lab work to characterize this allele is currently under way. |
| repeat              | ToDo ![todo](images/icon_todo.png | width=16) | Initial characterization did not work; restart lab work with another DNA sample from the same individual. |
| repeat original DNA | ToDo ![todo](images/icon_todo.png | width=16) | Initial characterization did not work; restart lab work with the same DNA. |
| on hold             | Pending ![pending](images/icon_pending.png | width=16) | Lab work on this target allele has been paused until further notice. |
| aborted             | Done ![done](images/icon_done.png | width=16) | The user has decided not to pursue work on this allele any further. Reasons should be listed in the ``comment`` field. |
| completed           | Done ![done](images/icon_done.png | width=16) | All laboratory work for this allele has been successfully completed. The generated sequence can be or has been uploaded to TypeLoader to submit it. |

![Pic](images/icon_important.png) **Note that all alleles that are created in TypeLoader by uploading a sequence file already start with the lab status "completed".**

**To use the other lab status values, the alleles have to be initialized at an earlier point, which is not yet supported.**