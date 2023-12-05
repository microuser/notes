# notes
## Books 
### OReilly Football Analytics with Python & R, Eager & Erickson
These are the personal notes, under MIT license of Paul Richeson, Dec 4th, 2023.
#### Chapter 1 Notes OReilly Football Analytics with Python & R, Eager & Erickson: 
 - MIT and Carnegie Mellon students got interested in football statistics, speicially the average Target Distance, and argressiveness compromises for exprexted point posibilities. NFL Scapper, NFL Faster, written in R. 
 - Baseball uses Walks, Strikeouts, Homeruns. Stability and repeatable is best.
 - RYOE - Rushing Yards Over Expected (RYOE)
 - Some players are stable, some players are risky.
 - What is a running back?
 - It is safer now that we use the forward pass. Throwing the football is faster than running.
 - NCAA Southeastern Conference Football. This includes texas.
 - A running back runs the football.
 - Using metrics like Yards Per Play or EPA
 - EPA football, expected points added, it is a scalar of points for the team. if it was 7 is it max?
 - The book could be said to argue that running backs do not have high market value.
 - Air Yards, Distance traveled from the line of scrimmage to the line of receiver. slightly less than the actual throw length.
 - Completion percentage over expected. quarterback metric
 - Bad draft picks from coahes can be a problem solved using calculations of draft capital. Picks, Pick rounds, Pick Numbers. 
 - Common Data Languages R, Julia, Python
 - Funny data languages Matlab, SaS, Jupiter.
 - Julia, is a math language, high level.
 - R, Python and Open source licenses get along with the football community it seems. check for libraries in python.
 - Insert coke or ford advertisement here.
 - If someone gives you data, and they generate a model with excel, it is best if they know their stuff. Use R or python if you care about posterity.
 ```py
2+2
=> 4
#comment for humans
```
 - ignore all install pip, python, conda, npm, nvm, instructions, invest your own with nix.
  ```nix.conf
python3
julia
conda
#unfinished
```
 - i like fluent code.
 - Key by name and number
 - value by number of plays and (adot) mean air yards per pass.
 - filter to include > 100 plays, and skip incomplete rows
 - never double negative. Only postive perspective.
 - its obvious that a quarterback who throws to a receiver who then can run is better than just a quarterback who throws to a receiver who sticks still.
 - the book declares that I have whet my appetite for using math to examine football data. indeed.
 - the R system of pipes is like linux, but with better symbols.
 - nflfastR is a package you should import in python
 - using filter() in R or query() for a subset of data. Or even, vlookup.
 - using summarize in group by.
 - Openion: WHy don't they nosql it? with queries. am i reinvting nosql? how is this not MongoDb.
 - a dataframe, is what I often call the Item object, the ith value in the itterated list.  A row . aka.
 - 
 - 
#### Chapter 2 Notes OReilly Football Analytics with Python & R, Eager & Erickson: 
 - Chosing the right players requires a tallent scout. We use statistics more than in the past, we started with punch cards.
 - With 0 meaning no cooorelation (independent variables) ,
 -  and -1 as a negative coorelation (occur mutually exclusive),
 -  and 1 as a postive coorelation (occur re-enforcingly). Meaning they 
 - unitized.
 - Stability is the reliability of the stat to stay the same,or as projected between difference circulstances with cross coorelations and oddities and meaningfull-ness of thestatisic.
 - EDA is about asking the right questions, now just using the stats blind.
 - The right answer to the wrong questionis useless is useless in and of itself, while the right question can lead you to prosperous outcomes even if you fall short of the correct answer.
 - Learning to asking the right question is a process honed by learning from asking the wrong questions. ! ! !
 - Good an dbad, and not quantifiable enough.
 - In python we select using numpy and array key access , we are realy just making "long and short" passing lengths in human understandable terms. It feels like make work. But it is nice to see, because it helps me understand the R code much better. the ifelse(condition, truevalue, falsevalue) mid mutate is kinda strange. Is this cause it is a map? Seems foreign technique.
 
   ``
   pbp["passing_yards"] = np.where(pbp["passing_yards"].isnull(), 0 , pbp["passing_yards"])
   ``

   
   ``
bpb <- bpb |> mutate( pass_length_air = ifelse(air >= 20, "long","short", passing = ifelse(is.na(passing),0,passing) )
   ``
   
 - it really is just simple trim the bad from the list. not really the best method, but a way to demonstrate what is happening. and this is our introduction.
usihg the theory of 25, median, and 7% third-quartiles we conclude the long passese are valable than short passes. Even though, they account for similear scores as a simple analysis would seem to indicate.
- the count is the number of records
- the mean is the arithmetic average
- min is minimum
- longer passes are more variable than short ones.
- it is difficult to figure out whether a particualar quarter pack will thow good deep passes in the future given the stat based on an unstable calculation. The passes for short more stable, but can even relate negative yards total. The passes for long, are of course positive, cause they are success or failure, and little chances for negative. (I preseume).
- in R we have a pattern like `` pbp -> filter() |> pull() |> summary()  ``
- in python we have a pattern like `` pbp.query('"columnVakye" == "expected"')["newColumn"].describe


   
