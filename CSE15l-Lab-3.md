# Grep commands

## grep -n

This command prints out the line where the searched for string appears within the file. Where you would usuall

**Example 1**

    [cs15lfa22qi@ieng6-201]:technical:387$ grep -n "crazy" */*.txt
    911report/chapter-13.4.txt:1218:                "ambitious, but not crazy."
    911report/chapter-3.txt:2989:                "a wince." Schroen recalled Massoud's response as "You guys are crazy-you haven't
    biomed/1472-6882-1-10.txt:393:          become temporarily crazy. Based on experiences like
    plos/journal.pbio.0020101.txt:13:        look at you as if you are crazy. They see an idyllic, sentimental movie, with beautiful

Example 2

[cs15lfa22qi@ieng6-201]:technical:390$ grep -n "tubular" biomed/cc103.txt     
24:        prevention or treatment of acute tubular necrosis (ATN).
26:        by increasing renal blood flow and that tubular obstruction
263:          unifying principle is cytoprotection of the renal tubular
265:          for a short time. The injury to the renal tubular cells
268:          permeability, tubular obstruction and transepithelial
271:          agents decrease the metabolic demand of the renal tubular
275:          also reduce the incidence of tubular obstruction and the
413:          of inhibition of sodium-potassium ATPase at the tubular
438:          related to tubular transport activity (medullary oxygen
451:          delivery to the distal tubular cells produced by the
453:          proximal tubular reabsorption) might actually increase

Example 3

[cs15lfa22qi@ieng6-201]:technical:392$ grep -n "outlandish" */*.txt
[cs15lfa22qi@ieng6-201]:technical:393$ 

grep -i

Example 1

[cs15lfa22qi@ieng6-201]:technical:393$ grep -i "CrAzY" */*.txt
911report/chapter-13.4.txt:                "ambitious, but not crazy."
911report/chapter-3.txt:                "a wince." Schroen recalled Massoud's response as "You guys are crazy-you haven't
biomed/1472-6882-1-10.txt:          become temporarily crazy. Based on experiences like
plos/journal.pbio.0020101.txt:        look at you as if you are crazy. They see an idyllic, sentimental movie, with beautiful

Example 2:

[cs15lfa22qi@ieng6-201]:technical:395$ grep -i "ChOpStIcK" */*.txt
plos/journal.pbio.0020101.txt:        instance, it is easy to tell if people eat with knife and fork or with chopsticks, but to

Example 3:

[cs15lfa22qi@ieng6-201]:technical:396$ grep -i "TuRbULeNt" */*.txt
911report/chapter-12.txt:                    rule at the national level, although that turbulent process does continue to

grep -w

Example 1

[cs15lfa22qi@ieng6-201]:technical:399$ grep -w "trail" */*.txt
911report/chapter-11.txt:                was no conscious decision to stop the operation after the trail was temporarily lost
911report/chapter-13.1.txt:                leaving an audit trail in order to determine who accessed the information. But the
911report/chapter-13.4.txt:                Terrorist,"Oct. 25, 2001 (online at www.pbs.org/wgbh/pages/ frontline/shows/trail).
911report/chapter-2.txt:                teams and one or two persons assigned to remove the evidence trail had left East
911report/chapter-6.txt:            Though Nawaf 's trail was temporarily lost, the CIA soon identified"Khalid" as Khalid
911report/chapter-6.txt:                Kuala Lumpur, let alone that their trail had been lost in Bangkok.
911report/chapter-7.txt:            We do not pick up their trail until February 1, 2000, when they encountered Omar al
911report/chapter-8.txt:                and January 2000. The trail had been lost in January 2000 without a clear
911report/chapter-8.txt:            Almost one year after the original trail had been lost in Bangkok, the FBI and the
911report/chapter-8.txt:                an FBI agent who works an investigation from beginning to end. Thus, when the trail
911report/chapter-8.txt:                Chasing Quso's trail, "Dave" suggested showing some photographs to FBI agents in New
911report/chapter-8.txt:                though it was not an easy trail to find. Discovering it would have required quick
911report/chapter-8.txt:                described, the links to Binalshibh might not have been an easy trail to find and
biomed/1471-213X-3-3.txt:          sloughed off and left behind in the slime trail. Although
biomed/1471-2288-3-9.txt:          allow values to trail off to infinity or not and whether
biomed/1472-6882-1-10.txt:          trail left by the deer's interdigital glands and thus
biomed/gb-2002-3-12-research0081.txt:        curation by experts using a full trail of evidence to
plos/journal.pbio.0020121.txt:        A number of scientists are currently on the trail of suspected CWD disease reservoirs.

Example 2

