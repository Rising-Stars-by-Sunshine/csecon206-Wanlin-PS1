# # Title [How to Choice a Good Title?](https://www.nature.com/articles/s41562-021-01152-2)
## Project information
- **Author**: Wanlin Deng, Political Economy/Economics, class of 2025, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to the Problem Set 1 for [COMPSCI/ECON 206 Computational Microeconomics, 2023 Spring (Seven Week - Second)](https://ce.pubpub.org/) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**: [How to Acknowledge?](https://www.scribbr.co.uk/thesis-dissertation/acknowledgements/)
[notes: please include all professors, students, and staff who have contributed to your completetion of the project.]
- **Project Summary**: 
  - [Summarize the Background/Motivation]
  - [Research Questions]
  - [Application Scenario]
  - [Methodology]
  - [Results]
  - [Intellectual Merits and Practical impacts of your project.]
  
   
Note: please insert the screenshot of the answers to your research question by ChatGPT. The methodology that you use to address the research questions must be more innovative than both the current literature and ChatGPT. 

## Table of Contents

- model
- code
- spotlight
- more about the author
- references

### Model
* Game environment <br>

	In ancient times, countries had different wealth and military forces of different intensities. Strong countries always plan to use their military power to attack weak countries and annex their property. Vulnerable countries are always thinking about how to adopt strategies to address risks and protect their property.<br>

	Against this background, this trust game is abstract from the ancient war between countries. Anyone with high fighting capacity can take the money of those with low fighting capacity. Players with the same fighting capacity cannot take wealth from each other. Players can form alliances, and their fighting capacity is the sum of both sides. They all want to get more wealth, or at least not worse off. <br>
	
	In this game, players will first need to decide on forming alliances with whom. Then, to persuade other players to ally with him, player 1 promises he won’t seize his partner’s money and can decide to offer some money to his potential partner to show his loyalty. After this, player 1’s target partner can see the money player 1 offer and redecide whether to cooperate with player 1. If they cooperate with player 1, player 1 will seize the remaining player’s money automatically. Next, player 1 will decide whether to break the cooperation and take his partner’s money.<br>
	
	
* Set of players <br>

	We assume that there are three players in this game. Each player has given the fighting capacity and money. <br>
Player 1 has 10 dollars, and his fighting capacity is 5.<br>
Player 2 has 3 dollars, and his fighting capacity is 2.<br>
Player 3 has 4 dollars, and his fighting capacity is 3.<br>

* Strategies <br>
	Each player has three strategies.<br>
	Player 1: ① Not to cooperate ② Cooperate with player 2 and provide x dollars to persuade player2 ③ Cooperate with player3 and provide x dollars to persuade player3<br>
	Player 2: ① Not to cooperate ② Cooperate with player 1 ③ Cooperate with player3<br>
	Player 3: ① Not to cooperate ② Cooperate with player 1 ③ Cooperate with player2<br>

	
	
* Payoffs <br>
	1.	No matter how much player 1 chooses to offer, player 2 and player 3 form an alliance and share 5 fighting capacities.
In this case, Player 1 cannot attack player 2 and player 3, and player 2 and player 3 can protect their original wealth. As a result, player 1 will have 10 dollars, player 2 will have 3 dollars and player 3 will have 4 dollars.<br>
	2.	Player 1 offers x dollars to player 2 and player 2 chooses to form an alliance with player 1. After seizing player 3’s money, player 1 breaks his promise and seizes player 2’s money. As a result, player 1 can have 17 dollars, player 2 and player 3 have 0 dollars.<br>
	3.	Player 1 offers x dollars to player 2 and player 2 chooses to form an alliance with player 1. After seizing player 3’s money, player 1 keeps his promise and doesn’t seize player 2’s money. As a result, player 1 has (14-x) dollars, player 2 has (3+x) dollars, and player 3 has no dollars.<br>
	4.	Player 1 offers x dollars to player 3 and player 3 chooses to form an alliance with player 1. After seizing player 2’s money, player 1 breaks his promise and seizes player 3’s money. As a result, player 1 can have 17 dollars, player 2 and player 3 have 0 dollars.<br>
	5.	Player 1 offers x dollars to player 3 and player 3 chooses to form an alliance with player 1. After seizing player 2’s money, player 1 keeps his promise and doesn’t seize player 3’s money. As a result, player 1 has (13-x) dollars, player 2 has 0 dollars, and player 3 has (4+x) dollars.<br>



	
* Solution based on forward induction <br>

	Here we use forward induction to solve the game. Forward induction is based on the assumption that past play was rational(Govindan and Wilson 2009). That is, players may form a belief of what types of other players are by observing their past actions. And players can make decisions based on their beliefs.<br>
	
	To disrupt other players’ cooperation, player 1 wants to cooperate with one of the other players, thus seizing the remaining player’s money. To reach cooperation, player 1 promises that he won’t seize his partner’s money after seizing another player’s money and offers part of his money to his partner at the beginning to show his loyalty. <br>
	
	Suppose that player2 and player3’s original willingness to form an alliance with player1 is 0 (with a maximum of 1). The more wealth player1 offer to his partner, the more his partner will believe that player1 will not ultimately disrupt their cooperation (i.e., not rob their wealth), and the more he is willing to cooperate with player1. The relationship between other players’ willingness to cooperate and the money player1 offered can be modeled as: <br>

	 $$w = \frac{c \times money\ offered}{potential\ partner's\ original\ money}$$,

	
	where c refers to a constant parameter.<br>
	
	And the willingness of player 1 to break the cooperation and seize his partner’s money is negatively related to player 1’s current money and positively related to his partner’s current money and time. <br>
	
	Based on this forward induction, the solution is that player 1 will offer money to player 2 and persuade player 2 to form an alliance with him successfully. After cooperating with player 2 and seizing player 3’s money, player1 will break the cooperation and take player 2’s money. Finally, Player 1 can have 17 billion dollars, while player 2 and player 3 can only have 0 billion dollars. <br>

* Evaluation<br>

	Efficiency: 
	
	Socially efficiency refers to the optimal distribution of resources in society, taking into account all external costs and benefits as well as internal costs and benefits (Pettinger 2019). Pareto efficiency refers to the situation no one player can be better off without making any other player worse off (“Pareto Efficiency - an Overview | ScienceDirect Topics,” n.d.). <br>
	
	In this game, the total payoffs among the three players are given and will not change according to how they behave. Every profile maximizes the sum of payoffs across all players in the game. Thus, this equilibrium solution, as well as other solutions, is socially efficient. Also, since the total payoffs are given, no one can get more payoffs without harming others’ payoffs for every solution. Thus, this equilibrium solution, as well as all other solutions, is Pareto efficient. <br>


	Fairness: 
	
	In this project we define the solution as outcome fair if all the players finally have the same payoffs. And we defined the solution as gaining fair if all the players can get the same amount of increasing (or decreasing) payoff during the process of playing games.<br>
	In this solution, player 1 will get all the money, and player 2 and player 3 will have nothing. Players cannot get the same payoffs at the end. Thus, this solution is not outcome fair. Compared to the beginning, player 1 gets 7 more dollars, player 2 losses 3 dollars, and player 3 losses 4 dollars. Hence, this solution is not a gaining fair.<br>



### Code
* Customized oTree demo code in zip. <br>

	The code is uploaded to the repository. <br>


* Description on how I customize the demo
	1. Endowment and multiplier <br>
	In oTree demo, I have changed the number of players to three. Moreover, in addition to having different money, each player is also endowed with different combat abilities. In the game, players will determine the strategy based on their initial combat power. The flow of the game is also pretty different from the demo. Multiplier is not applicable in my game. <br>
	
	2. Demonstration <br>

		There are three stages in the game. In the first stage, players first need to understand the consequences of allying with different players based on the game introduction and then decide their strategies. If everyone is rational, player 2 will form an alliance with player 3, which means player 1 can't seize their money.<br>
		
		In the second stage, to break this balance, player 1 will need to decide how much he is willing to give his target partner to persuade the target partner to collaborate with him. Then his target partner will need to decide whether to believe player 1 and cooperate with him.<br>
	
		In the third stage, once the loyalty of player 1 persuades his target partner and reaches cooperation successfully, player 1 will loot another player's wealth, and this player's wealth will be cleared automatically. Then, player 1 must decide whether to keep his promise and not rob his partner's money. After this decision, the game will end.<br>
	
		However, due to the page limit (8 pages) for the free use of oTree, the game demo lacks one waiting page in the third stage. The result will be accurate after player 1 decides whether to break the cooperation. Player 2 and player 3 should wait until player 1 makes the decisions before they click the button to reach the result page. That is, they should wait on the situation overview page until they were informed artificially that player 1 had made decisions.<br>

* Explaination on how subjects behavior playing the customized demo might be different from the behavior playing the oTree demo and why. <br>

	In the demo trust game, player A has $1000 and player B has $0. If player A choose to give B x dollars, player B will receive 10x dollars. Player A needs to decide how much he wants to give B and then player B needs to decide how much he is willing to give back to A after he receives the money. In this game, although cooperation will benefit both players, since player A and player B are strangers to each other and A cannot form any trust in B, player A tends not to send money to player B. <br>
	
	However, in the customized demo, although the cooperation between player 2 and player 3 is the safest strategy for them, player 1 still has a high possibility to cooperate with player 2 or player 3 successfully. Since player 1 has a chance to show his loyalty by offering some money, other players can form beliefs based on player 1’s actions and build trust before they make the final decision of cooperation. In other words, the additional trust-building activities increase the possibility for player 1 to cooperate with others.

### Spotlight


In this part, I will discuss the behavioral experimental research paper *Unintended effects of open data policy in online behavioral research: An experimental investigation of participants’ privacy concerns and research validity* (Liu and Wei 2022). Also, I will discuss the reinforcement learning algorithm paper *Dynamic trust game model between venture capitalists and entrepreneurs based on reinforcement learning theory* (Haiyan 2018). <br>

*Behavioral experimental research paper*

* What research question does the behavioral experimental research intend to address? <br>

	This research paper intends to address the problem about what are open-data policy’s effects on participants’ privacy concerns and their willingness to be honest, and what are the potential solutions to remove the unintended effect.
	
* How does behavior in the experiments differ from backward induction? <br>

	Backward induction in game theory is an iterative process of reasoning backward in time, from the end of a problem or situation, to solve finite extensive form and sequential games, and infer a sequence of optimal actions(“Backward Induction” 2019). Based on the backward induction, since participants are worried about privacy violations, they tend not to continue the research or select “choose not to answer”. However, the result of the experiments shows that only the rate of affirmative answers (not their disclosure level) is significantly affected.
	
* What is the behavioral (e.g., psychological, social) foundation that underpinning the observed behavior? 
	1.	Participants care about the payment for attending the research. They don’t want to be rejected by researchers due to their apparent nondisclosure. So they sometimes will force themselves to be disclosed even when they feel uncomfortable.
	2.	Because people are afraid of privacy leaks, they tend to select answers that are in line with socially approved behaviors.

*Reinforcement learning algorithm paper*
* What is the game environment and the learning algorithm? <br>

	1.	Game environment<br>

		Venture capitalists conduct credit assessments on startups and provide financial support for them; Entrepreneurs receive financial support from venture capital companies and provide returns for them. Investors can profit from their investments, but if other participants do not follow the rules and fulfill their commitments, they will suffer losses. Therefore, trust is risky and uncertain. Venture capitalists and entrepreneurs need to make trust strategies in this situation.
	
	2.	Learning algorithm <br>
	
		Q-Learning is a model-free reinforcement learning algorithm used to learn a policy for making decisions in an environment. The algorithm is based on estimating the expected utility or value of an action taken in a given state, which is called the Q-value. The Q-value represents the expected total reward that can be obtained by taking a specific action in a given state and following a specific policy thereafter (Amine 2020). <br>
		
		This paper uses a variant of the Q-learning algorithm called actor-critic Q-learning (Haiyan 2018) to learn the optimal strategy for both the venture capitalists (VCs) and the entrepreneurs in the game. The algorithm consists of two main components: the actor and the critic. The actor is responsible for choosing the actions of the agent (either the VC or the entrepreneur), while the critic evaluates the chosen actions and provides feedback to the actor. The algorithm uses a reward function to determine the value of each action, and the goal is to maximize the cumulative reward over time.<br>


* How are the strategies from the reinforcement learning agents inspires you on trust building among humans? <br>

	The dynamic trust process between venture capitalists and entrepreneurs is a process of mutual learning. More specifically, venture capitalists and entrepreneurs make trust decisions based on their interactive experiences. Venture capitalists and entrepreneurs make trust decisions based on the returns at different stages and update their strategies and trust status accordingly. Venture capital firms can monitor the efforts of entrepreneurs by offering fewer investments in the early stages. Entrepreneurs can check the amount of venture capitalists' investment in the later stage to decide how much effort they will put in the future. <br>

	This inspires me that building trust requires both parties to sacrifice some of their interests at a specific time to showcase themselves. Although cooperation is mutually beneficial, before their trust is stable, both parties need to rely on most of their own actions and a small portion of the other party's help to reach some results in a short period, thus demonstrating their potential and credibility. Hence, the best way to gain the trust of people's potential partners as soon as possible is to compromise more interests at the beginning.

### More about the Author
* Self-Intro 

<img src="生活照.png" width="100px">

My name is Wanlin Deng, and you can also call me Iris. I’m from the class of 2025 and my major is political Economy with a track in economics. I’m interested in the interdisciplinary field of computational economics. Now, I’m working on utilizing all the math, econ and coding knowledge to study economics in a more critical way, and hope to become a competitive person who possesses a truly interdisciplinary capability. <br>

Nice to meet you guys here and look forward to our future cooperation!

### References

- Literature References in [Chicago Author-Date](https://www.chicagomanualofstyle.org/tools_citationguide/citation-guide-2.html) Style and [BibTex](https://scholar.google.com/) 

Amine, Amrani. 2020. “Q-Learning Algorithm: From Explanation to Implementation.” Medium. December 19, 2020. https://towardsdatascience.com/q-learning-algorithm-from-explanation-to-implementation-cdbeda2ea187.

“Backward Induction.” 2019. Investopedia. 2019. https://www.investopedia.com/terms/b/backward-induction.asp.

Govindan, Srihari, and Robert Wilson. 2009. “On Forward Induction.” Econometrica 77 (1): 1–28. https://www.jstor.org/stable/40056520.

Haiyan, Li. 2018. “Dynamic Trust Game Model between Venture Capitalists and Entrepreneurs Based on Reinforcement Learning Theory.” Cluster Computing 22 (S3): 5893–5904. https://doi.org/10.1007/s10586-017-1666-x.

Levin, Dan, and Luyao Zhang. 2020. “Bridging Level-K to Nash Equilibrium.” *The Review of Economics and Statistics* 104 (6): 1329–40. https://doi.org/10.1162/rest_a_00990.

Liu, Bingjie, and Lewen Wei. 2022. “Unintended Effects of Open Data Policy in Online Behavioral Research: An Experimental Investigation of Participants’ Privacy Concerns and Research Validity.” Computers in Human Behavior, October, 107537. https://doi.org/10.1016/j.chb.2022.107537.

“Pareto Efficiency - an Overview | ScienceDirect Topics.” n.d. Www.sciencedirect.com. https://www.sciencedirect.com/topics/economics-econometrics-and-finance/pareto-efficiency.

Pettinger, Tejvan. 2019. “Social Efficiency.” Economics Help. September 17, 2019. https://www.economicshelp.org/blog/2393/economics/social-efficiency/.

“Strategy (Game Theory).” n.d. Encyclopedia.pub. Accessed May 10, 2023. https://encyclopedia.pub/entry/36857.

```
@article{levin2022bridging,
  title={Bridging level-k to nash equilibrium},
  author={Govindan, Srihari, and Robert Wilson},
  journal={Review of Economics and Statistics},
  volume={104},
  number={6},
  pages={1329--1340},
  year={2018},
  publisher={MIT Press One Rogers Street, Cambridge, MA 02142-1209, USA journals-info~…}
}
```
```
@article{
  title={Dynamic Trust Game Model between Venture Capitalists and Entrepreneurs Based on Reinforcement Learning Theory},
  author={Li,Haiyan},
  journal={Computers in Human Behavior},
  volume={October},
  number={107537},
  year={2022}
}
```
```
@article{
  title={Unintended Effects of Open Data Policy in Online Behavioral Research: An Experimental Investigation of Participants’ Privacy Concerns and Research Validity},
  author={Liu, Bingjie, and Wei Lewen},
  journal={Cluster Computing},
  volume={22},
  number={S3},
  pages={5893–5904},
  year={2022}
}
```
```
@article{
  title={Q-Learning Algorithm: From Explanation to Implementation},
  author={Amine, Amrani},
  journal={Medium},
  year={2020},
  url={https://towardsdatascience.com/q-learning-algorithm-from-explanation-to-implementation-cdbeda2ea187}
}
```
```
@article{
  title={Backward Induction},
  journal={Medium},
  year={2019},
  url={https://www.investopedia.com/terms/b/backward-induction.asp}
}
```
```
@article{
  title={Pareto Efficiency - an Overview | ScienceDirect Topics.},
  author={Pettinger, Tejvan},
  year={2019},
  journal={Economics Help.},
  url={https://www.economicshelp.org/blog/2393/economics/social-efficiency/](https://www.economicshelp.org/blog/2393/economics/social-efficiency/}
}
```
```
@article{
  title={Pareto Efficiency - an Overview | ScienceDirect Topics.},
  url={https://www.economicshelp.org/blog/2393/economics/social-efficiency/}
}
```
```
@article{
  title={On Forward Induction},
  journal={Econometrica},
  year={2009},
  pages={1--28},
  url={https://towardsdatascience.com/q-learning-algorithm-from-explanation-to-implementation-cdbeda2ea187](https://www.investopedia.com/terms/b/backward-induction.asp)](https://www.jstor.org/stable/40056520}
}
```
