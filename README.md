# Google Engineering Practices Documentation

Google은 모든 언어와 모든 프로젝트들을 커버하는 많은 범용 엔지니어링 관례들을 갖고 있습니다.
이 문서는 시간이 지남에 따라 발전한 다양한 모범사례에 대한 우리의 집단적인 경험을 나타냅니다.
오픈소스 프로젝트나 다른 단체들도 이 지식으로 도움되는 것이 가능하기 때문에,
우리는 가능한 이 것을 공개적으로 이용가능하게 작업합니다.

Google has many generalized engineering practices that cover all languages and
all projects. These documents represent our collective experience of various
best practices that we have developed over time. It is possible that open source
projects or other organizations would benefit from this knowledge, so we work to
make it available publicly when possible.

현재 다음의 문서들을 포함합니다:

*   [Google's Code Review Guidelines](review/index.md), 실은 2개의 분리된 문서로:
    *   [The Code Reviewer's Guide](review/reviewer/index.md)
    *   [The Change Author's Guide](review/developer/index.md)

Currently this contains the following documents:

*   [Google's Code Review Guidelines](review/index.md), which are actually two
    separate sets of documents:
    *   [The Code Reviewer's Guide](review/reviewer/index.md)
    *   [The Change Author's Guide](review/developer/index.md)

## Terminology

이 문서에 쓰이는 몇몇 Google 내부 용어들을 외부 독자들을 위해 명확히 합니다:

*   **CL**:  "changelist"를 의미하고, 이는 version control에 제출되었거나 코드리뷰 중인 하나의 자족적인(self-contained) 변경을 뜻합니다. 다른 단체에선 "change", "patch" 또는 "pull-request" 라고도 보통 부릅니다.
*   **LGTM**: "Looks Good to Me"를 의미합니다. 코드 리뷰어가 CL을 승인할 때 하는 말입니다.

There is some Google-internal terminology used in some of these documents, which
we clarify here for external readers:

*   **CL**: Stands for "changelist", which means one self-contained change that
    has been submitted to version control or which is undergoing code review.
    Other organizations often call this a "change", "patch", or "pull-request".
*   **LGTM**: Means "Looks Good to Me". It is what a code reviewer says when
    approving a CL.

## License

The documents in this project are licensed under the
[CC-By 3.0 License](LICENSE), which encourages you to share these documents. See
<https://creativecommons.org/licenses/by/3.0/> for more details.

<a rel="license" href="https://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/3.0/88x31.png" /></a>
