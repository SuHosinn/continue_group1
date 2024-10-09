Continue에서 사용하는 Model 유형, Model 연동 유형

[자동완성 모델]
자동완성 모델은 FIM(fill-in-the-middle)이라고 불리는 특별한 format으로 학습된 LLM이다.
로컬 환경에서 모델을 실행하기 위해서는 "starcoder2:3b" 모델을 추천한다고 한다.

[채팅 모델]
사람과 대화할 수 있도록 훈련된 모델로 Continue에서는 'Claude 3.5 Sonnet' 모델을 추천하며 이외에도 'GPT-4o', 'Gemini 1.5 Pro', 'Llama3.1 405B'를 추천한다.

[임베딩 모델]
임베딩은 텍스트를 벡터 공간에 배치하며 벡터에서 유사한 공간에 있는 텍스트는 동일 또는 유사한 단어로 인식할 수 있다.
Continue에서 @codebase 유사한 것을 찾는데 사용된다.
'voyage-code-2' 모델 사용을 추천하며 로컬 환경에서 사용하는 경우 'nomic-embed-text' 모델 사용을 추천한다.
자바스크립터에서 인기있는 'Transformers.js' 라이브러리를 사용할 수도 있으며 허깅페이스의 텍스트임베딩을 사용할 수도 있으며 OpenAI나 Gemini를 사용할 수도 있다.

[Reranking 모델]
Reranking은 사용자의 질문에 응답해야 하는 순서를 좀 더 정확하게 답변하기 위해서 재조정하는 단계라고 할 수 있다.
Continue에서는 벡터 검색 후 가장 관련성이 높은 코드를 선택하기 위해 @codebase에서 사용한다.

