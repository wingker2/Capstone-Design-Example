# 1. 과제 개요
## 1-1. 과제 선정 배경 및 필요성
 기존의 게임들, 특히나 1인칭 게임들은 둠이나 카스에서부터 시작하여 오버워치 배틀그라운드에 이르기까지 지난 수십년동안 많은 발전을 이루어냈습니다. 그러나 그래픽이나 장르, 매커니즘같은 부분들의 혁신은 기존보다 활발하게 적용되는 반면, 캐릭터 간의 상호작용은 예전보다 훨씬 혁신적인 시스템이 등장했음에도 불구하고 적용에 있어서는 다른 부분보다 매우 더딘 경향이 있습니다. 이는 특히나 인디쪽으로 갈수록 커지는데 대부분의 인디 게임에서는 그냥 제외되고 있다고 봐도 무방합니다. 물론 이러한 Action시스템의 도입이 그 자체만으로도 게임의 개발량을 무시할 수 없을 정도로 증가시킨다는 단점이 있어 의도적으로 제외했을 수도 있습니다. 그러나 Quick-Time-Event나 Interact 시스템이 적용하기에 너무 어렵고 Cost도 높다는 편견이 만연해 있어 지례짐작으로 게임에서 제외하는 경우도 없지 않을 것 입니다. 따라서 현재 3D 게임 개발에 있어 고평가 받고 있는 언리얼엔진을 사용하여 게임을 개발하는 경험을 쌓는 동시에 기존의 게임에서 벗어나 깊이를 더해줄 수 있을 Interactive Animation 시스템과 Quick Time Event(QTE) 시스템을 구현해보고 보다 Cheap하고 쉬운 방법을 찾고 연구해보고자 합니다.

## 1-2. 과제 주요내용
 본 과제는 시스템적으로 크게 두가지 파트로 나뉘어져 있으며 동시에 스토리적으로도 두가지 파트로 나뉘어져 있습니다. 먼저 시스템으로는 Quick-Time-Event 시스템과 그와 동반되는 Interactive-Animation 시스템이 있습니다. 이 중 Quick-Time-Event는 주로 버튼액션 방식으로 구현되며 특정한 상황에서 플레이어의 행동을 성공시키거나 적대적 NPC의 행동을 회피하거나 방어하는데 사용됩니다. 그리고 Interactive-Animation 시스템은 앞서 언급한 QTE와 연동되는 시스템으로 NPC의 Animation과 Player의 Animation이 서로 상호작용이 가능하도록 일치시키는 역활을 합니다. 또한 스토리적으로 나뉜 두 파트는 각각의 상황에서 QTE시스템이 적용되는 방식을 보여줍니다. 첫번째 파트에서는 플레이어가 비교적 자유롭게 움직이며 적대적 NPC를 상대할 때 QTE-Interactive-Animation이 적용되는 방식을 보여주고 두번째 파트에서는 일련의 Sequence가 자동으로 진행되어지는 과정에서 QTE-Interactive-Animation이 자연스럽게 적용되는 과정을 보여줍니다. 
  
## 1-3. 최종결과물의 목표
 본 과제의 최종결과물의 목표는 게임 중 각각의 상황에서 QTE-Interactive-Animation이 어떻게 구현이 될 수 있는지를 보여주는 데 있습니다. 일반적으로 생각하기에 하나 이상의 캐릭터와 애니메이션들을 서로 상호작용시키는 과정에서 Quick-Time-Event을 적용하는 것은 매우 코스트가 크고 어렵다는 인식이 있습니다. 그렇기에 이 프로젝트를 통해 그러한 편견을 깨고 본 결과물에서 보여지는 것처럼 쉽고 Cheap한 방법이 있다는 것을 제시하고자 합니다.    

# 2. 과제 수행방법

 시작하기 앞서 학기 중 1인 개발이라는 시간적 이슈가 있어 최대한 효율적인 방향으로 과제를 수행하기로 방향을 정했습니다. 요는 '1인칭 QTE게임 개발' 이니 만큼 구현해야할 핵심 Asset들인 Interactive-Animation과 언리얼엔진 내부의 QTE시스템을 제외하고는 되도록이면 외부에서 가져오려고 노력했습니다. 결과적으로 Level 디자인이나 스토리 설계, 게임에 적절하게 사용하기 위한 Texture-Tweak 작업, 받아온 Character들을 커스텀한 Skeleton에 다시 Rigging을 하는 작업 등이 필요했습니다만 전반적으로 시간을 많이 절약할 수 있었습니다. 그리고 최종발표 날짜에 맞춰 기본적인 캐릭터들과 Texture, 레벨디자인과 Particle System, 사운드 등을 구현해낼 수 있었으며 기본적인 Interactive-Animation 시스템과 Quick-Time-Button-Event 시스템 역시 구현해낼 수 있었습니다. 또한 자유롭게 컨트롤을 하는 와중에 QTE시스템이 적용되는 부분인 스토리 파트1과 일련의 Sequence 중에 자동으로 QTE시스템이 적용되는 파트2까지 구현을 성공했습니다
 
 # 3. 진행내용
 ## 3-1. 과제진행 내용
