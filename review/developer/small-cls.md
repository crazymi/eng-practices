# Small CLs

## Why Write Small CLs? {#why}

작고, 간단한 CLs은:
- **더 빨리 리뷰된다.** 리뷰어가 하나의 큰 CL을 리뷰하기 위해 30분을 확보하는 것보다, 5분씩 여러번을 확보하는 것이 쉽다.
- **더 철저히 리뷰된다.**
- **덜 버그를 내놓을 것이다.** 여러분이 더 작은 변경을 할수록, 여러분과 리뷰어들은 더 쉽게 CL의 영향에 대해 추리하고 버그가 내놓아 졌는지 찾을 수 있습니다.
- **덜 낭비이다. 거절당해도**  여러분이 거대한 CL을 작성한 뒤에, 리뷰어가 전반적인 방향이 틀렸다고 한다면 여러분은 엄청난 일낭비를 하게됩니다.
- **더 머지가 수월하다.** 큰 CL을 작업하는 것은 오래걸리므로, 머지할 때 많은 conflict이 생길 것이고, 여러분은 더 빈번하게 머지해야할 것 입니다.
- **더 디자인이 수월하다.** 큰 변경의 모든 세부사항을 개선하는 것보다, 작은 변경의 디자인과 코드 건강(code health)를 다듬는 것이 훨씬 쉽습니다.
- **덜 막힌다. 리뷰로 인해** 여러분의 전반적인 변경사항을 구성하는 자족적인 부분(self-contained portions)를 보내는 것은, 여러분이 CL이 리뷰되는 동안 계속 코딩하는 것을 가능케합니다.
- **더 롤백이 간단하다.** 큰 CL은 첫 제출된 CL과 롤백 CL 사이에 업데이트되는 파일들을 건드려 롤백을 복잡하게 만들 가능성이 큽니다. (중간 CL들도 롤백해야할 수도 있기 때문입니다.)

Small, simple CLs are:

-   **Reviewed more quickly.** It's easier for a reviewer to find five minutes
    several times to review small CLs than to set aside a 30 minute block to
    review one large CL.
-   **Reviewed more thoroughly.** With large changes, reviewers and authors tend
    to get frustrated by large volumes of detailed commentary shifting back and
    forth—sometimes to the point where important points get missed or dropped.
-   **Less likely to introduce bugs.** Since you're making fewer changes, it's
    easier for you and your reviewer to reason effectively about the impact of
    the CL and see if a bug has been introduced.
-   **Less wasted work if they are rejected.** If you write a huge CL and then
    your reviewer says that the overall direction is wrong, you've wasted a lot
    of work.
-   **Easier to merge.** Working on a large CL takes a long time, so you will
    have lots of conflicts when you merge, and you will have to merge
    frequently.
-   **Easier to design well.** It's a lot easier to polish the design and code
    health of a small change than it is to refine all the details of a large
    change.
-   **Less blocking on reviews.** Sending self-contained portions of your
    overall change allows you to continue coding while you wait for your current
    CL in review.
-   **Simpler to roll back.** A large CL will more likely touch files that get
    updated between the initial CL submission and a rollback CL, complicating
    the rollback (the intermediate CLs will probably need to be rolled back
    too).

참고로, **리뷰어는 변경이 너무 크다는 이유만으로도 변경을 거절할 재량이 있습니다.** 
그들은 보통 여러분의 기여(contribution)에 감사하지만, 일련의 작은 변경들로 만들어 줄 것을 요청할 것입니다.
이미 작성된 여러분의 변경을 작게 쪼개는 것은 많은 노력이 들어가고, 또는 왜 리뷰어가 여러분의 큰 변경을 받아들여야하는 지에 대해 논하는 것에 많은 시간이 요구됩니다.
그냥 애당초 작은 CL들을 작성하는 것이 더 쉽습니다.

Note that **reviewers have discretion to reject your change outright for the
sole reason of it being too large.** Usually they will thank you for your
contribution but request that you somehow make it into a series of smaller
changes. It can be a lot of work to split up a change after you've already
written it, or require lots of time arguing about why the reviewer should accept
your large change. It's easier to just write small CLs in the first place.

## What is Small? {#what_is_small}

일반적으로, CL의 올바른 크기는 **하나의 자족적인 변경** (**one self-contained change**)입니다. 이 것의 의미는:

