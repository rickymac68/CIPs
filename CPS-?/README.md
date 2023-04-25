---
CPS: ?
Title: Cardano Governance Security
Category: Meta
Status: Open
Authors:
    - Richard McCracken <rickymac68@icloud.com>
    - Andrew Westberg <andrewwestberg@gmail.com>
Proposed Solutions: N/A
Discussions:
    - https://github.com/cardano-foundation/CIPs/pull/490
    - https://github.com/cardano-foundation/CIPs/pull/491
Created: 2023-03-28
---


## Abstract

As Cardano's community-led governance system goes live, it's crucial to address the security of the governance mechanism in a way that informs all participants of potential weaknesses and how to mitigate them. The guidelines provided in the CIP are relevant to various groups, including Constitutional Committee members, Delegation Representatives, Stake Pool Operators, voters, and all Ada holders. Moreover, the guidelines are applicable to wallet, dApp, and infrastructure developers to help them build situational awareness and design governance security considerations into their development processes.

These recommendations are the result of a collaborative effort among cybersecurity, financial, and game theory experts, as well as participants of the Voltaire workshop, including developers, stake pool operators, representatives from IOG, Cardano Foundation, and Emurgo, members of Project Catalyst, and members of the Cardano community.


## Problem

The Cardano community's on-chain governance mechanism, Voltaire, is susceptible to various types of attacks that may compromise its security. This system defines on-chain decision-making that is automatically executed when a certain threshold of approval by human actors is met. To ensure maximum awareness of potential threats and vulnerabilities, this document will enumerate and describe each threat or vulnerability, including recommended mitigation techniques. It is crucial that all stakeholders, including voters, developers, and governance actors, are informed of these risks to identify and prevent any damage or, in the case of a threat event, facilitate recovery.

In rare instances, a threat may be identified that requires responsible reporting procedures to prevent exposing an active vulnerability to bad actors seeking to exploit it. In such cases, it is essential to notify the appropriate group or entity with the ressources, or are responsible for mitigating the threat in a confidential manner.

### #1: Unknown software vulnerability affecting governance is discovered.

An assumption is that are no known software back doors. Unknown software vulnerabilities may be discovered.

**Recommendation:Pre-planned Response** The person discovering the vulnerability should take the following steps:
* Document the vulnerability: The first step is to document the vulnerability as accurately as possible. This documentation should include a detailed description of the vulnerability, steps to reproduce it, and any other relevant information.
* Notify the relevant parties: The next step is to notify the appropriate parties, including the developers of the software, the blockchain community, and any relevant authorities. It's important to provide as much information as possible, so that the parties involved can understand the scope of the vulnerability and take the necessary steps to address it.
* Keep the vulnerability confidential: It's important to keep the vulnerability confidential until a fix has been implemented. This will prevent hackers from exploiting the vulnerability before it's patched.

### #2: Emergency change that needs to be done quickly.
* A nuclear option where the change requires “just do it” 
* A security fix that must be implemented but the nature cannot be communicated publicly.
* The emergency change may, or may not, require a vote on a hard fork or parameter change.
* This section may be in respose to section #1 above, or for other emergencies bug fixes.
* The emergency change may have to be coordinated by IOG for the Haskell based Cardano nodes, or the primary software provider of any other Cardano node implementations.

**Recommendation: Pre-planned Response 2.A and 2.B**

#### 2.A: For an Emergency change only requiring the SPOs, yet affects governance or voting:
1. IOG provide the Stake Pool Operators with clear and concise instructions for implementing the software change. Emphasize that while the change is not mandatory, but must be implemented without delay. Explain: What is the impact? Communicate the urgency of the change to the SPOs, without providing specific details about the threat or catastrophic failure. The operators should be aware of the importance of the change, but not necessarily the reasons behind it.

2. SMEs provide technical support to the SPOs as needed as they implement the change, if there are any hardware requirements, configuration file requirements, etc... Most SPOs are proficient but be careful to provide necessary details during emergency changes. Optimally software is tested on test nets first but a need may arise where use of the test net is not an option.

