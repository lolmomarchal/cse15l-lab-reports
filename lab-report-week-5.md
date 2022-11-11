LAB REPORT 3
===========
*Lorenzo Olmo Marchal*

*CSE 15L B05*

*10/30/2022*


>Grep

The grep command is used for both searching, printing, and matching files with the given parameters you give it. It is useful when trying to find instances of certain patterns or keywords. 

***grep -c***
------

The grep -c command allows you to find the count of a certain pattern/string within your files. For example in the example above, it counted a total occurences of the word "risk" within this text file. This is useful when trying to find pssages with key words wihtout having to open them and read through them. 

**EX 1:**
```[cs15lfa22ke@ieng6-203]:biomed:491$ grep -c rRNA 1468-6708-3-1.txt
0
[cs15lfa22ke@ieng6-203]:biomed:492$ grep -c DNA 1468-6708-3-1.txt
0
[cs15lfa22ke@ieng6-203]:biomed:493$ grep -c A 1468-6708-3-1.txt
29
```
In this example, we are using grep -c to count the instances of different words in the text file 1468-6708-3-1.txt. As seen above, there are no instances of "rRNA: or "DNA" in this file but there are 29 instances of "A" within it. This makes it easier when trying to find how many times a keyword appears in a file. 

**EX 2:**

Following on this concept of counting words through grep -c, in the example below, we will be trying to find instances of the word risk within the entire /government directory. 
```
[cs15lfa22ke@ieng6-203]:government:484$ grep -c risk *
grep: About_LSC: Is a directory
About_LSC:0
grep: Alcohol_Problems: Is a directory
Alcohol_Problems:0
grep: Env_Prot_Agen: Is a directory
Env_Prot_Agen:0
grep: Gen_Account_Office: Is a directory
Gen_Account_Office:0
grep: Media: Is a directory
Media:0
grep: Post_Rate_Comm: Is a directory
Post_Rate_Comm:0
```
When we input the command **grep -c risk** it gives a very strange output, citing that the contents of the government directory are other directories. Instead, when trying to go through a directore we need to use the command -r with grep -c in order to go through all the contents of the directories in governemnt in a recursive manner. 

```
[cs15lfa22ke@ieng6-203]:About_LSC:488$ grep -r -c risk *
CONFIG_STANDARDS.txt:0
Comments_on_semiannual.txt:0
LegalServCorp_v_VelazquezDissent.txt:0
LegalServCorp_v_VelazquezOpinion.txt:0
LegalServCorp_v_VelazquezSyllabus.txt:0
ODonnell_et_al_v_LSCdecision.txt:0
ONTARIO_LEGAL_AID_SERIES.txt:1
Progress_report.txt:0
Protocol_Regarding_Access.txt:0
Special_report_to_congress.txt:0
State_Planning_Report.txt:1
State_Planning_Special_Report.txt:0
Strategic_report.txt:0
commission_report.txt:3
conference_highlights.txt:0
diversity_priorities.txt:0
reporting_system.txt:0

```
When we do this we are able to see  how many times the keyword "risk" appears in every directory as seen above. This is useful when navigating a directory such as government, that has many files in separate directories. If we wanted, we could even do this in the parent directory, technical, to see the prevelance of this word throught the different directories. 


**EX 3:**
```
[cs15lfa22ke@ieng6-203]:About_LSC:487$ grep -c risk *
CONFIG_STANDARDS.txt:0
Comments_on_semiannual.txt:0
LegalServCorp_v_VelazquezDissent.txt:0
LegalServCorp_v_VelazquezOpinion.txt:0
LegalServCorp_v_VelazquezSyllabus.txt:0
ODonnell_et_al_v_LSCdecision.txt:0
ONTARIO_LEGAL_AID_SERIES.txt:1
Progress_report.txt:0
Protocol_Regarding_Access.txt:0
Special_report_to_congress.txt:0
State_Planning_Report.txt:1
State_Planning_Special_Report.txt:0
Strategic_report.txt:0
commission_report.txt:3
conference_highlights.txt:0
diversity_priorities.txt:0
reporting_system.txt:0

```
In this last example, we move into the about_LSC directory of government and by using the grep -c [keyword] command here we see the different files within this directory and the instance count of the keyword in each. Combined with the last examples, this shows the usefulness of grep -c when trying to find instances of a certain keyword within a file, within directories in a directory, and in a directory with files. We can slowly decrease our search span until we find exactly what we are looking for. 





***grep -l***
----

