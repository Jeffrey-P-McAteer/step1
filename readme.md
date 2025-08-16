
# Step1

`step1` stores and queries process data for large organizations, with a focus on
enabling complex processes to begin at their most-efficient place and allowing anyone in the
organization to access this data in `<2s` (i.e. their typing speed ought be the bottleneck, not the machines).

Design is in it's infancy; some notable requirements even at an early stage are:

## Design Requirements

 - non-human-in-the-loop query/update interfaces for `cli`, `python`, potential other `C/C++/Java` tools which power enterprises in the 21st century
 - cryptographic integrity for authorship of all data
    - We'll simplify certificate management by using a trust-on-first-contract design
 - high, predictable performance
    - We should be able to estimate the number of instructions servers need to answer queries knowing only query size and dataset size
    - This allows planners to make statements like "a 4ghz 1 CPU VM is capable of answering our org's process questions at a rate of 1,000 queries/second"
 - horizontal scalability
    - In direct support of high performance clients should be able to recieve and select from a set of N servers such that an organization can grow until a single server is filled with process data.
    - No support for having >1 server's worth of storage to manage process data is planned - given that we are querying graphs, which are often even smaller than text, the whole planet's process data could be stored on a `1tb` drive.



## Example of Stored Process Data and queries (Design) - simple

McBurgerBell has a process to order and serve food using a drive-through. We'll derive the process from final outcome working backwards,
once stored the process may be flipped for queries and other lookups such as process joins using input/output meta-data.

1. Customer Leaves with Burger they paid for
2. Customer is handed Burger
3. Customer pays for burger
4. Customer orders burger
5. Customer drives to McBurgerBell
6. Customer decides to eat at McBurgerBell
7. Customer feels hungry

## Example of Stored Process Data and queries (Design) - complex

GrandePox has infested the world with a disease making the digestion of coffee impossible!

The solution to this problem rarely resides entirely in one organization and
requires several different systems to be aware of and interact with eachother at certain times.

Let's break it down again in reverse chronological order, but we'll annotate overlapping tasks.

### Local Pharmacy

1. Customer can take a GrandePox curing pill
2. Customer is handed GrandePox curing pill
3. Customer pays for GrandePox curing pill
4. Customer orders GrandePox curing pill
5. Customer is aware GrandePox curing pill is available from local pharmacy

### Contract Manufacturing Org

1. CMO ships+delivers bottles of GrandePox curing pill to Pharmacies
2. CMO manufactures bottles of GrandePox curing pill
3. CMO is approved by Local Government to manufacture GrandePox curing pill
4. CMO decides to manufacture GrandePox curing pill
5. CMO researches profitable drugs to manufacture

### Local government

1. Local government approves new GrandePox curing pill
2. Local government tests new GrandePox curing pill in some low-risk manner
3. Local government recieves request to approve new GrandePox curing pill
4. John, a government employee, picks up the office mail monday morning.

### Research Lab

1. Research lab sells GrandePox curing pill IP to Contract Manufacturing Org


`TODO finish ^^^`






