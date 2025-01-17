# Mutant_Fault_Coupling

This repo contains the adapted version of defects4j and the data from the research paper: INSERT PAPER <br/>
defects4j_PIT was extended from René Just's defects4j project found here: https://github.com/rjust/defects4j

## Contents of Repo

- MAJOR_suites_test_methods
- csv_data
- defects4j_PIT
- fixed_suites
- important_log_files
- merged_valid_maps
- triggering_tests

## MAJOR Suites Test Methods

Contains "test_methods.txt" files with all the test methods for a given test suite. This file was used with the MAJOR mutation tool to create the kill maps at a test method level (Opposed to a test class level).<br/>
<br/>
**Example:** MAJOR_suites_test_methods/auto_gen_suites_all_test_methods/Collections/evosuite/2/28f/test_methods.txt: <br/>
<br/>
org.apache.commons.collections4.trie.AbstractPatriciaTrie_ESTest <br/>
test00() <br/>
test01() <br/>
test02() <br/>

This file contains the test methods for the test suite generated by the second run of evosuite for the Commons-Collections project's fault 28. It shows that there is 1 test class (org.apache.commons.collections4.trie.AbstractPatriciaTrie_ESTest) containing 3 test methods (test00, test01, test02).

## CSV Results

The raw csv files from the mutation analysis experiments.

## defects4j_PIT

This is the extended version of defects4j framework that was used. The PIT Mutation tool (https://pitest.org/) was intergrated into the defects4j framewok. Several other existing scripts were extended to allow MAJOR to operate at a test method level. See https://github.com/SteGaff7/Mutant_Fault_Coupling/blob/master/defects4j_PIT/README.md for further details.

## Fixed Suites

The fixed test suites used in the mutation analysis. Raw test suites were generated using defects4j gen_tests.pl with the Evosuite and Randoop test generation tools, 5 were generated for each tool. These suites were then fixed using defects4j fix_test_suite.pl script. Each folder corresponds to one of the 5 runs of each tool on a project, and contains the test suites for all faults in the projects as independent archives containing the test code.

## Log Files

Important and interesting log files. The list of bugs used for this research can be found here (valid_bugs), the suites used for each bug can also be found.

## Merged Valid Maps

The merged kill maps for a given mutation tool (PIT or MAJOR) for a given bug can be found here. E.g all merged PIT kill maps for fault Time-12. Stored in tar.xz archive as the extracted directories are quite large (MAJOR - 4.9GB and PIT - 29GB)

## Triggering Tests

Contains all the triggering tests from all test suites for a given bug in one file. Has 2 further subdirectories, triggering tests for generated test suites and triggering tests for developer test suites. <br/>
<br/>
**Example:** triggering_tests/auto_gen_triggering_tests/JacksonCore/10f/JacksonCore-10f-triggering_tests: <br/>
<br/>
10f-evosuite-5-com.fasterxml.jackson.core.sym.ByteQuadsCanonicalizer_ESTest.test44<br/>
10f-evosuite-5-com.fasterxml.jackson.core.sym.ByteQuadsCanonicalizer_ESTest.test10<br/>
10f-evosuite-5-com.fasterxml.jackson.core.sym.ByteQuadsCanonicalizer_ESTest.test59<br/>
