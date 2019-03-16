---
description: Or "Application Process"
---

# Interview Process

## General Job Application Process

The goal should ideally be, to do the least amount of work to get into the company you want to get in to.

If you don't know what company you want to join, this will increase the number of companies you are going to talk to. This can help you focus on what you want.

The general application process is like so:

1. General Call with Recruiter
2. Technical Phone Screen or Homework Assignment
3. Onsite
4. Offer extended

Knowing this process, the goal should be how many offers do we want to evaluate and we should work backwards, because this a time consuming process.

1. Offer extended
2. Onsite
3. Technical Phone Screen or Homework Assignment
4. General Call with Recruiter

### Example

If we want 3 offers, how many onsites do we need? Minimum: 3 \(Best case scenario\) Probably: 6

If we want 6 onsites, how many technical phone screens do we need? Minimum: 6 \(Best case scenario\) Probably: 12

If we want 12 technical phone screens, how many recruiters do we need? Minimum: 12 \(Best case scenario\) Probably: 15

We look at the process, work in reverse, and figure out how many offers we want.

Talking to 15 recruiters, is exhausting.

### Spreadsheets

Use a spreadsheet to manage all the companies you are talking to, and follow up steps.

Reserve a column for:

* Glassdoor Rating
* Glassdoor Salary Range
* Paysa Salary Range

### Scheduling

If we have to take at least 6 onsites, how many can we do a week? Probably: 2

If we an take 2 onsites. This means that the process will take at least 3 weeks to a month.

### Setting up meetings

Becareful about scheduling meetings/onsites back to back because they may stretch longer than the given time. They can also be very exhausting.

