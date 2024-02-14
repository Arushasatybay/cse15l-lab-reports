# Lab Report 3
## Part 1

### Failure Inducing Input:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
@Test
  public void testReversed2() {
    int[] input1 = { 3, 5, 7};
    assertArrayEquals(new int[]{7, 5, 3 }, ArrayExamples.reversed(input1));
  }
}
```

### An Input That Doesn't Induce a Failure:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
}
```
### The symptom:
![Screenshot](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-02-10%20at%206.06.43%20PM.png?raw=true)

### The bug:
```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
}
```

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
}
```
![PassedTests](https://github.com/Arushasatybay/cse15l-lab-reports/blob/main/Screenshot%202024-02-10%20at%206.15.20%20PM.png?raw=true)

* In the first code, we were assigning values of `newArray` to `arr`. However, every element of the `newArray` at that point is initialized to `0`, so `arr` is not being reversed but rather assigned to new elements, which are `0`. By assigning values of `arr` to `newArray`, and then returning the new reversed array, we are fixing the bug.


## Part 2 Researching Grep Command
1. a) **grep -i**:
   ```
   base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -i "kofi" ./technical/plos/*.txt
   ./technical/plos/journal.pbio.0020001.txt:        Kofi Annan, the Secretary-General of the United Nations, recently called attention to
   ```
   * This command searches for a specific pattern, in this case: "kofi", case-insensitively. It is useful for fast word and pattern finding.

   b) **grep -i**:
   ```
   (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -i "older" ./technical/biomed/1468-6708-3-1.txt
        Older adults are frequently counseled to lose weight,
        non-smoking older adults have investigated the association
        in certain small subsets. A review of 13 studies of older
        Many healthy older adults report gradual weight gain
        number of studies of older persons is fairly small, and
        In older adults, risk factors may have a greater effect
        years of being healthy, in a cohort of older adults for
        modification interventions in older adults.
          65 and older at baseline [ 11 ] . Subjects were recruited
          older men and 30-35 for older women. In Figure 1, the
          categories could be combined for older adults. Since
          older women could be efficient if YHL (but not YOL) was
          interventions for older adults who were merely overweight
          evaluations should be considered critically when older
          33 34 ] . For older adults, the risks associated with
          outcome for a trial of weight loss in older adults
          found for underweight older adults. Clinical trials whose
          average older adult; however, adjustment for detailed
        older adults, especially for women. Future efforts to
        no excess risk for older adults who would be classified as
        obese or underweight older adults, and discouraging trials
        that address older adults who are merely overweight.
   ```
   * This command, when applied to a file, scans for a pattern, in this case, the word "older," and outputs only the lines that contain the target word regardless of the case. This case-insensitive search is highly efficient for word searches. `grep -i`  searches not only for words but patterns which enables a more complex search.

2. a) **grep -n**:
```
(base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -n "objective" ./technical/government/Env_Prot_Agen/*.txt
./technical/government/Env_Prot_Agen/1-3_meth_901.txt:9:The objective of aquatic toxicity tests with effluents or
./technical/government/Env_Prot_Agen/1-3_meth_901.txt:253:permit requirements, the objectives of the test, the available
./technical/government/Env_Prot_Agen/atx1-6.txt:109:permit requirements, the objectives of the test, the available
./technical/government/Env_Prot_Agen/atx1-6.txt:518:objectives; (3) preparation of written descriptions of laboratory
./technical/government/Env_Prot_Agen/atx1-6.txt:599:on the objectives of the study and logistical constraints, as
./technical/government/Env_Prot_Agen/atx1-6.txt:757:objectives of the tests (see test condition summaries). The
./technical/government/Env_Prot_Agen/atx1-6.txt:819:objectives of the test and the statistical method used for analysis
./technical/government/Env_Prot_Agen/atx1-6.txt:1232:objective of the test.
./technical/government/Env_Prot_Agen/atx1-6.txt:1740:of the regulatory authority and the objectives of the test. It is
./technical/government/Env_Prot_Agen/ctf1-6.txt:167:The objective of aquatic toxicity tests with effluents or
./technical/government/Env_Prot_Agen/ctf1-6.txt:377:permit requirements, the objectives of the test, the available
./technical/government/Env_Prot_Agen/ctf1-6.txt:727:objectives (DQOs); (3) prepare a written description of laboratory
./technical/government/Env_Prot_Agen/ctf1-6.txt:813:on the objectives of the study and logistical constraints, as
./technical/government/Env_Prot_Agen/ctf1-6.txt:815:performed to meet NPDES objectives, synthetic, moderately hard
./technical/government/Env_Prot_Agen/ctf1-6.txt:993:objectives of the tests (see test condition summaries). The
./technical/government/Env_Prot_Agen/ctf1-6.txt:1053:of replicates varies with the objectives of the test and the
./technical/government/Env_Prot_Agen/ctf1-6.txt:1365:objective of the test.
./technical/government/Env_Prot_Agen/ctf1-6.txt:1771:requirements of the regulatory authority and the objectives of the
./technical/government/Env_Prot_Agen/ctf7-10.txt:8:tests will depend largely on the objectives of the study.
./technical/government/Env_Prot_Agen/ctf7-10.txt:12:If the objective of the test is to estimate the absolute
./technical/government/Env_Prot_Agen/ctf7-10.txt:21:If the objective of the test is to estimate the chronic
./technical/government/Env_Prot_Agen/ctf7-10.txt:39:If the objective of the test is to determine the additive
./technical/government/Env_Prot_Agen/ctf7-10.txt:49:for the objectives of the test; supports adequate performance of
./technical/government/Env_Prot_Agen/ctf7-10.txt:238:If the objectives of the test require the use of
./technical/government/Env_Prot_Agen/ctf7-10.txt:339:samples is based on the objectives of the test and an understanding
./technical/government/Env_Prot_Agen/ctf7-10.txt:482:The sampling point is determined by the objectives of the
./technical/government/Env_Prot_Agen/ctf7-10.txt:845:independently for each test based on the objective of the study,
./technical/government/Env_Prot_Agen/ctf7-10.txt:892:In cases where the objective of the test is to estimate
./technical/government/Env_Prot_Agen/ctf7-10.txt:903:9.1.1 The objective of chronic aquatic toxicity tests with
./technical/government/Env_Prot_Agen/ctf7-10.txt:985:9.2.1 If the objective of chronic aquatic toxicity tests with
./technical/government/Env_Prot_Agen/ctf7-10.txt:1280:replicates, and should be based on the objectives for obtaining the
./technical/government/Env_Prot_Agen/ctf7-10.txt:2068:depending on the degree of the departure and the objective of the
./technical/government/Env_Prot_Agen/ctf7-10.txt:2189:toxicant test, and the objective of the test. More frequent and/or
./technical/government/Env_Prot_Agen/ctf7-10.txt:2222:quality objectives and quality assurance plan.
./technical/government/Env_Prot_Agen/ctm4-10.txt:17:objectives (DQOs), (3) prepare written descriptions of laboratory
./technical/government/Env_Prot_Agen/ctm4-10.txt:104:objectives of the study and logistical constraints, as discussed in
./technical/government/Env_Prot_Agen/ctm4-10.txt:304:objectives of the tests (see test conditions and test acceptability
./technical/government/Env_Prot_Agen/ctm4-10.txt:365:of replicates varies with the objectives of the test and the
./technical/government/Env_Prot_Agen/ctm4-10.txt:679:reference toxicant test, and the objective of the test.
./technical/government/Env_Prot_Agen/ctm4-10.txt:1003:requirements of the regulatory authority and the objectives of the
./technical/government/Env_Prot_Agen/ctm4-10.txt:1376:will depend largely on the objectives of the study.
./technical/government/Env_Prot_Agen/ctm4-10.txt:1380:If the objective of the test is to estimate the absolute
./technical/government/Env_Prot_Agen/ctm4-10.txt:1389:If the objective of the test is to estimate the chronic
./technical/government/Env_Prot_Agen/ctm4-10.txt:1405:If the objective of the test is to determine the additive
./technical/government/Env_Prot_Agen/ctm4-10.txt:1415:for the objectives of the test; supports adequate performance of
./technical/government/Env_Prot_Agen/ctm4-10.txt:1572:If the objectives of the test require the use of
./technical/government/Env_Prot_Agen/ctm4-10.txt:1758:samples is based on the objectives of the test and an understanding
./technical/government/Env_Prot_Agen/ctm4-10.txt:1899:The sampling point is determined by the objectives of the
./technical/government/Env_Prot_Agen/ctm4-10.txt:2081:objectives of the study using hypersaline brine or artificial sea
./technical/government/Env_Prot_Agen/ctm4-10.txt:2264:independently for each test based on the objective of the study,
./technical/government/Env_Prot_Agen/ctm4-10.txt:2312:In cases where the objective of the test is to estimate
./technical/government/Env_Prot_Agen/ctm4-10.txt:2323:9.1.1 The objective of chronic aquatic toxicity tests with
./technical/government/Env_Prot_Agen/ctm4-10.txt:2407:9.2.1 If the objective of chronic aquatic toxicity tests with
./technical/government/Env_Prot_Agen/ctm4-10.txt:2694:replicates, and should be based on the objectives for obtaining the
./technical/government/Env_Prot_Agen/ctm4-10.txt:3501:depending on the degree of the departure and the objective of the
./technical/government/Env_Prot_Agen/ctm4-10.txt:3622:toxicant test, and the objective of the test. More frequent and/or
./technical/government/Env_Prot_Agen/ctm4-10.txt:3654:requirements of any applicable data quality objectives and quality
./technical/government/Env_Prot_Agen/final.txt:85:The objective was for sources to find the most cost-effective means
./technical/government/Env_Prot_Agen/multi102902.txt:2653:demand for work at power plants, the union has made it an objective
./technical/government/Env_Prot_Agen/nov1.txt:363:structured to ensure consistency with the NEP objectives. The NEP
./technical/government/Env_Prot_Agen/ro_clear_skies_book.txt:17:priorities. This progressive plan shows how that objective can be
```
* In this command "each output line is preceded by its relative line number in the file, starting at line 1.  The line number counter is reset for each file processed"(`man` command information). It might be very useful for finding typos and errors and fixing them because it provides the line number too.

   b) **grep -n**:
  ```
  (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -n "man" ./technical/911report/chapter-2.txt 
   7:                physician, Ayman al Zawahiri, arranged from their Afghan headquarters for an Arabic
   67:                his message are largely unknown to many Americans. Seizing on symbols of Islam's
   83:                from Abraham through Jesus, complete God's message to humanity. The Hadith, which
   95:                institution that continued until 1924, first under Arab and eventually under Ottoman
   103:            Islam is both a faith and a code of conduct for all aspects of life. For many
   147:                Prophet Mohammed). Qutb argued that humans can choose only between Islam and
   175:                of mankind." If the United States did not comply, it would be at war with the
   212:                local Islamist movements by ceding control of many social and educational issues.
   217:                many into exile. In Pakistan, a military regime sought to justify its seizure of
   235:                1980s, diminishing oil revenues, the economic drain from many unprofitable
   251:                the West. Furthermore, the repression and isolation of women in many Muslim
   265:                humanities and social sciences. Many of these young men, even if able to study
   274:                they disagree. Beyond the theology lies the simple human fact that most Muslims,
   275:                like most other human beings, are repelled by mass murder and barbarism whatever
   312:                appeared to be ungainly but was in fact quite athletic, skilled as a horseman,
   330:            Mosques, schools, and boardinghouses served as recruiting stations in many parts of
   375:                Group, was the so-called Blind Sheikh, Omar Abdel Rahman. His preaching had inspired
   377:                1980s, Abdel Rahman found refuge in the United States. From his headquarters in
   380:            The most important Egyptian in Bin Ladin's circle was a surgeon, Ayman al Zawahiri,
   383:                many to think of him as the deputy head of al Qaeda. He would in fact become Bin
   404:                member of the royal family, he managed to get out of the country under the pretext
   439:                Lebanon, Iraq, Oman, Algeria, Libya, Tunisia, Morocco, Somalia, and Eritrea. Al
   450:                    commanders.
   484:                border region. Still, he was just one among many diverse terrorist barons. Some of
   506:                fatwa demanding their eviction. In December, bombs exploded at two hotels in Aden
   621:                government advised him that it intended to yield to Libya's demands to stop giving
   633:                financial manager, whom his followers saw as miserly.
   642:                informant for the United States. Also testifying about al Qaeda in a U.S. court was
   725:                maintained collaborative relationships with al Qaeda, but many disengaged
   809:            Al Qaeda continued meanwhile to collaborate closely with the many Middle Eastern
   819:                fund-raising network, Bin Ladin had again become the rich man of the jihad movement.
   820:                He had maintained or restored many of his links with terrorists elsewhere in the
   851:                committee chief, continued to be the operational commander of the cell; but because
   853:                Fawwaz, to serve as the on-site manager. The technical surveillance and
   855:                state-of-the-art video cameras obtained from China and from dealers in Germany. The
   879:                searched the Kenya residence of Wadi al Hage, who had become the new on-site manager
   884:                manager was taken over by Harun Fazul, a Kenyan citizen who had been in Bin Ladin's
  ```
  * This command searches for a specific pattern and outputs lines with that pattern as well as states the line number. The command is very useful for locating the pattern 
  occurrences and I assume might be very helpful for debugging, given it outputs the line number.

3.  a) **grep -r**:
   ```
   (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -r "United Nations" ./technical/
   ./technical//government/Gen_Account_Office/Testimony_d01609t.txt:community has not provided the resources that the United Nations
   ./technical//government/Gen_Account_Office/d03273g.txt:United Nations about $1.3 billion for the regular and peacekeeping
   ./technical//government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:The United Nations has estimated that 27.5 percent of the
   ./technical//government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:Report, The United Nations, Department of International Economic
   ./technical//plos/pmed.0020067.txt:        Deworming satisfies a number of United Nations Millennium Development Goals including
   ./technical//plos/pmed.0020016.txt:        In June 2001, heads of state and government convened a United Nations Special Session on
   ./technical//plos/pmed.0020016.txt:        The World Health Organization and its partners in the Joint United Nations Programme on
   ./technical//plos/pmed.0020016.txt:          Joint United Nations Programme on HIV/AIDS and the World Health Organization based on the
   ./technical//plos/pmed.0010047.txt:        similar to the one used by the World Health Organization/United Nations Children's Fund
   ./technical//plos/journal.pbio.0020310.txt:        Hough, principal technical advisor on biodiversity for the United Nations Development
   ./technical//plos/journal.pbio.0020105.txt:        (OECD) and the United Nations' World Summit on the Information Society (WSIS), advocates
   ./technical//plos/pmed.0020050.txt:        The World Health Organization and the Joint United Nations Programme on HIV/AIDS have
   ./technical//plos/pmed.0020247.txt:        untiring advocate for justice for people with HIV/AIDS, addressed the United Nations
   ./technical//plos/journal.pbio.0020001.txt:        Kofi Annan, the Secretary-General of the United Nations, recently called attention to
   ./technical//plos/journal.pbio.0020001.txt:        challenges of building bridges across these gaps that should bring the United Nations and
   ./technical//plos/journal.pbio.0020001.txt:        Goldemberg 1998; Riddoch 2000). For example, recent United Nations Educational, Scientific,
   ./technical//plos/journal.pbio.0020161.txt:        Mayor, former director general of the United Nations Educational, Scientific, and Cultural
   ./technical//911report/chapter-13.5.txt:                For the report, see United Nations Development Programme report, Arab Human
   ./technical//911report/chapter-13.5.txt:                Development Report 2003: Building a Knowledge Society (United Nations, 2003) (online
   ./technical//911report/chapter-13.5.txt:            30. For terrorists being self-funding, see United Nations report, "Second Report of
   ./technical//911report/chapter-13.3.txt:            16. See Arab Human Development Report 2003 (United Nations, 2003), a report prepared
   ./technical//911report/chapter-3.txt:                U.S. ambassador to the United Nations, Bill Richardson, led a delegation to South
   ./technical//911report/chapter-3.txt:                with Albright when she was ambassador to the United Nations and had served on the
   ./technical//911report/chapter-3.txt:                support from Bin Ladin), the United States persuaded the United Nations to adopt
   ./technical//911report/chapter-6.txt:                    the United Nations and foreign governments to raise global security standards
   ./technical//911report/chapter-12.txt:                    United Nations to these enterprises are weak. NATO member states are not
   ./technical//911report/chapter-12.txt:                The United Nations has rightly equated "literacy as freedom."
   ./technical//911report/chapter-12.txt:                money, in the United States and through resolutions of the United Nations. These
   ./technical//911report/chapter-12.txt:                United States and the United Nations were often forced to unfreeze assets.
   ```

 * This command "recursively search subdirectories listed"(`man` command information). It is useful because it searches for a specific pattern within all files in the 
     provided directory.
    b) **grep -R**:
  
     ```
    (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -R "Boston" ./technical/911report/*.txt
    ./technical/911report/chapter-1.txt:    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.
    ./technical/911report/chapter-1.txt:    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.
    ./technical/911report/chapter-1.txt:    Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.
    ./technical/911report/chapter-1.txt:    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.
    ./technical/911report/chapter-1.txt:    Washington Dulles: American 77. Hundreds of miles southwest of Boston, at Dulles International Airport in the Virginia suburbs of Washington, D.C., five more men were preparing to take their early morning flight. At 7:15, a pair of them, Khalid al Mihdhar and Majed Moqed, checked in at the American Airlines ticket counter for Flight 77, bound for Los Angeles. Within the next 20 minutes, they would be followed by Hani Hanjour and two brothers, Nawaf al Hazmi and Salem al Hazmi.
    ./technical/911report/chapter-1.txt:    The four men passed through the security checkpoint, owned by United Airlines and operated under contract by Argenbright Security. Like the checkpoints in Boston, it lacked closed-circuit television surveillance so there is no documentary evidence to indicate when the hijackers passed through the checkpoint, what alarms may have been triggered, or what security procedures were administered. The FAA interviewed the screeners later; none recalled anything unusual or suspicious.
    ... note 69 lines omitted ...
    ```
* This command is the same as `grep -r` but because we specified `-R`, it will also show all symbolic links. However, in the above-provided text files, we can see no symbolic links were detected. "Symbolic links are commonly used to create shortcuts or aliases to files or directories, allowing for convenient access or organization within a file system"(`ChatGPT` Prompt: what are symbolic links used for)

4. a) **grep -w**:
  
     ```
     (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -w "an" ./technical/government/Alcohol_Problems/Session3-PDF.txt 
     Excessive alcohol consumption plays an important role in many of
     occasioned a call for an effective method of intervening with
     The presence of an adverse consequence that can be linked to
     medical problem; an automobile crash; unintentional injury; or
     setting. In an emergency department (ED) study of injured crash
     drinkers after their visit to an emergency setting. Several studies
     emergency department seem to dissipate without an alcohol-specific
     Re-injury and readmission to an emergency or other medical
     intervention in an emergency department by alcohol health workers
     a follow-up study, were randomized into an intervention or control
     the intervention group demonstrated an average reduction in
     older adolescents ages 18 to 19 years treated in an emergency room
     following an alcohol-related event randomly assigned 94 of the 184
     physician-delivered interventions in an emergency setting exist.
     appropriate to promote consideration of change and an
     the emergency department or has an extended stay in a trauma
     necessity, an assessment of drinking behavior and a follow-up
     Although an opportunity exists to intervene with patients who
     that testing was an "essential" characteristic for those centers.40
     score of 5.27. In an earlier report, Chang and Astrachan documented
     step to developing an effective and efficient intervention program
     change model appears to be an appealing one to help staff and
     intervention becomes an integral part of the emergency triage
     and treatment system, it will be an appendage that will be
     Zuska, a surgeon with an interest in alcohol problems among injured
     surgeon is an opportunity for intervention in a progressive, often
     emergency department: an epidemiologic study. Acad Emerg Med
     role of alcohol and other drugs-an EAST position paper prepared by
     in the event: an
     Intervention by an
     alcohol health worker in an accident and emergency
     29. Bernstein E, Bernstein J, Levenson S. Project ASSERT: an
     drugs: an assessment of testing and clinical practices in U.S.
     patients presenting to an ED with those presenting to primary care
     dependence, or history of treatment for an alcohol problem.2
     systems problems in an environment that at best can be described as
     SBI is successful in an ED? Available resources are essential, as
     be an important outcome. Rates of enrollment in treatment programs
     5. Bernstein E, Bernstein J, Levenson S. Project ASSERT: an ED
     with patients who enter the ED with an injury.3-10 Several
     compelling reasons make the ED an important setting for alcohol
     for patients seen in the ED, there can be an immediacy between the
     identification of and intervention for an alcohol problem.
     effective, an ED-based brief alcohol intervention model that
     in informing future research. First, the ED potentially provides an
     computerized, tailored messaging represents an important technique
     11. Buerhaus PI, Staiger DO, Auerbach DI. Implications of an
     Intervention by an
     alcohol health worker in an accident and emergency
     non-research settings will make an intervention their own. In any
     is extremely important. He cited a brief report and an upcoming
     change. She added that an in-home, brief intervention linked with
     an easy assumption that a brief intervention is more appropriate
     may constitute an
     blood alcohol level patients could remember an intervention. If
     Research and Quality has an R-03 program with a $100,000 cap,
     interventionist could be an influential factor, she was unsure
     both a unique opportunity for an intervention in the emergency
     like an appropriate venue for alcohol interventions because many ED
     toward getting help because of a connection made by an ED
     DiClemente pointed out that in an ideal world, primary care
     influence spontaneous remission such as an injury, type and
     patients do not present with an injury. He wondered how much of
     ```

     
* In this command "the expression is searched for as a word"(man command information). therefore, when we are asking to find `an` it is actually trying to find all the instances of the word `an` in the text. So in this example, the word `and` would not be a match although it contains those letters. It is useful for a more specified search.

  b) **grep -w**:
  ```
  (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ grep -wi "preventive" ./technical/government/Alcohol_Problems/Session4-PDF.txt 
  Implementing Preventive Interventions in
  ED-based intervention to increase acess to primary care, preventive
  Comments on Implementing Preventive Interventions in Emergency
  providing preventive services. The Society for Academic Emergency
  putting clinical preventive services into practice. He reasoned we
  (base) MacBook-Pro-46:docsearch-1 aruzhansatybay$ 
  ```
* We can add two commands we learned for a more precise search. So `grep -w` still is searching for a whole word but by adding `i` to it we make it search case-insensitively. This allows some flexibility in our search. 


# Work Cited
* `man` command
* `ChatGPT`


