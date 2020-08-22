# Writing good CL descriptions


CL description은 **어떤** 변화가 생겼고, **왜** 생겼는지에 대한 공개기록입니다.
이는 version control 기록에 영구적으로 남을 부분이며,  
그리고, 리뷰어 이외에도 이후 몇년에 걸쳐 수백명의 사람들에게 읽혀질 수 있습니다.

A CL description is a public record of **what** change is being made and **why**
it was made. It will become a permanent part of our version control history, and
will possibly be read by hundreds of people other than your reviewers over the
years.

미래 개발자들은 description을 토대로 여러분의 CL을 검색할 것 입니다.
미래에 누군가는 구체적인 목표 없이 관련성에 대한 희미한 기억 때문에 여러분의 변경을 찾아볼 수 있습니다. (??)
만약 모든 중요한 정보가 description이 아닌 코드에 있다면, CL을 찾는 것이 무척 어려울 것 입니다. 

Future developers will search for your CL based on its description. Someone in
the future might be looking for your change because of a faint memory of its
relevance but without the specifics handy. If all the important information is
in the code and not the description, it's going to be a lot harder for them to
locate your CL.

## First Line {#firstline}

* 무엇을 했는지에 대한 짧은 요약
* 명령문으로 된 완전한 문장
* ???

*   Short summary of what is being done.
*   Complete sentence, written as though it was an order.
*   Follow by empty line.


CL description의 **첫 줄**은 반드시 *CL에서 구체적으로* **어떤** *것을 했는지*에 대한 짧은 요약이어야 합니다.
이것은 Version control 기록의 요약에 나오기 때문에, 이후 코드를 검색하는 사람들이 여러분의 CL이나 모든 description을 읽지 않고도 이 CL이 실제로 어떤 것을 **했는지** 또는 다른 CL들과 무엇이 다른지를 알수있을정도로 유익해야합니다.
즉, 첫 줄은 반드시 독립적이고(stand-alone), 독자들이 빠르게 코드기록을 훑을 수 있게끔 해야합니다.


The **first line** of a CL description should be a short summary of
*specifically* **what** *is being done by the CL*, followed by a blank line.
This is what appears in version control history summaries, so it should be
informative enough that future code searchers don't have to read your CL or its
whole description to understand what your CL actually *did* or how it differs
from other CLs. That is, the first line should stand alone, allowing readers to
skim through code history much faster.

여러분의 첫 줄이 짧고, 집중적이며 요점을 말하도록 노력하세요.
독자의 명확함과 유용함이 최우선 관심사여야합니다.

Try to keep your first line short, focused, and to the point. The clarity and
utility to the reader should be the top concern.

전통적으로, CL description의 첫 줄은 완전한 문장이고, 명령인 것 마냥 (명령문) 쓰여야합니다.
예를 들어서, 
"**Deleting** the FizzBuzz RPC and **replacing** it with the new system" 라고 쓰는 대신에,
"**Delete** the FizzBuzz RPC and **replace** it with the new system." 이라고 쓰세요. 
그러나, 나머지 description은 명령문으로 쓸 필요는 없습니다.

By tradition, the first line of a CL description is a complete sentence, written
as though it were an order (an imperative sentence). For example, say
\"**Delete** the FizzBuzz RPC and **replace** it with the new system." instead
of \"**Deleting** the FizzBuzz RPC and **replacing** it with the new system."
You don't have to write the rest of the description as an imperative sentence,
though.

## Body is Informative {#informative}

나머지 description은 반드시 유익해야합니다. 
해결한 문제에 대한 간략한 설명이나, 왜 그것이 최선의 접근법이였는지를 포함할 수 있습니다.
만약 접근법에 결점이 있다면, 그것들도 반드시 언급되어야 합니다.
관련있는 버그 번호(bug numbers)나 벤치마크 결과, 디자인 문서 링크들과 같은 배경정보도 포함하세요.

The rest of the description should be informative. It might include a brief
description of the problem that's being solved, and why this is the best
approach. If there are any shortcomings to the approach, they should be
mentioned. If relevant, include background information such as bug numbers,
benchmark results, and links to design documents.

만약 외부 리소스에 대한 링크를 포함할 것이라면, 미래 독자들에게 접근제한이나 보관정책들로 인해서 링크가 보이지 않을 수 있다는 것도 고려하세요.
가능하다면 충분한 컨텍스트를 리뷰어와 미래 독자들의 CL에 대한 이해를 위해 포함하세요. 

If you include links to external resources consider that they may not be visible
to future readers due to access restrictions or retention policies. Where
possible include enough context for reviewers and future readers to understand
the CL.

