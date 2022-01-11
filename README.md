# Solution
We know:
<ul>
  <li>The type of crime was murder.</li> 
  <li>The date of the crime was January 15, 2018. </li>
  <li>The crime was committed in SQL City.</li>
</ul>
We can write an SQL query that selects all and only reports on crimes which satisfy these three criteria.
<img src='' />
Let's begin by investigating the second witness. We can simply select those persons with the first name "Annabel" and the address street name "Franklin Ave."
<img src='' />
Only one row is displayed, so Annabel Miller must be our second witness. Now that we know Annabel's ID is 16371, we can use that to obtain her interview transcript.
<img src='' />
Investigating the first witness is a bit trickier. We have to not only select those persons who live on Northwestern Dr, but also arrange their address numbers in descending order. That way we can tell right away which person lives in the last house on that street.
<img src='' />