3. Monitor the network closely after the change has been implemented, to ensure that it is functioning correctly and that there are no unforeseen issues or problems. Once the change has been successfully implemented across a high % of Cardano nodes and the network is stable, consider whether it is appropriate to provide more information about the reasons for the change. If not, continue to emphasize the importance of keeping the details confidential in order to protect the security and stability of the network.

#### 2.B: For an Emergency change requiring on chain approval Governance Action:
* May require a hard fork or parameter change, or both.
* May require DReps, CC, and SPO coordination.
* May require trusted coordinators from the Cardano Foundation (CF) or IOG.

1. (CF/IOG?) Assemble a team of technical experts to develop and submit the on-chain governance action proposal. This team should include software engineers, network administrators, and other relevant experts who can ensure that the proposal is technically correct and addresses the identified issue.

2. Communicate the governance action proposal to the SPOs, DReps, and CC. Emphasize the importance of maintaining discretion regarding the issue and the need for a prompt vote to approve the proposal. This may take some extensive debate and convincing. Trust may be a factor.

3. SMEs should communicate the urgency of the change to the SPOs, DReps and CC without providing specific details about the threat or catastrophic failure if discretion is required. SMEs may have to communicate the impact if the proposal is not approved.

4. Offer technical support to the voters as needed, as an emergency response may cause people to rush and make mistakes.

9. IOG, CF, SPOs, and dApp creators will have to monitor the network closely after the governance action has been approved and activated, to ensure that it is functioning correctly and that there are no unforeseen issues.

### #3: Emergency Group required to support the Disaster Recovery Plan.
* An Emergency Group may be needed in the event of disaster recovery of the network, or an emergency change must be implented as described in section #3 below. This scenario for an Emergency Group may occur under various unknown conditions. The current disaster recovery scenarios involve "Long Lived Network Wide Partitions" and a scenario involving "Long Lived Global Outage" both referenced at this link https://iohk.io/en/research/library/papers/cardano-disaster-recovery-plan/

* Both disaster scenarios are currently and primarily handled by the stake pool operators, and do not yet require governance individual's private keys to get the Cardano network back to normal operation. 

* In the event that governance individuals and their keys are required to recover the network, a threat exists where attacks on the persons if known and their keys would prevent recovery on the Cardano network. This section offers recomendations to pretect these key critical persons, their governance keys, and the concept that we don’t want attackers to know who the main coordinators are in Disaster Recovery Plan. 

**Recommendation: Pre-planned Response**

Notify the current Constituional Commitee of the person in charge of the Emergeny Group responsible for the disaster recovery so that they know any governance actions submitted by the group are valid, or that some level of trust is established. To minimize the risk of physical and cyber threats, The Emergency Group needs to protect their private keys and identities, and ensure that the Cardano network can be recovered in the event of a disaster. Notify Delegator Representatives as needed in the event that they and their keys are required to recover the Cardano network:

1. (CF?) Identify and select a group of trusted individuals who will be responsible for disaster recovery. These individuals should be chosen based on their experience, skills, and trustworthiness.

2. Ensure that each individual in the group understands the importance of their role in disaster recovery and the need to keep their involvement confidential.

3. Provide training as needed to the Emergency Group on security best practices, including physical security, cybersecurity, and operational security. This training should include:

- Keeping their private keys secure: This includes storing them in secure locations, such as a safe or a safety deposit box, and using strong passwords or passphrase to protect them.
- Limiting access to their keys: Only authorized individuals should have access to their keys, and the keys should be stored in a way that prevents key compromise.
- Using secure communication channels: All communication should be encrypted and transmitted over secure channels to prevent interception and eavesdropping.
- Operational security: The group should be aware of their surroundings and take steps to minimize the risk of physical threats, such as surveillance or theft.

4. Develop a contingency plan for the group in the event of a security breach. This plan should include steps to revoke compromised keys, notify other members of the group of the breach, and initiate recovery procedures. Experts may need to provide guidance to Delegator Representatives. 

5. Implement measures to protect the group's identities, such as using pseudonyms or code names when communicating with each other. Consider the Constitutional Committee or Delegator Representatives may need confirmation from the Emergency Group for actions taken.

