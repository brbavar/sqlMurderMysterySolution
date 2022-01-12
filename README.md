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
Let's begin by investigating the second witness. We can simply select those people with the first name "Annabel" and the address street name "Franklin Ave."
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/annabel.png?token=GHSAT0AAAAAABQNHLKURG5D2L3W5LSF7LMWYO6CRUA' width='700px' height='auto' />
Only one row is displayed, so Annabel Miller must be our second witness. Now that we know Annabel's ID is 16371, we can obtain her interview transcript.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/annabelTranscript.png?token=GHSAT0AAAAAABQNHLKVM2FUSKE5UVRBEE7WYO6CR7A' width='700px' height='auto' />
Annabel's statement tips us off to the fact that, likely, the suspect will be on the list of Get Fit Now members, and will have checked in at the gym on January 9, 2018. That's useful, but it may not narrow down the list of suspects that much, so let's see what the first witness has to say. 
<br><br>
Identifying the first witness is a bit trickier. We have to not only select those people who live on Northwestern Dr, but also arrange their address numbers in descending order. That way we can tell right away which person lives in the last house on that street.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/secondWitness.png?token=GHSAT0AAAAAABQNHLKVBUVUGYUHH2DZ6N2QYO6CJ5Q' width='700px' height='auto' />
Given that Morty Schapiro's ID is 14887, let's write:
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/mortyTranscript.png?token=GHSAT0AAAAAABQNHLKVP7V5LM7WBNP26HA6YO6CKHA' width='700px' height='auto' />
Now we're getting somewhere! Only the gold members of the gym remain suspects. We can narrow the suspects down further using the wildcard % to find the gold members whose membership numbers begin with 48Z (followed by anything).
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/goldGymMembers48Z.png?token=GHSAT0AAAAAABQNHLKVHGQN6VVRB7PL2CFMYO6CK3A' width='700px' height='auto' />
Let's get some more information on these two honored members of Get Fit Now Gym, using the names we just uncovered.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/suspects.png?token=GHSAT0AAAAAABQNHLKVYGTHDZ26SBQVB7WGYO6CLYA' width='700px' height='auto' />
Now, using the license IDs, we just need to see which of these two owns a car with a license plate number containing "H42W" (preceded or followed by anything).
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/suspectDriversLicense.png?token=GHSAT0AAAAAABQNHLKUAVDXA2IWPQLZWJ5KYO6CMFQ' width='700px' height='auto' />
There you have it. The suspect with a license ID of 423327, namely Jeremy Bowers, is the only one whose license plate number contains that substring. In fact, there is no license on file for Joe Germuska, the other suspect. So let's check our answer: Jeremy Bowers.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/solution1.png?token=GHSAT0AAAAAABQNHLKUMABUUVTJJRJ5HGDGYO6CMUA' width='700px' height='auto' />
Jeremy Bowers is indeed the culprit! But apparently he's not the only responsible party. Who else could be in on this? Per the stated challenge, let's find out in just two queries. 
<br><br>
This first query is not at all involved, so the next query will have to do the heavy lifting. Let's use Jeremy's ID to see what he said in his interview.
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/bowersTranscript.png?token=GHSAT0AAAAAABQNHLKVYKYPDF37PLDRUQRKYO6CNEQ' width='700px' height='auto' />
Gee, where do we go from here... Well, we would expect to find the data Jeremy mentions in the income, drivers_license, and facebook_event_checkin tables. And obviously what we want to learn is the name of the person, which we can then enter as our second solution. So we <em>could</em> join the person, income, drivers_license, and facebook_event_checkin tables, narrowing down the rows to the ones that meet Jeremy's specifications (e.g., hair color and car model), and then select the people's names from the resulting table. (I admit I took that approach at first.)
<br><br>
But there's really no <em>need</em> to use all the information Jeremy gave to identify the woman who hired him. I managed to narrow the suspects down to one using just two of the details Jeremy gave: the name of the event this woman attended and the make of her car. Aside from that, all I had to do was ensure that the final table contained only rows where
<ol type='a'>
  <li>the person's ID matched the ID of the event attendee, and</li>          
  <li>the license ID from the person table matched the ID from that person's row in the drivers_license table.</li>
</ol>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/minimalQuery.png?token=GHSAT0AAAAAABQNHLKV364CQIG5UISPJ4PWYO6CNTA' width='700px' height='auto' />
Wow, check this out. Not only did we narrow down to one the list of distinct suspect names, but instantly we notice her name occurs three times. This is because, as Jeremy said of the woman who hired him, Miranda attended the SQL Symphony Concert three times. Really, though, the sole fact that just one name remains guarantees this is our criminal. So let's submit our answer!
<br><br>
<img src='https://raw.githubusercontent.com/brbavar/sqlMurderMysterySolution/main/solution2.png?token=GHSAT0AAAAAABQNHLKUTAS3J6DQXJVX5SVCYO6COLA' width='700px' height='auto' />