![Map](https://user-images.githubusercontent.com/38785553/123765589-d4e5f600-d900-11eb-87d5-2da2aec273e2.png)
Figure 1. 프로젝트에 사용된 맵의 구조.
![QTE_RealTime2](https://user-images.githubusercontent.com/38785553/123763605-ededa780-d8fe-11eb-9719-56d98e9645fa.png)
Figure 2. Part0와 Part2에 사용된 QTE-Interactive-Animation의 예시1.
![QTE_RealTime](https://user-images.githubusercontent.com/38785553/123763615-efb76b00-d8fe-11eb-9f13-a1e4d8251b30.png)
Figure 3. Part0와 Part2에 사용된 QTE-Interactive-Animation의 예시2.
 먼저 기본적으로 게임에 필요한 레벨 디자인을 러프하게 만들었습니다. 이후 게임에 필요한 캐릭터들을 가져와서 새롭게 텍스쳐링을 하고 리깅을 해서 UE4로 보내고 기본적인 캐릭터 Blueprint들을 만들어서 서로 연결을 시켰습니다. 이후부터는 스토리 파트1을 위한 Animation들을 만들기 시작했습니다. 또한 플레이어를 공격하는 적대적 NPC를 상대하여 일정한 공간안에서 움직이고 반격하며 그렇게 게임이 진행됨에 따라 자연스럽게 QTE-Interactive-Animation이 실행되어 버튼 판정을 통해 게임을 이어나갈 수 있도록 알고리즘들을 설계하였습니다. 중간발표 바로 일주일 전인 4월 23일에 플레이어에게 컨트롤권을 준 상태에서 QTE를 적용시키는 스토리 파트1을 어느정도 완성할 수 있었습니다. 또한 최종 발표일인 6월 18일까지 자동으로 진행되는 중에 QTE-Animation이 자동으로 적용되는 Part2 부분을 완성했으며 추가적인 Sound와 Particle시스템까지 어느정도 완성하여 적용시켰습니다.  

## 3-2. 진행내용의 주요특징 및 설명

![QTE_Images](https://user-images.githubusercontent.com/38785553/123754571-03120880-d8f6-11eb-9373-3d3cf691e3f4.png)
Figure 4. 언리얼엔진4에서 사용될 QTE-Widget의 예시.
![Skeleton](https://user-images.githubusercontent.com/38785553/123764235-900d8f80-d8ff-11eb-82e0-98883f180280.png)
Figure 5. QTE-Interactive-Animation를 위하여 Interaction 계산을 위한 Joint를 Root Joint위에 추가해준 Skeleton구조의 예시.
![Interactive_Images](https://user-images.githubusercontent.com/38785553/123757642-24c0bf00-d8f9-11eb-95b2-0bea70c9fc04.png)
Figure 6. 커스텀한 QTE-Interactive-Animation 제작을 위하여 3D 프로그램에서 Animation을 Bake하기 위한 예시.
![Blueprint1](https://user-images.githubusercontent.com/38785553/123764256-9439ad00-d8ff-11eb-89fb-23c60220b78c.png)
Figure 7. 언리얼엔진4에서 Cheap한 QTE-Interactive-Animation을 실행하기 위한 Blueprint의 구조.
![Blueprint2](https://user-images.githubusercontent.com/38785553/123764263-96037080-d8ff-11eb-8792-2a7410d65c8f.png)
Figure 8. 언리얼엔진4에서 QTE-Interactive-Animation을 위하여 Interaction Joint에 Bake된 데이터들을 이용하여 각각의 모델들의 Location를 맞춰주는 과정.
![Blueprint3](https://user-images.githubusercontent.com/38785553/123764267-97349d80-d8ff-11eb-95bb-dc5acabe9888.png)
Figure 9. 언리얼엔진4에서 QTE-Interactive-Animation을 위하여 Interaction Joint에 Bake된 데이터들을 이용하여 각각의 모델들의 Rotation를 맞춰주는 과정.
![Blueprint4](https://user-images.githubusercontent.com/38785553/123764271-9865ca80-d8ff-11eb-81e8-16b24eab5c4d.png)
Figure 10. 언리얼엔진4에서 QTE-Interactive-Animation을 위하여 각각의 모델들의 Collision 프로파일을 변경시켜주는 과정.

 1인칭 게임이기에 플레이어의 애니메이션은 많은 부분이 생략되어있습니다. 보이지 않는 부분은 대체로 제대로 구현이 되어있지 않습니다. 그리고 이는 상호작용을 하는 NPC들에게도 동일하게 적용되어 있습니다. 시간을 절약하기 위한 방편입니다. 게임에 등장하게 될 캐릭터들은 플레이어를 포함하여 6명이며 파트1에는 두명이 등장하고 나머지는 파트2에 등장합니다. 자유로운 행동이 설정되어 있는 파트1에 여러명의 캐릭터를 등장하기에는 Cost가 너무 커질 것 같아 최대한 줄인 결과입니다. 내용을 설명드리면, 파트1에서 플레이어는 한정된 공간인 밀실에서 무기를 들고 있는 적대적 캐릭터와 싸우게 됩니다. 플레이어는 knife를 휘둘러서 저항이 가능하고 적대적 npc의 체력을 일정 수치 이하로 깎거나 특정한 위치에 있게 된다면 QTE가 가미된 Interactive-Animation이 실행됩니다. 이때 버튼 판정을 실패한다면 게임오버가 되고 버튼 판정을 성공한다면 게임을 더 이어갈 수 있습니다. 그리고 플레이어가 적대적 NPC의 체력을 0보다 이하로 깎는 것을 성공한다면 일련의 QTE-Interactive-Animation을 통해 밀실에서 탈출하게 됩니다. 여기까지가 파트1입니다. 그리고 파트2부터는 캐릭터가 어느 지점에 도착한다면 자동으로 애니메이션이 진행되게 됩니다. 이 Sequence중에는 플레이어의 조작권한은 박탈되며 QTE-Interactive-Animation의 결과에 따라 게임이 더 진행될지 아니면 GameOver가 될지 정해지게 되고 최종적으로 모든 QTE를 성공하게 된다면 게임이 종료됩니다.
 추가로, QTE와 Interactive-Animation에 대해 설명을 드리자면, 먼저 QTE는 간단하게 두가지로 나뉩니다. 이 두가지는 각각 버튼연타형 QTE와 한정된 시간 안에 올바른 키를 누르는 QTE로서 본 프로젝트에서는 이 두가지 모두 성공하기 어렵지 않도록 난이도를 설정했습니다. 그리고 Interactive-Animation은 각 캐릭터들마다 Interactive용 Joint를 하나씩 둬서 이 Joint들을 같은 위치, 같은 Rotate로 일치시키는 방식을 통해 구현을 했습니다. 
 
 # 4. 기대효과 및 활용방안
 ## 4-1. 기대효과
 앞서 말씀드렸다시피 언리얼엔진의 인디게임 개발자 지원과 더불어 3D 마켓플레이스의 활성화로 인해 이제는 소수의 인디게임 개발자들도 3D 인디게임을 수월하게 개발할 수 있게 되었습니다. 그러나 QTE나 Interactive-Animation을 적용하는 데는 막연한 어려움이 존재했었지요. 그러나 이런 본 프로젝트에서 제시하는 방법을 통해 개발자들은 손쉽게 QTE나 Interactive-Aniamtion을 게임에 적용할 수 있을겁니다. 이는 곧 전반적인 3D인디 게임들의 퀄리티를 증가시키는데 유의미한 도움이 될 수 있을 것이라 생각합니다.  

## 4-2. 활용방안
 본 프로젝트에서 제시하는 QTE와 Interactive-Animation은 다방면으로 활용이 가능합니다. 필자가 제작한 일인칭 게임에서처럼 적용을 할 수 있을뿐만 아니라 3인칭 게임에서도 중요한 순간마다 사용을 해 게임에대한 몰입감을 높일 수 있을 것입니다. 또한 게임 진행 중에 컷씬이 추가되어있을 경우 자연스럽게 그 컷씬으로 전환이 가능하도록 하는 기능 역시 포함되어 있습니다. QTE를 중심으로 사용한다면 '헤비레인'이나 '디트로이트 비컴휴먼'같은 영화같은 게임을 제작하는데도 간단하게 활용이 가능할 것이라 생각하는 바입니다.
 
## 4-3. 결론 및 제언
 게임 엔진을 다루는 코어한 코딩이 아닌 커먼하게 게임 제작자의 입장에서 새로운 기술의 연구와 적용이라는 주제를 다루고 있습니다. 하지만 그럼에도 불구하고 꽤나 유용한 기술이라는 것은 확신할 수 있습니다. 실제로 언리얼엔진에서는 이러한 애니메이션들에 대한 매커니즘을을 따로 지원하지도 않을 뿐더러 비슷한 알고리즘을 다루는 툴이나 듀토리얼 조차도 없기 때문입니다. 따라서 단순히 어려울 것이라는 편견에서 벗어나 생각보다 복잡하지 않게 QTE-Interactive-Animation을 만들고 적용시킬 수 있다는 것은 게임 제작자의 입장에서는 크나큰 어드밴티지라고 생각하는 바입니다. 
 그러나 그럼에도 불구하고 프로젝트를 위해 제작한 게임의 결과물이 매우 작위적이라는 것은 부정할 수 없는 바입니다. 너무 QTE와 관련된 애니메이션과 기술들만 보여주려고 하다보니 하고싶은 게임이 아닌 보여주기 위한 게임이 되어버렸다는 사실에 조금 아쉬울 따름입니다. 
