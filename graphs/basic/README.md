
# Graph 구조

1. LLM A, B, C, D 정의
2. GraphBuilder 정의
3. State 정의
4. Tools 정의
5. Memory 정의
6. 각 LLM 마다 Tools 입력
7. node, edge로 연결
  - node의 실행은 __call__ 로 실행된다.
8. conditional edge로 if elif else 구현 가능
  - tools을 가지고 있는 llm에게 tool을 실행하려면 tools_condition 필수
9. graph 생성 (compile, memory 연결)
10. Config 정의 (session 관리를 위한 id 지정)
11. graph.invoke()

### Debugging을 위해
1. snapshot = graph.get_state(config)
2. snapshot.next - 하나씩 실행해볼 수 있음
3. graph.get_state_history()

### time travel
state에는 checkpoint_id가 있어서 invoke, stream 할 때 특정 단계의 state를 넣어주면 그 곳에서부터 시작