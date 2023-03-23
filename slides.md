---
theme: gaia
_class: lead
paginate: true
backgroundColor: #EeEeFf
marp: true
---

# Developer Productivity

---

## What is productivity?

As a developer you might...

* Fix bugs
* Add new features
* Refactor code

---

<!-- ## If it's a thing... can it be measured? -->
```c
float Q_rsqrt( float number )
{
	long i;
	float x2, y;

	const float threehalfs = 1.5F;
	x2 = number * 0.5F;
	y  = number;
        // evil floating point bit level hacking
	i  = * ( long * ) &y;                       
        // what the fuck? 
	i  = 0x5f3759df - ( i >> 1 );               
	y  = * ( float * ) &i;
        // 1st iteration
	y  = y * ( threehalfs - ( x2 * y * y ) );   
        // 2nd iteration, this can be removed
        // y  = y * ( threehalfs - ( x2 * y * y ) );   
	return y;
}
```

---


```js
function isEven(number) {
    if (number == 0) return true;
    if (number == 1) return false;
    if (number == 2) return true;
    if (number == 3) return false;
    if (number == 4) return true;
    if (number == 5) return false;
    if (number == 6) return true;
    if (number == 7) return false;
    if (number == 8) return true;
    if (number == 9) return false;
    if (number == 10) return true;
    if (number == 11) return false;
    if (number == 12) return true;
    if (number == 13) return false;
    if (number == 14) return true;
    if (number == 15) return false;
    if (number == 16) return true;
    if (number == 17) return false;
    if (number == 18) return true;
    if (number == 19) return false;
    ...
    if (number == 499) return false;
    if (number == 500) return true;
}
```
---
- Define productivity in broad stokes, 
- Make sure to outline that productivity can take many forms, and that good metrics are really hard.
	- Different types of productivity can't be directly compared,
	- "Producing" isn't necessary for productivity. (time spend reviewing/improving is still productive)
	- Not all lines of code are equal
	- Learning is productive

## Introduce the main pitfalls

1. Technical Debt
2. Inefficient sharing of knowledge (siloing)
3. Misdirected Work
4. Poor tooling


## Technical Debt

### Quick definition of technical debt

Small audience interaction, ask people to raise hand if they have ever written code that made them feel as if they needed to apologize for it in a comment.

Follow up by talking about the reasons this might have happened valid or otherwise.

### Causes / Repercussions
 - The trade off between speed now and speed later
 - Just like real debt, technical debt has interest to pay.
 - Technical debt isn't always bad, but it must be accounted for
 - Technical debt can slow development to a crawl

### How to deal with it

 - Proactive prevention
 - Code reviews
 - Pay attention to Signal/Noise ratio 


## Knowledge Finding

### Introduce what is meant by knowledge finding

 - Searching for information
	 - This can take the form of
	 - Asking coworkers
	 - Documentation
	 - Internet searches
	 - etc.

### Stack overflow stats

 - Teams encounter a lot of knowledge silos
 - [teams spend a lot of time looking info and answering questions](https://survey.stackoverflow.co/2022/#section-productivity-impacts-daily-time-spent-searching-for-answers-solutions)

### How to prevent
- Take time to pre-emptively document procedures and protocols
- Communicate with coworkers, even across teams, 
	- Different companies will have different amounts of overlapping concerns


## Misdirected Work

Just because it takes effort, does not make it productive.

### Outline different types

- Overlapping work
	- If two people end up doing the same thing, this not only contributes to technical debt, but also is spent time that could be used for something else.
- Unnecessary work
	- Some things aren't really that important
	- Constantly re-evaluate what the most effective thing you could be doing is
- Misguided work
	- Using the wrong tool
	- the wrong algorithm 
	- there's something small your not considering

### Prevention

- Plan tasks before starting (to a reasonable degree)
- Communicate your intentions with your team
- If you hit a block, 
	- Talk about it
	- Take a break
	- Break into the silo


## Conclusion

Quick rundown of the different pitfalls / lessons learned about each

### Open ended question

What aspects do you think are different in a professional versus school setting when it comes to productivity.


## Sources
[Starter Source](https://shopify.engineering/modelling-developer-infrastructure-teams)
[technical debt](https://medium.com/serious-scrum/the-hidden-cost-of-technical-debt-1963b958e5ed)
[stack overflow servey](https://survey.stackoverflow.co/2022/#professional-developers-productivity-impacts)