또한 작은 CL들도 디테일에 약간 관심을 기울일 필요가 있습니다. 컨텍스트에 CL을 넣으세요.

Even small CLs deserve a little attention to detail. Put the CL in context.

## Bad CL Descriptions {#bad}

"Fix bug"는 부적절한 CL description입니다. 무슨 버그지? 고치기 위해서 무엇을 했어?
비슷하게 나쁜 다른 description들은 다음을 포함합니다:
- "Fix build."
- "Add patch."
- "Moving code from A to B."
- "Phase 1."
- "Add convenience functions."
- "kill weird URLs."

몇몇은 실제 CL descrption입니다. 비록 짧지만, 충분히 쓸만한 정보를 주진 않습니다.

"Fix bug" is an inadequate CL description. What bug? What did you do to fix it?
Other similarly bad descriptions include:

-   "Fix build."
-   "Add patch."
-   "Moving code from A to B."
-   "Phase 1."
-   "Add convenience functions."
-   "kill weird URLs."

Some of those are real CL descriptions. Although short, they do not provide
enough useful information.

## Good CL Descriptions {#good}

다음은 좋은 descriptions의 예시들입니다.

Here are some examples of good descriptions.

### Functionality change

Example:

> rpc: remove size limit on RPC server message freelist.
>
> Servers like FizzBuzz have very large messages and would benefit from reuse.
> Make the freelist larger, and add a goroutine that frees the freelist entries
> slowly over time, so that idle servers eventually release all freelist
> entries.

첫 몇 단어는 실제로 CL이 한 것을 설명합니다.
나머지 description은 문제가 해결되었고, 왜 이것이 좋은 해결책인지 그리고 구체적인 구현에 대한 약간의 정보에 대해서 이야기합니다.

The first few words describe what the CL actually does. The rest of the
description talks about the problem being solved, why this is a good solution,
and a bit more information about the specific implementation.

### Refactoring

Example:

> Construct a Task with a TimeKeeper to use its TimeStr and Now methods.
>
> Add a Now method to Task, so the borglet() getter method can be removed (which
> was only used by OOMCandidate to call borglet's Now method). This replaces the
> methods on Borglet that delegate to a TimeKeeper.
>
> Allowing Tasks to supply Now is a step toward eliminating the dependency on
> Borglet. Eventually, collaborators that depend on getting Now from the Task
> should be changed to use a TimeKeeper directly, but this has been an
> accommodation to refactoring in small steps.
>
> Continuing the long-range goal of refactoring the Borglet Hierarchy.

첫 줄에서 CL이 어떤 것을 했고, 과거와 어떻게 다른지 설명합니다.
(??)
또한 *왜* 이런 변경을 했는지에 대한 설명을 했습니다.

The first line describes what the CL does and how this is a change from the
past. The rest of the description talks about the specific implementation, the
context of the CL, that the solution isn't ideal, and possible future direction.
It also explains *why* this change is being made.

### Small CL that needs some context

Example:

> Create a Python3 build rule for status.py.
>
> This allows consumers who are already using this as in Python3 to depend on a
> rule that is next to the original status build rule instead of somewhere in
> their own tree. It encourages new consumers to use Python3 if they can,
> instead of Python2, and significantly simplifies some automated build file
> refactoring tools being worked on currently.

The first sentence describes what's actually being done. The rest of the
description explains *why* the change is being made and gives the reviewer a lot
of context.

## Generated CL descriptions

어떤 CL들은 tools로 생성됩니다(generated by tools).
언제라도 가능하다면, 그 CL들의 descriptions도 역시 이 조언들을 따라야 합니다.
첫 줄은 반드시 짧고, 집중적이고, 독립적이며 CL description body는 반드시 리뷰어나 미래에 코드를 검색할 사람들이 각 CL의 영향을 이해하는 것을 돕는 유익한 세부사항을 포함해야합니다. 

Some CLs are generated by tools. Whenever possible, their descriptions should
also follow the advice here. That is, their first line should be short, focused,
and stand alone, and the CL description body should include informative details
that help reviewers and future code searchers understand each CL's effect.

## Review the description before submitting the CL

CL은 리뷰 중에 큰 변경을 겪을 수 있습니다.
Description이 CL이 하는 것을 여전히 잘 반영하는지, CL을 submit하기 전에 CL description을 검토할 가치가 있습니다.

CLs can undergo significant change during review. It can be worthwhile to review
a CL description before submitting the CL, to ensure that the description still
reflects what the CL does.

Next: [Small CLs](small-cls.md)