모델 제공 업체
1. Mistral(미스트랄) (https://mistral.ai/)
 미스트랄은 프랑스 회사로 한국어에도 꽤 좋은 성능을 보이는 알려졌다. Continue 문서에는 채팅에는 'Mistral Large' 모델 적용, 자동완성에는 'Codestra', 임베딩에는 'Mistral Embed' 모델을 추천한다.
 Continue에 미스트랄의 모델 사용을 하기 위해서는 api key를 등록해야 하며 정책에 따라 과금된다. (과금 정보 : https://mistral.ai/technology/#pricing)
 1.1 Mistral Large
  Mistral Large 모델은 복잡한 작업에 가장 좋은 추론이 가능한 모델로 한국어를 포함해 다양한 언어를 지원
  128K 토큰을 한번에 처리할 수 있으며(Context window) 80개 이상의 프로그래밍 언어에서 수준 높은 코딩 능력을 갖추었다.
 1.2 Codestra
  Codestra는 코드 작업을 위해 만들어진 모델로 Python, java, C, C++, PHP와 같은 프로그래밍 언어 80개 이상에 대해 학습한 모델로 다른 모델보다 응답이 빠르다.
  32K 토큰을 처리할 수 있다.
 1.3 Mistral Embed
  Mistral Embed는 텍스트를 추출하기 위해 사용되는 모델로서 현재는 영어만 지원하고 있다.

2. Anthropic(앤트로픽) (https://www.anthropic.com/)
 Anthropic은 미국의 인공지능 회사로 OpenAI 퇴사자가 설립한 회사로 대화형 인공지능 Claude가 있다.
 모델은 3가지로 Haiku는 가볍고 빠르게 사용하기 위한 모델, Sonnet은 성능과 속도의 적절한 수준의 모델, Opus는 성능이 가장 우수한 모델로 어려운 수학과 프로그래밍에 사용하는 모델이 있다.
 Continue에 적용 시 api키를 발급받아 사용해야 하며 과금 체계에 따라 과금된다. (과금 정보 : https://www.anthropic.com/pricing#anthropic-api)

3. Azure OpenAI (https://azure.microsoft.com/ko-kr)
 Azure는 Microsoft사의 Public Cloud 서비스를 제공하는 CSP사이다. 여러 AI 모델 공급사로부터 모델을 공급받아 서비스를 하는 형태이다.
 Continue에서는 채팅 모델로 'GPT-4o' 모델을 추천하며 자동완성 모델로 'Codestral', 임베딩에는 'text-embedding-3-large' 모델 사용을 추천한다.
 Azure OpenAI에서 re-Ranking 모델은 제공하지 않는다.
 사용을 위해서는 api key를 발급받아 적용해야 사용이 가능하며 과금 체계에 따라 과금 된다. (과금 정보 : https://azure.microsoft.com/ko-kr/pricing/details/cognitive-services/openai-service/#pricing)
                                                    
4. Amazon Bedrock (https://aws.amazon.com/ko/bedrock/?gclid=Cj0KCQjwmOm3BhC8ARIsAOSbapXJzJtKJf-adSQvzrKZ32ICT4sj4d8cLZGrvUvXJD6VpAV5i8Zy1ZIaAreUEALw_wcB&trk=24a8f13a-f5db-4127-bcb7-8b2876aa4265&sc_channel=ps&ef_id=Cj0KCQjwmOm3BhC8ARIsAOSbapXJzJtKJf-adSQvzrKZ32ICT4sj4d8cLZGrvUvXJD6VpAV5i8Zy1ZIaAreUEALw_wcB:G:s&s_kwcid=AL!4422!3!692062155749!e!!g!!amazon%20bedrock!21058131112!157173586057)
 AWS는 Azure와 같이 amazon사의 Public Cloud 서비스를 제공하는 곳이며 Amazon Bedrock(아마존 베드록)은 AWS 환경에서 LLM을 개발하고 배포할 수 있는 플랫폼이다. 
 Continue에서는 채팅 모델로 'Claude 3.5 Sonnet' 모델을 추천하며 임베딩에는 'amazon.titan-embed-text-v2:0' 모델 사용을 추천한다.
 Amazon Bedrock에서 자동완성, re-Ranking 모델은 제공하지 않으며 사용자가 정의한 모델을 사용할 경우에는 'config.json' 파일에 모델을 지정해야 한다.
                                                        
5. Deepseek(딥시크) (https://www.deepseek.com/)
 딥시크는 중국의 스타트업이다.
 Continue에서는 채팅 모델로 'deepSeek-chat', 자동완성 모델에는 'deepseek-coder' 사용을 추천하며 임베딩, re-Ranking 모델은 제공하지 않는다.
 api key 사용을 위해서는 키를 발급 받아 적용해야 하고 과금 체계에 따라 과금된다.

6. Gemini(제미니) (https://gemini.google.com/?hl=ko)
 제미니는 구글이 만든 AI 챗봇이다.
 Continue에서는 채팅 모델로 'Gemini 1.5 Pro', 임베딩 모델에는 'models/text-embedding-004' 사용을 추천하며 자동완성, re-Ranking 모델은 제공하지 않는다.
 api key 사용을 위해서는 키를 발급 받아 적용해야 하고 과금 체계에 따라 과금되는데 일부 사용에 대해 무료로 사용할 수 있는 것 같다. (과금 정보 : https://ai.google.dev/pricing?hl=ko)
 다만 코드 어시스턴트 특성상 자동완성과 채팅이 지원되지 않는 것은 아쉽다.
                                                        
7. Gemini(제미니) (https://gemini.google.com/?hl=ko)
 제미니는 구글이 만든 AI 챗봇이다.
 Continue에서는 채팅 모델로 'Gemini 1.5 Pro', 임베딩 모델에는 'models/text-embedding-004' 사용을 추천하며 자동완성, re-Ranking 모델은 제공하지 않는다.
 api key 사용을 위해서는 키를 발급 받아 적용해야 하고 과금 체계에 따라 과금되는데 일부 사용에 대해 무료로 사용할 수 있는 것 같다. (과금 정보 : https://ai.google.dev/pricing?hl=ko)
 다만 코드 어시스턴트 특성상 자동완성과 채팅이 지원되지 않는 것은 아쉽다.

8. Ollama
  Ollama는 로컬에서 LLM을 구동할 수 있도록 하는 오픈소스이다.
  Continue에서는 채팅 모델로 'llama3.1:8b', 자동완성 모델로 'starcoder2:3b', 임베딩 모델로 'nomic-embed-text'를 추천하며 re-Rankig 모델은 제공하지 않는다.
  오픈소스이므로 apikey를 발급받아 설정하거나 할 필요는 없고 해당 모델을 다운로드 받아 Continue의 config에 해당 모델 사용을 적용이 필요할 것으로 보인다.

9. OpenAI (https://openai.com/)
   OpenAI는 미국의 인공지능 기업으로 chatGPT로 유명해졌다.
   Continue에서는 채팅 모델로 'GPT-4o', 자동완성 모델로 'starcoder2:3b', 임베딩 모델로 'text-embedding-3-large'를 추천하며 re-Rankig 모델은 제공하지 않는다.
   사용하기 위해서는 apikey 발급하여 적용해야 하며 과금 체계에 따라 과금된다. (과금 정보 : https://openai.com/api/pricing/)

이외에도 Cloudflare, 캐나다의 coHere 등 다양한 모델을 제공하는 회사가 있다.