[cs15lfa22qi@ieng6-201]:technical:402$ grep -w "stump" */*.txt
biomed/1471-2156-4-9.txt:          stump (not shown). The reduced wings also occasionally
biomed/1471-2202-2-8.txt:        region and distal stump. Wallerian degeneration normally
biomed/1471-2202-2-8.txt:        the distal stump must occur sufficiently within a critical
biomed/1471-2202-2-9.txt:        parallel orientation within the distal stump. These axons
biomed/1471-2202-2-9.txt:        tract (such as the distal stump of the injured spinal cord)
biomed/1472-6874-2-1.txt:        level of the internal cervical os. The cervical stump was
biomed/1472-6963-3-7.txt:            readmissions for debridement and major stump revisions,

Example 3

[cs15lfa22qi@ieng6-201]:technical:405$ grep -w "car" */*.txt
911report/chapter-13.2.txt:                Pentagon was struck, and he saw smoke as his car made its way back to the building.
911report/chapter-13.4.txt:            29. On the purchase of the car, see FBI report, "Hijackers Timeline," Nov. 14, 2003
911report/chapter-13.4.txt:                bought a car. FBI briefing materials, Penttbom, Dec. 10-11, 2003, p. 150. For their
911report/chapter-13.4.txt:                married but could not because he was injured in a car accident there. German BKA
911report/chapter-13.5.txt:                Hamlan and Nami traveled by car and by air to an address KSM had given them
911report/chapter-13.5.txt:                Nawaf had a minor car accident traveling eastbound on the George Washington Bridge,
911report/chapter-13.5.txt:                intercepted after the FBI found the Express Mail receipt for it in Hazmi's car at
911report/chapter-13.5.txt:                and open New Jersey bank accounts. Hazmi also had a car registered and had been
911report/chapter-13.5.txt:                could have unearthed the driver's licenses, the car registration, and the telephone
911report/chapter-13.5.txt:                listing. A search on the car registration would have unearthed a license check by
911report/chapter-2.txt:                November 24, 1989, when a remotely controlled car bomb killed Azzam and both of his
911report/chapter-2.txt:            In November 1995, a car bomb exploded outside a Saudi-U.S. joint facility in Riyadh
911report/chapter-2.txt:                embassy in Nairobi was an easy target because a car bomb could be parked close by,
911report/chapter-5.txt:                included conventional car bombing, political assassination, aircraft bombing,
911report/chapter-5.txt:                from mistaken identity: Khallad was driving the car of another conspirator in the
911report/chapter-6.txt:            On December 14, 1999, Ressam drove his rental car onto the ferry from Victoria,
911report/chapter-6.txt:                cursory examination of Ressam's car, the INS agents allowed Ressam to board the
911report/chapter-6.txt:                all the other cars to depart the ferry, assuming (incorrectly) that the last car off
911report/chapter-6.txt:            Inspectors examining Ressam's rental car found the explosives concealed in the spare
911report/chapter-7.txt:                lived. For example, when they purchased a used car (with cash), they bought it from
911report/chapter-7.txt:                June of 2000, he closed his bank account, transferred the car registration to Hazmi,
911report/chapter-7.txt:                affiliated with his school and bought a car.
911report/chapter-7.txt:                Connecticut, followed by Hazmi, who had Moqed and Ghamdi in his car. After a short
911report/chapter-7.txt:                a car and drove to Reus to pick up Binalshibh; the two then drove to the nearby town
911report/chapter-7.txt:                when he returned his rental car in Madrid and flew back to Fort Lauderdale. On July
biomed/1472-684X-1-5.txt:          (especially drowsiness), it is safe to drive a car.
biomed/1475-2875-1-14.txt:          car-repair, car-washing, although a formal sector also
biomed/1475-2875-1-14.txt:          an occupant owned a car or satellite dish. The medium
biomed/1475-2875-1-14.txt:        reported owning a car. The proportion of households
biomed/1475-2875-1-14.txt:        car ownership. The proportion of households within the
plos/journal.pbio.0020012.txt:        about life extension using analogies with a car warranty concept is wrong-headed.”
plos/journal.pbio.0020101.txt:        SNL is incomplete without at least one sketch in which someone's car
plos/journal.pbio.0020306.txt:        make lightweight constructions for the aerospace and car industry’.
plos/journal.pbio.0020310.txt:        For Ferraro, the logic of direct payment is simple. He draws an analogy with a car
plos/pmed.0020197.txt:        car ride. She was started on cyclobenzaprine, 10 mg b.i.d., and continued on valdecoxib.
plos/pmed.0020197.txt:        Finally, prolonged stasis, such as that which occurred during the 6-h car trip, may