- **단 하나만**을 해결하는 최소한의 변경을 만드는 CL입니다. 보통 이는 한 번에 모든 기능이기 보다는, 그저 기능의 한 부분입니다. 일반적으로 너무 거대한 CL을 작성하느니, 지나치게 작은 CL들을 작성하는 것이 더 좋습니다. 여러분의 리뷰어와 함께 받아들일만한 크기를 찾아보세요.
- CL은 반드시 [관련된 테스트 코드를 포함](#test_code)해야합니다.
- 리뷰어가 (미래 개발을 제외하고) CL에 대해 이해해야할 것은 CL description, 기존에 존재하는 코드베이스 또는 이미 리뷰했던 CL이 전부입니다.
- CL이 체크인된 이후, 시스템은 유저와 개발자에게 계속 잘 동작해야합니다.
- CL은 그 함축이 이해하기 어려울 정도로 작지 않습니다. 만약 여러분이 새로운 API를 추가한다면, 리뷰어들이 어떻게 API가 사용될지 잘 이해할 수 있도록 API의 용법(usage)를 포함해야합니다. 이는 또한 사용되지 않는 API들이 체크인되는 것을 방지합니다. 

In general, the right size for a CL is **one self-contained change**. This means
that:

-   The CL makes a minimal change that addresses **just one thing**. This is
    usually just one part of a feature, rather than a whole feature at once. In
    general it's better to err on the side of writing CLs that are too small vs.
    CLs that are too large. Work with your reviewer to find out what an
    acceptable size is.
-   The CL should [include related test code](#test_code).
-   Everything the reviewer needs to understand about the CL (except future
    development) is in the CL, the CL's description, the existing codebase, or a
    CL they've already reviewed.
-   The system will continue to work well for its users and for the developers
    after the CL is checked in.
-   The CL is not so small that its implications are difficult to understand. If
    you add a new API, you should include a usage of the API in the same CL so
    that reviewers can better understand how the API will be used. This also
    prevents checking in unused APIs.

"너무 큰"이 얼마나 큰 지에 대한 엄격한 규칙은 없습니다. 보통 100라인은 적당한 CL의 크기이고, 1000라인은 CL은 보통 너무 큽니다만, 이는 리뷰어의 판단에 달려있습니다.
변경이 분산된 파일 갯수도 "크기"에 영향을 줍니다. 200라인의 변경이 하나의 파일에 있다면 괜찮지만, 50개의 파일에 나누어져 있다면 이건 보통 너무 큰 것입니다.

There are no hard and fast rules about how large is "too large." 100 lines is
usually a reasonable size for a CL, and 1000 lines is usually too large, but
it's up to the judgment of your reviewer. The number of files that a change is
spread across also affects its "size." A 200-line change in one file might be
okay, but spread across 50 files it would usually be too large.

여러분은 코드를 작성한 순간부터 밀접히 코드와 관련되었지만, 리뷰어는 보통 아무런 맥락이 없다는 것을 명심하세요. 여러분에게 그런대로 괜찮아 보이는 크기의 CL도 리뷰어에게는 압도적일 수가 있습니다.
확신이 안서면, 작성해야한다고 생각한 것보다 작게 CL을 작성하세요.
리뷰어는 너무 작은 CL을 받는 것에 대해 거의 불평하지 않습니다.

Keep in mind that although you have been intimately involved with your code from
the moment you started to write it, the reviewer often has no context. What
seems like an acceptably-sized CL to you might be overwhelming to your reviewer.
When in doubt, write CLs that are smaller than you think you need to write.
Reviewers rarely complain about getting CLs that are too small.

## When are Large CLs Okay? {#large_okay}

큰 변경이 나쁘지 않은 상황이 조금 있습니다:
- 파일 하나를 통째로 삭제하는 건 보통 한 줄의 변경으로 세도 됩니다. 리뷰어가 리뷰하는데 오래걸리지 않기 때문입니다.
- 가끔 큰 CL은 여러분들이 전적으로 신뢰하는 자동화된 리팩토링 툴로 생성되어서, 리뷰어의 역할은 단순히 제대로 된지 확인하고 정말 변경을 원하는지 말하는 것입니다. 이러한 CL들은 클 수 있지만, 여전히 앞서 말한 주의점들은(머지나 테스트와 같은) 적용됩니다. 

There are a few situations in which large changes aren't as bad:

-   You can usually count deletion of an entire file as being just one line of
    change, because it doesn't take the reviewer very long to review.
-   Sometimes a large CL has been generated by an automatic refactoring tool
    that you trust completely, and the reviewer's job is just to sanity check
    and say that they really do want the change. These CLs can be larger,
    although some of the caveats from above (such as merging and testing) still
    apply.

### Splitting by Files {#splitting-files}

CL을 나누는 또다른 방법은, 자족적인 변경이지만 서로 다른 리뷰어가 필요한 것들을 그룹으로 나누는 것 입니다.

Another way to split up a CL is by groupings of files that will require
different reviewers but are otherwise self-contained changes.

예를 들어: 여러분은 protocol buffer를 변경하는 한 CL을 보내고, 그 proto를 사용하는 다른 CL을 보냅니다. proto CL을 code CL 이전에 보내야하지만, 둘은 동시에 리뷰되어도 됩니다.
만약 여러분이 이렇게 한다면, 두 리뷰어 집단에 여러분이 작성한 다른 CL을 알려 변경에 대한 맥락을 가지도록 하는 것이 좋습니다.

For example: you send off one CL for modifications to a protocol buffer and
another CL for changes to the code that uses that proto. You have to submit the
proto CL before the code CL, but they can both be reviewed simultaneously. If
you do this, you might want to inform both sets of reviewers about the other CL
that you wrote, so that they have context for your changes.

다른 예시: 하나는 코드 변경에 대한 CL, 다른 하나는 그 코드를 쓰는 설정이나 실험에 대한 변경을 보냅니다;
경우에 따라 설정/실험 파일들은 코드 변경보다 빠르게 production에 push되기 때문에, 이는 필요하다면 롤백하기도 쉽습니다.

Another example: you send one CL for a code change and another for the
configuration or experiment that uses that code; this is easier to roll back
too, if necessary, as configuration/experiment files are sometimes pushed to
production faster than code changes.

## Separate Out Refactorings {#refactoring}

대개 리팩토링은 기능 변경이나 버그 픽스와 분리된 CL에서 하는 것이 제일 좋습니다.
예를 들어, 클래스를 옮기거나 이름을 바꾸는 것은 그 클래스의 버그 픽스와 다른 CL에 속해야합니다.
리뷰어는 각각 CL이 개별적으로 도입한 변경을 이해하는 것이 훨씬 더 쉽습니다.

It's usually best to do refactorings in a separate CL from feature changes or
bug fixes. For example, moving and renaming a class should be in a different CL
from fixing a bug in that class. It is much easier for reviewers to understand
the changes introduced by each CL when they are separate.

그래도 로컬 변수 이름을 픽스하는 등의 작은 청소(cleanups)들은 기능 변경이나 버그 픽스 CL안에 포함되어도 됩니다.
리팩토링이 너무 커서 현재 CL에 포함되었을 때 리뷰가 더 어려워질지는 개발자와 리뷰어들의 결정에 달려있습니다.

Small cleanups such as fixing a local variable name can be included inside of a
feature change or bug fix CL, though. It's up to the judgment of developers and
reviewers to decide when a refactoring is so large that it will make the review
more difficult if included in your current CL.

## Keep related test code in the same CL {#test_code}

CL은 반드시 관련된 테스트 코드를 포함해야합니다.
여기서 [작다는 것](#what_is_small)이 단순한 라인 수에 대한 함수가 아니라,
CL이 집중적이어야한다는 개념적인 아이디어를 나타낸다는 것을 기억하세요.

CLs should include related test code. Remember that [smallness](#what_is_small)
here refers the conceptual idea that the CL should be focused and is not a
simplistic function on line count.

로직을 추가하거나 변경하는 CL은 반드시 새로운 동작에 대한
신규 혹은 업데이트된 테스트를 동반해야합니다.
순수 리팩토링 CL은 (동작을 변경할 의도가 없는) 테스트에 의해 커버되어야한다.
이상적으로 이러한 테스트들은 이미 존재해야하나, 만약 없다면 여러분은 반드시 추가해야한다.

A CL that adds or changes logic should be accompanied by new or updated tests
for the new behavior. Pure refactoring CLs (that aren't intended to change
behavior) should also be covered by tests; ideally, these tests already exist,
but if they don't, you should add them.

_독립적인_ 테스트 수정은 [리팩토링 가이드](#refactoring)와 비슷하게 일단 별도의 CL로 갈 수 있다.
이러한 것들을 포함:

_Independent_ test modifications can go into separate CLs first, similar to the
[refactorings guidelines](#refactoring). That includes:

* 신규 테스트로 이미 제출된 존재하는 코드의 유효성 검사
    * 중요한 로직이 테스트에 의해 커버되는 것을 보장하세요.
    * 영향을 받는 후속 리팩토링에 대한 신뢰도를 올린다. 예를 들어,
        아직 테스트 커버가 안된 코드를 리팩토링하길 원할 때, 
        리팩토링 CL을 제출하기 **이전에** 테스트 CL을 제출하는 것은, 
        테스트된 동작이 리팩토링 전후로 변하지 않음을 입증할 수 있다.
* 테스트 코드를 리팩토링 (e.g. helper 함수를 도입)
* 더 큰 테스트 프레임워크 코드를 도입 (e.g. integration 테스트)


*  Validating pre-existing, submitted code with new tests.
    *   Ensures that important logic is covered by tests.
    *   Increases confidence in subsequent refactorings on affected code. For
        example, if you want to refactor code that isn't already covered by
        tests, submitting test CLs _before_ submitting refactoring CLs can
        validate that the tested behavior is unchanged before and after the
        refactoring.
*   Refactoring the test code (e.g. introduce helper functions).
*   Introducing larger test framework code (e.g. an integration test).

## Don't Break the Build {#break}

서로 의존적인 CL이 여러개라면, 각각 CL이 제출된 이후에도 시스템이 계속 동작할 수 있는 방법을 찾아야한다는 것을 명심하세요.
그게 아니면, 여러분의 CL 제출사이 몇분간 모든 동료 개발자들의 빌드를 깨뜨릴 수 있습니다 (나중에 제출된 CL에 예상치못한 문제가 생기면 훨씬 더 길게)

If you have several CLs that depend on each other, you need to find a way to
make sure the whole system keeps working after each CL is submitted. Otherwise
you might break the build for all your fellow developers for a few minutes
between your CL submissions (or even longer if something goes wrong unexpectedly
with your later CL submissions).

## Can't Make it Small Enough {#cant}

때때로 여러분의 CL이 거대*해야할* 것 같아 보이는 상황을 마주할 것이다.
이는 거의 사실이 아닙니다.
작은 CL들을 작성하도록 훈련한 작성자들은 거의 항상 기능들을 일련의 작은 변경들로 분해하는 방법을 찾을 수 있습니다.

Sometimes you will encounter situations where it seems like your CL *has* to be
large. This is very rarely true. Authors who practice writing small CLs can
almost always find a way to decompose functionality into a series of small
changes.

큰 CL을 작성하기 이전에,
더 깔끔한 구현을 위한 길을 닦을 수 있는 리팩토링뿐인 CL을 앞서할지 검토해보세요.
어떻게 작은 CL들로 대신 기능을 구현할지 팀원들에게 말해서 알아보세요.

Before writing a large CL, consider whether preceding it with a refactoring-only
CL could pave the way for a cleaner implementation. Talk to your teammates and
see if anybody has thoughts on how to implement the functionality in small CLs
instead.

만약 이러한 선택들이 모두 실패한다면 (극도로 드물것이지만),
미리 여러분의 리뷰어들에게 큰 CL을 리뷰에 대한 동의를 얻어서,
무엇이 다가오는지 그들이 미리 경고받게 해주세요.
이런 상황에선, 리뷰과정이 오래걸릴 것이라고 예상하고,
버그를 발생하지 않게 방심하지 말고,
그리고 테스트 작성에 있어 각별히 부지런하세요.

If all of these options fail (which should be extremely rare) then get consent
from your reviewers in advance to review a large CL, so they are warned about
what is coming. In this situation, expect to be going through the review process
for a long time, be vigilant about not introducing bugs, and be extra diligent
about writing tests.

Next: [How to Handle Reviewer Comments](handling-comments.md)