I use [vyte.in](https://www.vyte.in) to coordinate with recruiters about time availability.

### General Call with Recruiter

* Lasts from 15mins to 30mins. Some can last longer.

### Technical Phone Screen or Homework Assignment

* The phone screen lasts up to an hour.
* Homework assignments lasts up to two hours.

### Onsites

* These last the whole day. From 4 to 6 hours.
* Arrive early.
* Mentally taxing.
* Bring your own whiteboard markers and erasers. Theirs may suck.

Be prepared for:

* Systems Designs
* Product Design Questions
* Be careful about scheduling onsites back to back. Due to how taxing it is this can be really tiring.

#### Pair Programming

* Work with the interviewer 
* Check your data structures

#### Whiteboarding

* Not the best.
* Highly subjective.
* How precise a code do you want?
* Not the best environment available.

Whiteboard sucks:

* [https://github.com/poteto/hiring-without-whiteboards/blob/master/README.md](https://github.com/poteto/hiring-without-whiteboards/blob/master/README.md)
* [https://news.ycombinator.com/item?id=13874026](https://news.ycombinator.com/item?id=13874026)
* [http://they.whiteboarded.me/companies-that-dont-whiteboard.html](http://they.whiteboarded.me/companies-that-dont-whiteboard.html)

### Negotiation

## Deciding

* What are you prioritizing for?
* Choose a team for growth
* How will this help your spiritual growth?
* Do you have any devops?
* Do you have any SRE?
* Vacation policy?
* Sick leave policly?
* Maternity/Paternity leave?
* How does the company dogfood their own product?

### Integration

* How integrated is the company?

### Meetings

* What are meeting policies like?
* What are the laptop policies during meetings?

### Exit Interviews

* How do you handle exit interviews?

### Colleagues

* What can you learn from your new colleagues?

### Socializing/Integration

* Do you do lunch meetings?
* Do you have lunch at your desk?
* Does the team go for lunch together?
* How do you integrate new employees?

### Tooling

* What tooling do you have?
* What tools do you have for onboarding?
* What tools do you have for feedback?
* What tools do you have to manage momentum?
* What tools do you have for measurements and metrics?
* What tools do you have for effectiveness?
* How do you schedule time for building tooling?
* Is tooling an after sight?
* How much time do you spend on your tooling?

### Onboarding

* How long will onboarding take?
* How many reponsitories do you they have?
* How many lines of code?
* What programming language do they use?
* How do they maintain the language?
* What tools do they have to maintain the language?
* What tooling has the team built?
* What is your plan of attack?
* What are your companies best practices?
* How fast can you learn the context?
* How do you easy onboarding?
* How fast do you teach the require processes?

### Collaboration/Communication

* Ask how do people collaborate?
* How well is collaboration done across teams?
* How big is the team? Larger teams have much larger communication overhead.

### Momentum

* Where does the company have momentum?
* What momentum does the company have?

### Feedback

* How do I best deliver feedback?
* What platforms do you have for feedback?
* Do you have an employee engagement survey? CultureAmp
* How is feedback managed?

### Metrics

* What needles are you trying to move?
* How do you measure your metrics?

### Excitement

* What is the team excited about?

### Processes

* What processes do you have to deploy code in to production

### Miscellaneous

* What bottlenecks are you facing?
* How do you release those bottlenecks?
* How do you balance delivering business value and managing technical debt?
* How do you reduce the technical debt?
* Do you have monitoring/alerts?
* How is knowlede shared? PResentations/Demos/Repositories
* How "open" is the company?
* How is feedback managed?
* How well do the executives steer the company?

## After Joining / Accepting / Acceptance

* [https://notes.breakoutlist.com/how-to-get-the-most-out-of-working-at-a-startup-5e29b8f5f7a1](https://notes.breakoutlist.com/how-to-get-the-most-out-of-working-at-a-startup-5e29b8f5f7a1)
* Define your expectations for joining the company.
* Ask how you can be able to do your best?
* How can I set myself up for success?
* What expectations does your manager have?
* It takes about 3 weeks to normalize.

## Market Rates

* [Glassdoor](http://glassdoor.com/)
* [Paysa](https://www.paysa.com/salary-rank)

## Rejection

* Always ask for feedback.
* If you really like the company, ask how you could work together.

## Coding

Example Question:

* Make assumptions
* If they tell you are taking input from STDIN, start by just taking input from a string.
* Write example cases as comments, or part of the code execution. This gives discussion points.
* Explain assumptions about validity of input
* Create an `assert` function, which takes in the `expected` result given an `input`. See [PHP](/php#simple-assert) or [JS](/js#simple-assert)

```javascript
input = "a b c d e";

main(input) {
  ...
}

assert(expected, input) {
  console.log(input);
  actual = main(input);
  result = expected === actual;
  console.log(result);
  if (!result) {
    console.log(actual);
    console.log(expected);
  }
}

// Case 1
assert(expected, input);

// Case 2
assert(expected2, input2);

// Case 3
assert(expected3, input3);
```

## Soft Skills

| Themes | Job 1 | Job 2 |
| :--- | :--- | :--- |
| Leadership & Influence | story |  |
| Mistakes & Failures |  | story |
| Challenges | story |  |
| Teamwork | story | story |
| Successess |  | story |

From [http://www.crackingthetechcareer.com/uploads/6/5/2/8/6528028/\_handout\_-\_cracking\_the\_soft\_skills.png](http://www.crackingthetechcareer.com/uploads/6/5/2/8/6528028/_handout_-_cracking_the_soft_skills.png)

* What stories do you have on leadership and influence?
* What stories do you have about mistakes and failures?
* What stories do you have on challenges?
* What stories do you have on teamwork?
* What stories do you have on successes?

### Keywords:

* Constraints
* Feasibility
* Limitations
* Technical Challenges
* Organizational Challenges
* Fail Overs
* Distribute

### Product Management

If you have worked with multiple product/project managers, and each have had a different style of work, describe each way that you've worked.

For example:

* Quarterly goals assigned by upper management, which your program manager managed
* Weekly Sprints
* Cowboy Style \(daily reprioritizing of tasks\)

### Others

* Describe a time when you took technical feedback from a peer, and how you handled it.

