# The-Boundary-Paradox_Geometric_Dist
Why the fastest event in cricket is the least predictable one
Cricket, like many sports, is rich with patterns waiting to be discovered through the lens of statistics. In this analysis, we explore a fascinating question: How many legal deliveries does a batting team typically face before recording their first wicket or first boundary?
Using ball-by-ball data from the IPL 2026 season, we applied the Geometric distribution—a probability model that describes the number of trials needed to achieve the first success. Our analysis reveals:
First wicket: A batting team faces, on average, 19.13 legal deliveries before their first wicket falls.
First boundary: A team typically needs only 4.44 legal deliveries to hit their first boundary.
The "Memoryless" property: The Geometric distribution suggests that the probability of a wicket or boundary doesn't depend on how many balls have already been bowled. Our data shows this holds remarkably well for wickets but deviates for boundaries.
This report unpacks these findings and explores how the game's different phases—powerplay, middle overs, and death overs—dramatically alter these probabilities.
1. Introduction: The Geometry of Cricket
1.1 The Question Behind the Numbers
Every cricket fan knows the tension of the first over. Will the opening batsman hit a boundary? Will the bowler strike early? But have you ever wondered: How many balls does it really take, on average, for these events to occur?
Enter the Geometric distribution—a statistical model that answers exactly this type of question. It helps us understand the "waiting time" until a specific event happens for the first time.
1.2 Our Data Source
We analyzed ball-by-ball data from the IPL 2026 season, spanning:
17,501 total deliveries
16,639 legal deliveries (excluding wides, no-balls, etc.)
870 wickets from legal deliveries
3,746 boundaries (4s and 6s) from legal deliveries
For each innings, we tracked:
The delivery number on which the first wicket fell (or whether no wicket fell—a "censored" observation)
The delivery number on which the first boundary was scored (or whether no boundary was scored)