![image](https://user-images.githubusercontent.com/114376800/199087332-62d36a55-abdc-4949-a0fd-a0d32b36a9a4.png)

The grep -l command lists all the files that have a certain keypattern/word within them. This is more helpful when trying to find certain instances of a word throughout large directories such as technical or biomed. 

***grep -A***
----

**EX 1**
```
[cs15lfa22ke@ieng6-203]:biomed:460$ grep -A1 DNA *
bcr631.txt:        BCIP = 5-bromo-4-chloroindol-3-yl phosphate; cDNA =
bcr631.txt:        complementary DNA; EGTA = (ethylene-bis
bcr631.txt-        [oxyethylenenitrilo])tetraacetic acid; CHTN = Cooperative

cc1547.txt:        in excess inactivate proteins, disrupt DNA, and oxidize
cc1547.txt-        lipids [ 22]. Preterm newborn infants may be particularly

cvm-2-6-278.txt:        DNA injected directly into the skeletal muscle in a later       
cvm-2-6-278.txt-        study, using the same hind limb ischemia model, also

cvm-2-6-278.txt:          bioactivity of VEGF-A, naked VEGF165 DNA was injected
cvm-2-6-278.txt-          into the myocardium of five patients who had failed

cvm-2-6-278.txt:          dose VEGF. In a different approach, VEGF cDNA was
cvm-2-6-278.txt-          delivered via liposomes by catheter to coronary arteries      
cvm-2-6-278.txt:          transfection with VEGF-A cDNA [ 31], then it may possibly     
cvm-2-6-278.txt-          affect angiogenesis elsewhere [ 32]. As plaque

cvm-2-6-278.txt:          cDNA. This has been delivered either to promote
cvm-2-6-278.txt-          therapeutic angiogenesis (12 patients) or to accelerate       

cvm-2-6-278.txt:        myocardium with VEGF165 cDNA led to a significant
cvm-2-6-278.txt-        mobilization of CEP cells [ 31]. Another recent publication     

gb-2000-1-1-research002.txt:          et al. [ 16] reported a human cDNA
gb-2000-1-1-research002.txt-          sequence (GenBank accession number U88880) that includes

gb-2000-1-1-research002.txt:          PCR-amplified human TLR4 cDNA sequence as a probe. All
gb-2000-1-1-research002.txt-          three BACs were fragmented by ultrasound, shotgun cloned

gb-2000-1-1-research002.txt:          Sequencing DNA from mouse, chimpanzee and baboon  
gb-2000-1-1-research002.txt-          samples
gb-2000-1-1-research002.txt:          Mouse DNA, obtained from animals of 35
gb-2000-1-1-research002.txt-          Mus musculus strains, was ordered
gb-2000-1-1-research002.txt:          from the Jackson Laboratories. Chimpanzee and baboon DNA
gb-2000-1-1-research002.txt-          were obtained from Kurt Benirschke (University of 
```
In the format grep -A(number of lines you want to print ofter keyword) (keyword) (files(s)), grep -A finds all instances of a keyword within a directory (if used with * for the file parameter) and prints out the instances as well as the specified amount of lines after them. This is helpful when trying to find certain words as well as the contexts they are used in within files and directories, especially large ones. 

In this first example, grep is returning every instance of the word DNA within biomed with one line of context(represented by A1). For the sake of space (the original output is ~3000 lines) the output was shortened, nonetheless, this command is very useful when trying to get certain instances of a word. 

Let's say we do another example in which we use the command **grep -A3 incident ** within the plos directory 
```
[cs15lfa22ke@ieng6-203]:plos:464$ grep -A3 incident *.txt
journal.pbio.0020101.txt:        coincidentally after World War II, was Konrad Lorenz (1966). Lorenz's thesis was greeted
journal.pbio.0020101.txt-        with accusations about attempts to whitewash human atrocities, all the more so given the
journal.pbio.0020101.txt-        Nobel Prize winner's native tongue, which was German. But Lorenz was hardly alone. In the
journal.pbio.0020101.txt-        USA, science journalist Robert Ardrey (1961) presented us as “killer apes” unlikely to ever

journal.pbio.0020101.txt:        the male bullies of his main study troop. As a result, the number of aggressive incidents
journal.pbio.0020101.txt-        dropped dramatically. This by itself was not so surprising. It became more interesting when
journal.pbio.0020101.txt-        it was discovered that the behavioral change was maintained for a decade. Baboon males
journal.pbio.0020101.txt-        migrate after puberty, hence fresh young males enter troops all the time, resulting in a

journal.pbio.0020112.txt:        incidentally, Scottish Master Butcher of the Year in 1996), but also in the inspectors who
journal.pbio.0020112.txt-        had visited his shop eight times in the previous two years. They had not, apparently,
journal.pbio.0020112.txt-        picked up that Barr and his staff employed the same knives for cutting up raw and cooked
journal.pbio.0020112.txt-        meat, nor that they used a ‘biodegradable’ cleaning fluid, not realising that this is not

journal.pbio.0020206.txt:        principle, genome duplications should be easily identified through the coincident emergence
journal.pbio.0020206.txt-        within a phylogeny of many gene families. Unfortunately, this signal is complicated by
journal.pbio.0020206.txt-        subsequent piecemeal loss and gain of gene family members. Consequently, there is heated
journal.pbio.0020206.txt-        debate over possible ancient genome duplication events in early vertebrate evolution and

journal.pbio.0030032.txt:        physical therapy, and accounting. In the 1990s, non-incidental master's in the sciences—in
journal.pbio.0030032.txt-        other words, intentionally terminal degrees, not consolation prizes for failing out of
journal.pbio.0030032.txt-        graduate school—crept into engineering and applied mathematics, too, as companies grew more
journal.pbio.0030032.txt-        reliant on computational analysis and hired accordingly. From 1981 to 2000, for example,

journal.pbio.0030094.txt:        and DNA replication have led to a model whereby cohesion is established coincident with the
journal.pbio.0030094.txt-        passage of the replication fork [25]. This requires an alternative replication factor C
journal.pbio.0030094.txt-        (RF-C) complex [26,27,28] and may require the origin recognition complex (ORC) [29].
journal.pbio.0030094.txt-        Cohesion is maintained during G2 by the cohesin complex, and is eventually dissolved in

journal.pbio.0030127.txt:        eating more fish and squid (which, not incidentally, also eat krill). Fraser believes this
journal.pbio.0030127.txt-        dietary flexibility, along with the increased availability of open water and a late
journal.pbio.0030127.txt-        breeding schedule (which protects their eggs and chicks from spring snow meltwater),
journal.pbio.0030127.txt-        largely explain their range extensions.

journal.pbio.0030136.txt:        the comic book image, but the relationship seems to be coincidental in view of the
journal.pbio.0030136.txt-        iconographic symbolism of his choices. The likelihood that he had heard of these scientific
journal.pbio.0030136.txt-        developments seems remote, particularly in view of the fact that Andy Warhol was following
journal.pbio.0030136.txt-        the same track of using cartoon material, reputedly in mutual ignorance of Lichtenstein's

pmed.0010021.txt:        incidental finding in the elderly because of mild thrombocytopenia or splenomegaly, or it
pmed.0010021.txt-        may present early in life with hepatosplenomegaly, thrombocytopenia, anemia, and bone
pmed.0010021.txt-        lesions.
pmed.0010021.txt-        Until 1990, treatment consisted only of palliative measures such as splenectomy and hip

pmed.0020180.txt:        fetal death was incidental and found on routine ultrasound. (One case presented with
pmed.0020180.txt-        decreased fetal movement.) There were no significant differences between the IUFD-affected
pmed.0020180.txt-        pregnancies and the unaffected pregnancies with regards to antenatal indicators of
pmed.0020180.txt-        intrauterine growth restriction and TTTS. In three of the five pregnancies (autopsy was

pmed.0020246.txt:          within the same institution having observed the same inciden 
s.
pmed.0020246.txt-          While this study focused on HIV/AIDS, it is possible that health-care professionals
pmed.0020246.txt-          also engage in inappropriate behavior toward or breach the confidentiality of people with
pmed.0020246.txt-          other conditions. The health-care system in Nigeria is underfunded and suffers from

```

As seen above, this returns all instances of incident, even within other words like "coincidentally"- much like control f in a document or google  webpage. We also specified that we wanted to find this in any files that had *.txt specifically. This can be remedied by also using the command -i in grep, which states that a specific string must be found. 

**EX3**

```
[cs15lfa22ke@ieng6-203]:plos:478$ grep -i -A0 incident pmed.0020246.txt 
          within the same institution having observed the same incidents.

```

In this example, we go further to specify the range of our search to one single file, pmed.0020246.txt, in which we also return A0 - only the line that the instance of the keyword is in. This is useful when paired witch other grep commands like -c (which counts the instances of a certain keyword per file) when we want to simply look at certain instances without much context/for a quick glance. 
