6. Limit the number of people who know the identities of the Emergency Group members to minimize the risk of information leaks. The identity of the group members should only be disclosed on a need-to-know basis.

7. When Stake Pool Operators are requred to take action, have trusted experts communicate with them via the normal Stake Pool Operator channels so they know they are getting information from the correct source. Switch to less public channels if the normal channels are suspected of being compromised.

8. Regularly review and update the security measures in place to ensure that they remain effective. Possibly do a periodic practice disaster recovery drill on one of the test networks.

### #4: Operational Security (OPSEC) of the committee.
  * Physical security
  * Digital security

**Recommendation:**

### #5: Committee keys lost or stolen or committee keys sold to a bad actor.

**Recommendation:**

### #6: DRep keys lost or stolen or DRep keys sold to a bad actor.

**Recommendation:**

### #7: Lack of governance for an extended period of time.
  * Uncontrolled hard forks by SPOs
  * Risk of no confidence

**Recommendation:**

### #8: Lack of trust in voter tooling.

**Recommendation:**

### #9: Trust in the wallets.
  * wallet voting attack vector
  * hardware wallet support

**Recommendation:**


### #10: Corruption - in any form, any number of actors.
  * Code of Conduct mitigation
  * on-chain mitigation


**Recommendation:**

### #11: Collusion - the bad version of collaboration to do something illegal or undesirable.

**Recommendation:**

