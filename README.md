# Git Practice

## Article I found interesting

[TDD inside the agent loop - theater or actual value?](https://martinfowler.com/articles/exploring-gen-ai/tdd-in-the-agent-loop.html) by Birgitta Böckeler (martinfowler.com, August 2026)

## Why I found it interesting

Böckeler ran an experiment of giving coding tasks to an agent with/without instructions to follow test-driven development (TDD), and a second model not knowing ranked the results. The TDD runs used roughly 3-8x tokens and ranked slightly worse. Her explanation is the agents without TDD instructions have the whole design first, on the other hand the TDD runs let the design grow out of test order, and behavior didn't get build if there's no test for it.

She furthermore split TDD into the goals of it and check which ones still work when agent run the process. Most of them didn't because when the same agent write, run and report a test, the step checking what went wrong is gone (e.g. one run even compute the "expected" values by calling the implementation itself...). Test first matters because it force a human to think through behavior before writing the code, and AI don't do that.

For Böckeler thinking move into writing the spec, using mutation testing instead of trusting coverage, and freezing test scenarios she confirmed herself. The job is more "decide what correct mean, and build checks that don't grade their own homework." This have made me think maybe switching to the ideas of failing fast is better but ofc there are still constraints around this.
