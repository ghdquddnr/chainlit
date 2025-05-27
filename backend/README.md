<h1 align="center">Literal AI의 Chainlit에 오신 것을 환영합니다 👋</h1>

<p align="center">
<b>몇 주가 아닌 몇 분 만에 Python 기반의 프로덕션급 대화형 AI 애플리케이션을 구축하세요 ⚡️</b>

</p>
<p align="center">
    <a href="https://discord.gg/k73SQ3FyUh" rel="nofollow"><img alt="Discord" src="https://dcbadge.vercel.app/api/server/ZThrUxbAYw?style=flat" style="max-width:100%;"></a>
    <a href="https://twitter.com/chainlit_io" rel="nofollow"><img alt="Twitter" src="https://img.shields.io/twitter/url/https/twitter.com/chainlit_io.svg?style=social&label=Follow%20%40chainlit_io" style="max-width:100%;"></a>
    <a href="https://pypistats.org/packages/chainlit" rel="nofollow"><img alt="Downloads" src="https://img.shields.io/pypi/dm/chainlit" style="max-width:100%;"></a>
        <a href="https://github.com/chainlit/chainlit/graphs/contributors" rel="nofollow"><img alt="Contributors" src="https://img.shields.io/github/contributors/chainlit/chainlit" style="max-width:100%;"></a>
    <a href="https://github.com/Chainlit/chainlit/actions/workflows/ci.yaml" rel="nofollow"><img alt="CI" src="https://github.com/Chainlit/chainlit/actions/workflows/ci.yaml/badge.svg" style="max-width:100%;"></a>
</p>

<p align="center">
    <a href="https://chainlit.io"><b>웹사이트</b></a>  •  
    <a href="https://docs.chainlit.io"><b>문서</b></a>  •  
    <a href="https://help.chainlit.io"><b>Chainlit 도움말</b></a>  •  
    <a href="https://github.com/Chainlit/cookbook"><b>Cookbook</b></a>
</p>

<p align="center">
    <a href="https://trendshift.io/repositories/6708" target="_blank"><img src="https://trendshift.io/api/badge/repositories/6708" alt="Chainlit%2Fchainlit | Trendshift" style="width: 250px; height: 45px;" width="250" height="45"/></a>
</p>

https://github.com/user-attachments/assets/b3738aba-55c0-42fa-ac00-6efd1ee0d148

> [!NOTE]
> Chainlit은 [Literal AI](https://literalai.com)에서 관리하는 LLMOps 플랫폼으로, LLM 애플리케이션을 모니터링하고 평가할 수 있습니다! Python 또는 TypeScript 애플리케이션과 호환되며, Chainlit과 [매우 쉽게 연동](https://docs.chainlit.io/llmops/literalai)할 수 있습니다. 엔터프라이즈 지원이 필요하다면 [이 양식](https://docs.google.com/forms/d/e/1FAIpQLSdPVGqfuaWSC2DfunR6cY4C7kUHl0c2W7DnhzsF9bmMxrVpkg/viewform?usp=header)을 작성해 주세요.

## 설치 방법

터미널을 열고 아래 명령어를 실행하세요:

```sh
pip install chainlit
chainlit hello
```

`hello app`이 브라우저에서 열리면 설치가 완료된 것입니다!

### 개발 버전 설치

최신 개발 버전은 GitHub에서 바로 설치할 수 있습니다:

```sh
pip install git+https://github.com/Chainlit/chainlit.git#subdirectory=backend/
```

(설치 전 Node와 pnpm이 시스템에 설치되어 있어야 합니다.)

## 🚀 빠른 시작

### 🐍 순수 Python 예제

아래와 같이 `demo.py` 파일을 새로 만드세요:

```python
import chainlit as cl


@cl.step(type="tool")
async def tool():
    # 예시 도구
    await cl.sleep(2)
    return "도구에서 반환된 응답!"


@cl.on_message  # 사용자가 UI에 메시지를 입력할 때마다 호출됩니다.
async def main(message: cl.Message):
    """
    이 함수는 사용자가 UI에 메시지를 입력할 때마다 호출됩니다.
    도구의 중간 응답과 최종 답변을 순차적으로 보냅니다.

    Args:
        message: 사용자의 메시지

    Returns:
        없음
    """

    # 도구 호출
    tool_res = await tool()

    await cl.Message(content=tool_res).send()
```

이제 실행해보세요!

```sh
chainlit run demo.py -w
```

<img src="/images/quick-start.png" alt="빠른 시작"></img>

## 📚 더 많은 예제 - Cookbook

OpenAI, Anthropic, LangChain, LlamaIndex, ChromaDB, Pinecone 등 다양한 도구와 서비스를 활용한 Chainlit 앱 예제는 [여기](https://github.com/Chainlit/cookbook)에서 확인할 수 있습니다.

Chainlit에 추가되었으면 하는 기능이나 예제가 있다면 Github 이슈 또는 [Discord](https://discord.gg/k73SQ3FyUh)에서 의견을 남겨주세요.

## 💁 기여하기

Chainlit은 빠르게 발전하는 오픈소스 프로젝트로, 새로운 기능 추가나 문서 개선 등 다양한 기여를 환영합니다.

기여 방법에 대한 자세한 내용은 [여기](/CONTRIBUTING.md)를 참고하세요.

## 📃 라이선스

Chainlit은 오픈소스이며 [Apache 2.0](LICENSE) 라이선스를 따릅니다.

---

원문은 Chainlit 공식 저장소에서 확인하실 수 있습니다.