### #12: Vote buying - Ada kickbacks.
**Problem: Buying and Selling of Delegation** 
 * With regard to [CIP-1694](https://github.com/JaredCorduan/CIPs/blob/voltaire-v1/CIP-1694/README.md), Treasury withdrawals come to mind but there could be a market for delegation on most any governance action. It seems that in a close election where there is a lot of ADA waiting on the outcome, a market for delegation is created where delegation becomes much more valuable as we approach the [end of an epoch](https://github.com/JaredCorduan/CIPs/blob/voltaire-v1/CIP-1694/README.md#lifecycle) when votes are tallied. Payment for delegators could be in ADA or another currency. So there may be a perverse incentive for delegators to wait till the last minutes of an epoch before delegating in order to get the best price for their delegation. Aside from corrupting the election, it could also overload the system as votes come in at the last moments before an epoch closes. 
  * Delegation is linked to wallets in an obvious way so payment for delegation could be most easily made in ADA.  
  * In this market for delegation:  
    * Where it is known exactly how much delegation you still need in order to get the ADA for your project out of the treasury,  
    * which makes possible to calculate with certainty the price for delegation which leaves you with your target profit margin intact,  
    * and where you can broadcast an offer to purchase delegation,  
    * and where you can see exactly which wallets are delegating to you in response to your offer...  
    * Then you know exactly where to send the delegator's share of ADA after snatching it from the treasury.  
    * Likely this fraud could be automated via smart contract in a trustless manner such that the price for  delegation is displayed and so that the dishonest delegators would not need to trust the dishonest DRep for payment.  
    * This attack could also be carried out on a vote for parameter change or on any other governance action.  

**Modeling Cardano Governance On Bee Democracy**  
  * The notion that we are locked into any given voting system because of current blockchain structure is an illusion  
    * Our community can build anything it wants if we believe we can  
    * Let's build a blockchain to fit our voting needs not a voting system to fit our blockchain   
  * Bee Democracy
    * Over millions of years, through the process of evolution, nature has already worked out the form of democracy which produces the most truth and best results for its citizens  
    * [This video explains Bee Democracy](https://youtu.be/NDnQ4pAjBUg?t=310)  
    * Bee Democracy has DReps. Let's call them BReps. 
    * These are the scouts which return to the hive with information about a particular proposal (A new location for the hive)
    * From the video we see that BReps dance for the delegators to communicate why their proposal is the best.
    * Unlike our DReps... 
      * BReps (the scouts) compete for delegation with no reward except for survival of their hive which includes their own survival  
        * If paying scouts for their work produced more truth than simply working for their own survival and prosperity then evolution would have selected for that  
      * BReps only receive delegation for the proposal they are currently soliciting for - Then delegation ends  
        * This is key to a functioning democracy - DReps in the bee's world have to earn their delegation for each proposal  
        * In human democracy the DReps only their earn delegation once and then learn to exploit their power for personal gain during the rest of their careers  
        * Bee democracy is structured like so because those structured differently were all selected out of existence  
        * We should model our democracy after the one which nature has perfected over the course of millions of years  
    * **Abstracting bee democracy functions and applying these to Cardano governance** 
      * Each BRep must solicit for delegation on each and every proposal using an online document (a solicitation) which explains their position and which also locks their vote. 
      * The mechanism is an on-chain transaction with a signed vote and the hash of an immutable webpage
      * The BRep's vote is cast and embedded in the solicitation with their digital signature. 
      * The BRep's vote can not be changed once the solicitation has been published so delegators know what they are getting
      * Delegators delegate ADA to the BRep's solicitation rather than to the BRep directly  
      * Delegators may change their delegation at any time before the final tally
      * Delegators may not vote directly, rather Delegators may register as a BRep and then delegate ADA to their own solicitation if they wish and then vote on that. 
      * This structure ensures that:  
        * Delegators have lots of good information to make their decisions  
        * Delegators are deliberately casting their delegation of ADA for a given proposal  
        * Uninformed delegators don't delegate  
        * Uninformed BReps don't vote
        * Delegators know in advance, before delegation, how BReps voted and why
        * BReps must explain their reasoning on every proposal
        * A body of literature remains (the solicitations) so future generations will understand how we came to our decisions and what they should consider before making changes
        * BReps can remain anonymous, building reputations only on their body of solicitations which all have the same signature.  
      * In bee democracy there is a race to consensus which prevents a market for delegation from emerging - Bees can't sell their delegation 
        * A race to consensus is not possible in Cardano democracy because too many votes or delegations in a short amount of time will jam the system
        * So other methods must be employed to make delegation of ADA more costly to buy then simply buying ADA at market rate.  
          * Block the ability to read the total amount of ADA delegated to a BRep's solicitation while voting is in progress.  
            * This makes it impossible to calculate the ADA tally until the election is over
            * This will help prevent a delegation market from emerging during an election by making it difficult to determine how much ADA delegation is required to pass a proposal  
            * This may necessitate voting on a sidechain which has the required properties 
          * Block the ability of anyone except the delegator from seeing to which solicitation an individual has delegated   
            * This will help prevent a delegation market from emerging during an election by making it difficult to determine the how much ADA is needed to pass a proposal
            * Prevents a delegation market from forming because it would not be easy (cost effective) for BReps to know where to send ADA in exchange for delegation after the election  
            * Prevents automating a delegation market with smart contracts
            * Allows proof that an election is not rigged  
            * Protects delegator from reprisal by current a regime  
            * This may necessitate voting on a sidechain which has the required properties 
      * CC, BRep, and SPO votes to remain transparent by virtue of the solicitation process which forces all to explain their votes and leave a body of information so that future generations will understand why those decisions were made
      * Code to enforce that BReps commit their vote in a signed solicitation for delegation prior to tally with no ability to change the vote which gives delegators sufficient time to verify that BReps are voting as expected and gives delegators time to read and understand the solicitations prior to delegation
      * Code to enforce that delegation of ADA to a solicitation must come from a wallet and never from a smart contract
        * This is to prevent trustless renting of ADA via smart contract for use as delegation in an election
        * In other words to rent out ADA for use as delegation, the renter will be forced to give up custody
      * Provide a forum (perhaps right here) for all BRep solicitations for delegation.  

**Dealing With Low Delegator Participation Which Blocks Governance Action**  
  * It is essential for the security of the Cardano blockchain that delegators (the regular folks) participate in elections. Otherwise whales and exchanges will be winning all the governance actions and will manipulate Cardano government for their advantage with little or no consideration for the unbanked individuals that Cardano was built to serve. It is assumed that the big investors will always delegate their ADA to any solicitation which best advances their goals. Since it can be estimated how much ADA is held by big investors, a delegation threshold parameter is coded into the system to ensure that a significant amount of ADA (well above what the big investors hold) is delegated to the solicitations. This is the only way to know for sure that the little people are delegating too. If delegation to the solicitations does not meet the threshold when votes are tallied then the proposal is dismissed and no action is taken. So a mechanism which is meant to protect small investors will have the unintended consequence of blocking all governance if small investors are not interested enough to delegate their ADA in order to settle the matter. There is a way to proceed with governance if a proposal suffers from low delegator participation
    * Putting A Proposal On Trial
      * If an election does not meet the threshold for delegator participation then the proposal goes to trial. 
      * Jurors are randomly selected from the pool of BReps in an amount equal to the number of Constitutional committee members. Their identities are not required - they can remain anonymous. All that is required is that they have submitted perhaps 10 solicitations in the past. If they can provide the same signature that is on their past solicitations, that is all which is needed to establish them as community members and to judge their character and reputation.
      * In an online meeting (audio only - no video), each juror is questioned by BReps from both sides of the proposal to determine that they are willing to examine both sides of the issue and have the time to do so.
      * Jurors are then asked to read the solicitations. 
      * The next day there is a group online discussion with BReps from both sides of the proposal presenting to the jurors
      * Finally, the jurors vote on the proposal using the same signature they have been using to sign their past solicitations

**Conclusion:** 
* The process of evolution has solved many engineering problems . Perhaps we should take a look at how nature to implements democracy. Bees don’t use their DReps to make decisions for the group. Bees use DReps as scouts. Bees use DReps to collect information and broadcast it to the group. Then all of them decide together. The Cardano protocol was built on peer reviewed science. Our community should look at peer reviewed science on how decision making has evolved in nature and apply what we can to Cardano governance.


### #13: IGCO - initial governance coin offering
  * offering voters a token of unknown value by a representative to acquire delegators
  * including tokens other than Ada

**Recommendation:**

### #14: Powerful Voter Collusion
  * demotivates smaller bag holders
  * cause a loss of participation
  * too many voters abstain
  * minority controls the outcome
  * can push through any proposal

**Recommendation:**

### #15: Persistence - Removal of proposals by attackers.

Recommendation:

### #16: Risk of Proposal overload - Risk of DDOS.

**Recommendation:**

### #17: Excessive actions.
  * Drawing too much money
  * Changing parameters that break the chain (block size=0 for example)
  * overlapping actions and duplicate actions

**Recommendation:**

### #18: Lack of technical understanding by DReps.
Education of correct procedures for DReps

**Recommendation:**

### #19: Sybil behavior - one person acting as multiple DReps.

**Recommendation:**

### #20: Overpower Risk - One DRep or entity with too much power.

**Recommendation:**

### #21: Superstar attack - one “superstar” person that everybody delegates to becomes a dictator with little skin in the game.
(Example: Elon Musk as a DRep)

### #22: High chain load impacting governance.

**Recommendation:**

### #23: Unknown external regulation risks - affecting a specific DRep by country or affecting governance as a whole.

**Recommendation:**

### #24: Blocking a Constitutional Committee revote after a vote of “no confidence”.


**Recommendation:**

### #25: Ensuring the legitimacy of side chains involved in governance.

**Recommendation:**

### #26: Governance capture by a Layer 2.
* Could be enough Ada dedicated to a Hydra head, how does that Ada weight get accounted for in L1 governance?
* This may or may not be an issue for Cardano L2 or Hydra heads. Needs more analysis from experts.

**Recommendation:**


## Use Cases

Use cases need to be fleshed out. Need more inputs here as each use case would apply to each prolem listed above. Seems like both the CIP and CPS formats is not a good fit for this document.


## Goals

The intent of this CPS is to promote awareness of governance security vulnerabilities and possible mitigation techniques in the Cardano ecosystem. The goal is to provide a comprehensive guide describing all known governance security threats and possible mitigiations techniques, but not to address specific software vulnerabilities. The governance security need is present regardless of the final form of CIP-1694 or any other governance document to minimize malicious activities that may occur within a system of voting, holding elections, and/or on-chain approval of automated actions are present.

## Open Questions

Proposed solutions should strive to address the questions outlined within [Problem](#problem).
