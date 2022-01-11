# Solution
We know:
<ul>
  <li>The type of crime was murder.</li> 
  <li>The date of the crime was January 15, 2018. </li>
  <li>The crime was committed in SQL City.</li>
</ul>
We can write an SQL query that selects all and only reports on crimes which satisfy these three criteria.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/report.png?token=GHSAT0AAAAAABQNHLKVHNF7IPMGZWH2JKLMYO6CQ6Q' width='700px' height='auto' />
Let's begin by investigating the second witness. We can simply select those persons with the first name "Annabel" and the address street name "Franklin Ave."
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/annabel.png?token=GHSAT0AAAAAABQNHLKURG5D2L3W5LSF7LMWYO6CRUA' width='700px' height='auto' />
Only one row is displayed, so Annabel Miller must be our second witness. Now that we know Annabel's ID is 16371, we can use that to obtain her interview transcript.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/annabelTranscript.png?token=GHSAT0AAAAAABQNHLKVM2FUSKE5UVRBEE7WYO6CR7A' width='700px' height='auto' />
Annabel's statement tips us off to the fact that, likely, the suspect will be on the list of Get Fit Now members, and will have checked in at the gym on January 9, 2018. That's useful, but it may not narrow down the list of suspects that much, so let's see what the first witness has to say. 
<br><br>
Identifying the first witness is a bit trickier. We have to not only select those persons who live on Northwestern Dr, but also arrange their address numbers in descending order. That way we can tell right away which person lives in the last house on that street.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/secondWitness.png?token=GHSAT0AAAAAABQNHLKVBUVUGYUHH2DZ6N2QYO6CJ5Q' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/mortyTranscript.png?token=GHSAT0AAAAAABQNHLKVP7V5LM7WBNP26HA6YO6CKHA' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/goldGymMembers48Z.png?token=GHSAT0AAAAAABQNHLKVHGQN6VVRB7PL2CFMYO6CK3A' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/suspects.png?token=GHSAT0AAAAAABQNHLKVYGTHDZ26SBQVB7WGYO6CLYA' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/suspectDriversLicense.png?token=GHSAT0AAAAAABQNHLKUAVDXA2IWPQLZWJ5KYO6CMFQ' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/solution1.png?token=GHSAT0AAAAAABQNHLKUMABUUVTJJRJ5HGDGYO6CMUA' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/bowersTranscript.png?token=GHSAT0AAAAAABQNHLKVYKYPDF37PLDRUQRKYO6CNEQ' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/minimalQuery.png?token=GHSAT0AAAAAABQNHLKV364CQIG5UISPJ4PWYO6CNTA' width='700px' height='auto' />

<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/solution2.png?token=GHSAT0AAAAAABQNHLKUTAS3J6DQXJVX5SVCYO6COLA' width='700px' height='auto' />
