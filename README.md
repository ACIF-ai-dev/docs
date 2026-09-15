# tobuilder docs

`docs.tobuilder.io` 가 서빙하는 Mintlify 소스.

## 🔴 이 저장소는 정본이 아니다

정본은 **`ACIF-ai-dev/tobuilder-backend` 의 `docs/api/`** 다. 이 저장소의 파일은 그 디렉터리의 **복사본**이고,
`openapi.json` 은 백엔드가 **코드에서 생성**한다(`npm run docs:openapi:generate`).

⇒ **여기서 직접 고치지 마라.** 고치면 다음 동기화에서 덮이고, 그 사이 백엔드 CI 는 아무것도 못 잡는다.

## 동기화 (지금은 수동)

```bash
cp <tobuilder-backend>/docs/api/{docs.json,openapi.json,index.mdx,sdk-guide.mdx,webhooks.mdx} .
mint validate    # 푸시 전에 반드시 — 이 저장소는 공개이고 Mintlify 가 바로 배포한다
```

🔴 **자동화되어 있지 않다.** 백엔드에서 스펙이 바뀌어도 여기는 안 따라오고 **아무것도 빨개지지 않는다**
(백엔드 `docs:openapi:check` 는 백엔드 안의 드리프트만 잡는다). 자동화는 백엔드 큐 `DOC-7`.

## 마지막 동기화 시점

- 백엔드 `origin/main` = **`92f3528`**
- `openapi.json` sha256 = `35015a20454d31d3b16d83627b00afd380b94f3d4949da82659d3b7065c51eb7`
- 드리프트 확인: 위 sha256 을 백엔드 `docs/api/openapi.json` 의 것과 대조한다

## 🔴 여기 넣으면 안 되는 것

이 저장소는 **공개**다. `/v1/console` 연산은 **내부 표면**이고 이 스펙에 **0건**이어야 한다.
백엔드 루트의 `openapi.json`(콘솔 포함)을 여기로 복사하지 마라 — 복사할 것은 `docs/api/openapi.json` 하나다.

확인:
```bash
python3 -c 'import json;d=json.load(open("openapi.json"));print(sum(1 for p in d["paths"] if p.startswith("/v1/console")))'
# 0 이어야 한다
```
