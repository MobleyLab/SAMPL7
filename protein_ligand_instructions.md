# SAMPL7 Detailed Protein-Ligand (PHIP2) Instructions

Details of the challenge itself, and what information you will submit at each stage, is available in [protein_ligand/README.md](protein_ligand/README.md). This document provides information on how submissions will be handled.

## Due date

Due dates vary by challenge; refer to the main [README.md](README.md) for exact dates.

Your predictions must be uploaded via our [web form](http://sampl-submission.us-west-1.elasticbeanstalk.com/submit) before midnight US Pacific time on the due date. The experimental results will be available as soon as possible after SAMPL closes. Please refer to the below instructions for information on uploading.

You must use the provided templates to upload your predictions. Templates are:
- [protein_ligand/stage1_submission_template.txt](protein_ligand/stage1_submission_template.txt) for the virtual screening component
- [protein_ligand/stage2_submission_template.txt](protein_ligand/stage2_submission_template.txt) for the pose prediction component; must be uploaded along with pose predictions in a tar.gz file; see [instructions](protein_ligand/README.md) for full details.
- [protein_ligand/stage3_submission_template.txt](protein_ligand/stage3_submission_template.txt) for the compound selection component.

File names must begin with the letters "PHIP2" and the additional details provided in the submission template.

## Multiple submissions

As per our [policy on multiple submissions](https://samplchallenges.github.io/roadmap/submissions/), each participant or organization is allowed only one ranked submission, which must be clearly indicated as such by filling the appropriate field in the submission form. We also accept non-ranked submissions, which we will not formally judge. These allow us to certify that your calculations were done without knowing the answers, but do not receive formal ranking, as discussed at the link above. Please refer to the above policy for additional explanation of this distinction.

If multiple submissions are incorrectly provided as "ranked" by a single participant, we will judge only one of them; likely this will be the first submitted, but it may be a random submission.

## Anonymous participation

Anonymous participation is not allowed.

## Computational methods

You may use any method(s) you like to generate your predictions; e.g. docking, shape-based methods, machine learning models, etc. We only ask that you clearly explain your method in your submission file. Null model submissions are also acceptable.

## Method descriptions

Your method descriptions should give a detailed description of your approach, ideally with enough detail that someone could reproduce the work. These often serve to allow researchers to coordinate on why calculations which seem similar performed quite different in practice, so you should be sure to address how you generated poses, selected protonation states and tautomers if applicable, etc., as well as any method-specific details that, if varied, might result in different performance. Software versions should be provided. You will also need to assign a category to your method, as discussed below.

## Method category

In the Method Category section of your submission file please state which of the method category labels describe your prediction the best: `Docking`, `Ligand-based`, `MD`, `ML`, `Other`, `Null`.
If your method takes advantage of multiple approaches please report more than one category label, separated by comma.  
- `Docking` refers to structure-based virtual screening methods that model the structure of the receptor binding pocket and pose of the ligand followed by a scoring the goodness of the fit.
- `Ligand-based` methods are virtual screening methods that do not rely on protein structure such as pharmacophore modeling, ligand shape-based, 2D or 3D structural similarity based methods.
- `MD` methods utilize molecular dynamics simulations based on molecular mechanics including free energy calculations. Select this also if you used a docking or ligand-based approach combined with MD.
- `ML` category includes machine learning, QSPR approaches, and other predictive methods trained on empirical knowledge (however, docking approaches using empirical scoring functions belong in the `docking` category)
- `Null` predictions employ a model which is not expected to produce useful predictions (e.g., molecular weight). However, these can provide a simple comparison point for more sophisticated methods, as ideally, good methods should outperform the null model.
- `Other`: If these categories do not match your method, report as “Other”. If you choose the “Other” category, please explain your decision in the beginning of Method Description section.  


## Uploading your predictions

We are now accepting submissions via upload at [http://sampl-submission.us-west-1.elasticbeanstalk.com/submit](http://sampl-submission.us-west-1.elasticbeanstalk.com/submit); note that your filename must begin with `PHIP2` and follow the submission format described above.

If you want to upload more than one set of predictions, generated by different methods, each set must be uploaded as a separate file. Please use the template provided, as the predictions will be parsed and analyzed with automated scripts, and if you violate the file format, you will receive an error message and your submission will not be accepted. A complete set of predictions constitutes predicted binding (true/false) for all those compounds you predict to bind; you may also predict binding by site (S1 through S4) as well as total binding. Compounds which are omitted from your file will be assumed to be predicted to be nonbinders and no error message will be raised (though you are welcome to include these compounds with binding status listed as "False").

Names of the uploaded prediction files must begin with the name of the challenge component for which it contains predictions, as in the provided templates (i.e., PHIP2).

The file will be machine parsed, so correct formatting is essential.

Lines beginning with a hash-tag (#) may be included as comments. These and blank lines will be ignored.

The file must contain the following five components in the following order: your predictions, a name for your computational protocol, a list of the major software packages used, a long-form methods description, and, finally, whether your submission is to be ranked or not. Each of these components must begin with a line containing only the corresponding keyword: Predictions:, Name:, Software:, Method:, and Ranked:, as illustrated in the example files. The last field should have a boolean value (True or False). See above information on "multiple submissions" for discussion of the role this plays. If you would like to provide a full authors list/list of participants, please include this as part of the Method section.

Please note that the submission page is relatively minimal and is hosted at AWS at an ".elasticbeanstalk.com" address; do not be alarmed to find that in the URL.
