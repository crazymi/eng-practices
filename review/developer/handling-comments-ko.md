# How to handle reviewer comments

여러분들이 리뷰를 위해 CL을 보내왔다면,  리뷰어들은 여러분의 CL에 여러 코멘트로 대답했을 것 입니다.
여기 리뷰어의 코멘트를 다루기 위해 알아야할 몇가지 유용한 것들이 있습니다.

When you've sent a CL out for review, it's likely that your reviewer will
respond with several comments on your CL. Here are some useful things to know
about handling reviewer comments.

## Don't Take it Personally {#personal}

리뷰의 목적은 우리의 코드베이스의 퀄리티와 제품을 유지하기 위해서입니다.
리뷰어가 여러분의 코드에 대한 비평을 줄 때,
여러분이나 여러분의 능력에 대한 개인적인 공격이 아닌, 
여러분, 코드베이스 그리고 구글을 돕기 위한 그들의 노력으로 생각하세요. 

The goal of review is to maintain the quality of our codebase and our products.
When a reviewer provides a critique of your code, think of it as their attempt
to help you, the codebase, and Google, rather than as a personal attack on you
or your abilities.

때로 리뷰어는 불만을 느끼고 코멘트에 불만을 표현하기도 합니다.
이 것은 리뷰어에겐 좋은 관행이 아니지만, 개발자로써 여러분은 이 것에 준비해야합니다.
스스로에게 "리뷰어가 나와 소통하려 노력하는 건설적인 것이 무엇일까?"라고 물어보고,
실제로 리뷰어가 말한 것처럼 작용하세요.

Sometimes reviewers feel frustrated and they express that frustration in their
comments. This isn't a good practice for reviewers, but as a developer you
should be prepared for this. Ask yourself, "What is the constructive thing that
the reviewer is trying to communicate to me?" and then operate as though that's
what they actually said.

**절대로 코드리뷰 코멘트에 화난 채로 대답하지마세요**
그건 코드 리뷰 툴에 영원히 남아있을, 직업상 예절에 대한 심각한 위반입니다.
여러분이 친절하게 대답하기에 너무 화나거나 짜증난다면, 
정중하게 답할 수 있을 정도로 충분히 진정되기 전까지,
잠깐 컴퓨터 곁을 떠나거나 다른 무언가를 작업하세요.

**Never respond in anger to code review comments.** That is a serious breach of
professional etiquette that will live forever in the code review tool. If you
are too angry or annoyed to respond kindly, then walk away from your computer
for a while, or work on something else until you feel calm enough to reply
politely.

일반적으로 만일 리뷰어가 건설적이고 정중한 피드백을 주지 않는다면,
그들에게 직접 대면으로 설명하세요.
직접 혹은 화상으로 말하기 어렵다면, 개인 이메일을 보내세요.
어떤 점이 싫고, 어떻게 다르게 행동했으면 좋겠는지 상냥하게 설명하세요.
만약 리뷰어가 이런 사적인 논의에 대해서 비건설적으로 대응하거나,
논의가 의도한 효과가 없었다면,
적절하게 여러분의 매니저에게 보고(escalate)하세요.

In general, if a reviewer isn't providing feedback in a way that's constructive
and polite, explain this to them in person. If you can't talk to them in person
or on a video call, then send them a private email. Explain to them in a kind
way what you don't like and what you'd like them to do differently. If they also
respond in a non-constructive way to this private discussion, or it doesn't have
the intended effect, then
escalate to your manager as
appropriate.

## Fix the Code {#code}

만약 리뷰어가 여러분의 코드의 어떤 것을 이해하지 못한다고 말하면,
먼저 대답해야할 것은 코드 자체를 명확하게 하는 것 입니다.
만일 코드를 명확하게 하기 어렵다면, 왜 코드가 그 곳에 있어야하는지에 대한 주석을 추가하세요.
주석이 무의미해보이는 경우에만, 코드리뷰 툴에서 설명합니다.

If a reviewer says that they don't understand something in your code, your first
response should be to clarify the code itself. If the code can't be clarified,
add a code comment that explains why the code is there. If a comment seems
pointless, only then should your response be an explanation in the code review
tool.

