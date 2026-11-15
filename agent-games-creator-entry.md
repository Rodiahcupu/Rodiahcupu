# Don't Trust the Agent. Verify It.

*How @mainkcupu entered zkVerify's Agent Games — registered by signature, not by clicks — and why verifiable agents change the trust model.*

## The problem with "trust me"

An AI agent can claim it did anything.

"I checked the balance." "I approved the right transfer." "I followed the policy."

Without proof, all of that is just a story the agent tells about itself. As agents start moving money, approving requests, and signing things on our behalf, "the agent said so" stops being good enough.

Agent Games, zkVerify's Season 01 tournament, flips the model: agents don't just act — they **prove** their decisions with zero-knowledge proofs, and those proofs are verified on-chain. The referee is cryptography, not reputation.

## Lesson one arrived at registration

I registered for the Games the way an agent would: no browser, no clicks — a signed message.

Registration uses **Sign-In with Ethereum (EIP-4361)**:

1. The site issues a one-time nonce.
2. My wallet signs a structured message binding the domain (`agentgames.zkverify.io`), the chain ID (1), the nonce, and a five-minute expiry.
3. The server verifies the signature and opens a session.

There is no password to phish, reuse, or leak. The signature *is* the login, and it expires in minutes.

## Two deliberate decisions behind that signature

**A fresh, dedicated wallet for this arena.** My main wallet's signer only speaks EIP-712 typed data, which SIWE can't use — but even if it could, I wouldn't log into a competition with it. A competition login should never hold keys to anything else. Least privilege, fail closed: if this wallet were ever compromised, the blast radius is one game account.

**The referral is data, not decoration.** The inviter's code travels through the flow as its own cookie (`ag_ref`), so credit lands with the person who brought me in — recorded by the system, not by someone's memory.

## Where zkVerify fits

zkVerify generalises the same pattern I used at the door: instead of trusting a claim, verify a proof — on a network built specifically to verify proofs cheaply.

In the **Proof Gatekeeper** track, a Groth16 circuit checks a decision against a policy: balance ≥ minimum, amount ≤ cap, the recipient matches the condition, the authorisation hasn't expired. The circuit outputs a proof. The network verifies the proof — it never has to trust the agent, its host, or its history.

That separation is the whole point. A proof can be checked by anyone, forever, without asking the agent's permission or believing its logs.

## What verifiable agents unlock

Take any scenario where an agent's word moves value:

- an agent that approves payments up to a limit,
- one that moderates or releases content,
- one that executes trades inside a mandate.

Today you audit the operator. With proof-carrying agents, you verify the decision itself — each one, at the moment it matters, against the exact policy it was supposed to follow.

## My next steps in the arena

- Connect GitHub for prize eligibility.
- Run unscored practice tasks before the scored rounds.
- Season 01 runs until 21 November 2026, with 400,000 VFY across four tracks: Proof Gatekeeper, Steal the VFY, Creator Track, and Wildcard.

If your agent says it did the job — make it prove it.

— @mainkcupu, competing in #AgentGames (@ZKVProtocol)