만약 리뷰어가 여러분의 어떤 코드조각을 이해하지 못했다면,
그 코드를 읽을 미래의 독자들 또한 이해하지 못할 가능성이 있습니다.
코드리뷰 툴에 대답을 적는 건 미래 독자들에게 도움이 안되나,
코드를 명확하게 하거나 주석을 추가하는 건 그들에게 도움이 됩니다.

If a reviewer didn't understand some piece of your code, it's likely other
future readers of the code won't understand either. Writing a response in the
code review tool doesn't help future code readers, but clarifying your code or
adding code comments does help them.

## Think for Yourself {#think}

CL을 작성하는 건 많은 노력이 들어갈 수 있습니다.
보통은 최종적으로 CL을 리뷰를 위해 보내는 것은 정말 만족스럽고
마치 다 끝난 것처럼 느껴지고,
더 이상 추가적인 작업이 필요없을 것 같은 확신이 듭니다.
그렇기 때문에 리뷰어가 개선될만한 코멘트를 가지고 왔을 때,
반사적으로 코멘트가 틀렸다거나,
리뷰어가 여러분을 불필요하게 방해하고 있거나,
그냥 CL을 제출하도록 해야한다고 생각하기 쉽습니다.
그러나, 여기서 **여러분이 아무리 확신하더라도** 잠시 한발짝 뒤로 물러서고
리뷰어가 코드베이스와 Google에 도움이 될 가치있는 피드백을 주는지 숙고할 시간을 가지세요.
스스로에게 물어볼 첫 질문은 "리뷰어가 옳은가?" 입니다.

Writing a CL can take a lot of work. It's often really satisfying to finally
send one out for review, feel like it's done, and be pretty sure that no further
work is needed. So when a reviewer comes back with comments on things that could
be improved, it's easy to reflexively think the comments are wrong, the reviewer
is blocking you unnecessarily, or they should just let you submit the CL.
However, **no matter how certain you are** at this point, take a moment to step
back and consider if the reviewer is providing valuable feedback that will help
the codebase and Google. Your first question to yourself should always be, "Is
the reviewer correct?"

만약 이 질문에 답할 수 없다면, 리뷰어가 코멘트를 명확히 해야할 가능성이 높습니다.

If you can't answer that question, it's likely the reviewer needs to clarify
their comments.

만약 여러분이 숙고*했고* 여전히 여러분이 맞다고 생각된다면,
마음껏 왜 여러분의 수행 방법이 코드베이스, 유저, 그리고/또는 구글에게 더 나은지 설명하세요.
흔히 리뷰어는 사실 *제안*을 하고, 여러분이 스스로 어떤 것이 최선일지 생각하기를 원합니다.
아마도 리뷰어가 모르는 유저, 코드베이스 또는 CL에 관해 여러분은 사실 무언가를 알고있습니다.
그러니 채우세요; 더 많은 맥락을 제공하세요.
대개는 기술적인 사실에 기반해서 여러분 자신과 리뷰어간의 합의에 도달할 수도 있습니다.

If you *have* considered it and you still think you're right, feel free to
respond with an explanation of why your method of doing things is better for the
codebase, users, and/or Google. Often, reviewers are actually providing
*suggestions* and they want you to think for yourself about what's best. You
might actually know something about the users, codebase, or CL that the reviewer
doesn't know. So fill them in; give them more context. Usually you can come to
some consensus between yourself and the reviewer based on technical facts.

## Resolving Conflicts {#conflicts}

갈등을 해결하는 첫 단계는 항상 리뷰어와의 합의에 도달하는 것입니다.
만약 합의에 도달할 수 없다면, 이런 상황에서 따라야할 원칙을 제공하는 
[The Standard of Code Review](../reviewer/standard.md)을 보세요.

Your first step in resolving conflicts should always be to try to come to
consensus with your reviewer. If you can't achieve consensus, see
[The Standard of Code Review](../reviewer/standard.md), which gives principles
to follow in such a situation.
