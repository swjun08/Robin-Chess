# Robin-Chess
-  Self-Designed Chess game

1) 개발 동기

저는  여러 활동을 통하여 디자인 프로그램과 작곡 기술을 모두 다룰 수 있게 되었습니다. 또한 Python 언어를 공부하며 class를 활용한 객체지향 프로그래밍에 대한 전반적인 이해를 갖추고  상황에서 그동안 배웠던 부분을 활용하여 저만의 프로젝트를  하였습니다. 종종 친구들과 보드게임을 즐겨하는데, 최근 체스에 빠져 있습니다. 각기 다른 특징을 가지는 기물을 이용하여 상대의 ‘킹’을 잡아야 하는 체스는 오랜  만큼 짜임새 있는 게임이라고 생각합니다. 상점에서 판매되는 체스판들을 포함하여 온라인으로 플레이할 수 있는 게임들은 제각기 다른  있습니다. 저만의 체스 게임을 제작하며, 하나의 프로젝트를 완성하는데 프로그래머, 디자이너, BGM 작곡가들이 어떤 역할을 수행하는지  하였습니다. 또한 저만의 캐릭터를 가진 작품을 통하여 각 분야에 대한 역량을 더욱 끌어올리는 계기가 되고자 저의 이름을 따서 만든 “로빈 체스: 디지털 아트와 음악의 조화” 프로젝트를 수행했습니다.

2) 개발 과정 (아트)

  - 컬러 팔레트 설정 과정
한 scene에 사용되는 색들은 서로 조화를 이루어야 합니다. 체스판에는  색을 메인으로 하여  색상이 필요합니다. 어떤 색을 배치할지 고민하던 중 “색상 palette”를 알게 되었습니다. 팔레트(palette)는 컴퓨터 그래픽스에서 디지털 이미지 관리를 위해 존재하는 색의 유한 집합입니다. 여러 팔레트를 살펴보던 도중   색상 팔레트를 찾았고, 해당 팔레트의 색을 RGB 형태로 프로젝트에서 활용하였습니다. 

  - 기물 화풍 직접 제작
체스 기물은  특징을 잘 살려 그렸습니다. 기존의 딱딱한 느낌을 새롭고 창의적으로 바꾸고 싶었고, 저만의 캐릭터를 만들게 되었습니다. 


왕이 군중들 앞에서 연설하는 상황을 상상하여 두 손을 하늘로 뻗고 있는 캐릭터를 만들었습니다. 이처럼 캐릭터마다 가지고 있는 직업의 특징과 처할 상황 등을 상상하여 만드니 재미있는 기물들이 많이 만들어졌습니다. 프로젝트에 사용되는 Sprite 들은 프로 크리에이트 (Procreate)라는 디자인 툴을 사용하여 제작했습니다.

  - Stable Diffusion 활용
게임 준비 화면을 구성할 때 text-to-image를 수행하는 대표적인 인공지능인 “Stable Diffusion”을 활용했습니다. 예측할 수 없지만 알면 알수록 빠져든다는 점에서 우주와 체스는 비슷하다고 생각했습니다. “Stable Diffusion”에 “I made a chess game and I want to show the harmony of the universe and chess on the preview screen."이라는 prompt를 입력하여 우주와 체스가 합쳐진 그림에 대한 아이디어를 얻었고, 이를 바탕으로 프로젝트의 준비 화면을 그렸습니다. 디자인 툴 내 “성운”, “라이트 펜” 브러시 등을 사용하여 성운, 유성을 표현했습니다. 그리고 체스 게임 내 가장 중요한 기물인 “킹”기물을 각 팀당 하나씩 두 개를 기울여 놓는 방법을 통해 두 팀의 경쟁 구도를 표현했습니다.


제가 게임에 사용할 폰트를 고르는 기준은 두 가지였습니다. 첫째, 체스 게임에 어울리는 클래식한 폰트입니다. 체스 게임은 오랜 역사를 지닌 게임으로 곳곳에 클래식한 폰트를 사용하면 어울릴 것이라고 생각했습니다. 클래식한 폰트로 Merida Regular를 사용했습니다. 둘째, 가독성이 좋은 폰트입니다. 아무리 예쁜 폰트여도 가독성이 좋지 않으면 소용이 없다고 판단했고, Open Sans 폰트를 사용했습니다. 



3) 개발 과정 (코딩)

  - State 변수 사용
State 변수를 사용하여 Ready, Gaming, Gameover 화면을 만들었습니다. Ready 화면에서는 Start 버튼을 누르면 state가 Gaming으로 바뀌게 했습니다. Gaming에서 홈버튼을 누르면 state가 Ready로, 게임오버 되면 state가 Gameover로 바뀌게 설정했습니다. Gameover에서는 restart 버튼을 통해 Ready 화면으로 돌아갈 수 있게 했습니다.

- Object를 이용하여 각기 다른 특징을 가지는 기물 생성 (상속)
클래스 개념을 사용하여 기물의 움직임과 게임 규칙을 구현했습니다. Gameobject라는 부모 클래스를 만들었습니다. 기본 입력값은 team, lx, ly, img입니다. l은 location의 약자로 lx와 ly는 해당 기물이 있는 위치의 x, y 좌표를 뜻합니다.
또한 부모 클래스는 마우스 클릭을 처리하는 click이라는 함수를 가집니다. 만약 마우스 위치가 해당 기물에 있다면 False였던 clicked가 True로 바뀌는 함수입니다. 
자식 클래스에는 dx, dy, move_candidate_x,move_candidate_y의 변수가 들어갑니다. "나이트"와 "킹", "폰"의 dx와 dy는 기물이 움직일 수 있는 상대위치를 가지고 있습니다. 예를 들어"나이트"기물이 두 칸 앞으로 가서 한 칸 오른쪽으로 갈 수 있으니, dx에는 [-2], dy에는 [1]을 넣어주었습니다. "룩"과 "비숍", "퀸"들의 dx와 dy는 기물이 움직일 수 있는 방향을 가지고 있습니다. 예를 들어 "비숍"이 갈 수 있는 방향은 대각선뿐이니 dx에는 [1, -1, -1, 1], dy에는 [1, 1, -1, -1]을 넣어주었습니다. 만약 dx, dy에 상대위치가 담겨있다면 해당 위치에 아군이 있는지 2차원 리스트를 통해 확인한 후 아군이 없는 값들만 따로 move_candidate_x와 move_candidate_y에 append 해주었습니다. 만약 방향만 담겨있다면 해당 방향으로의 모든 칸을 검사하여 아군과 겹치지 않는 곳만 후보지 리스트에 append 해주었습니다. 그리고 적군을 통과해서 갈 수 없기 때문에 적군을 만나고 나면 탐색을 중단하도록 코드를 짰습니다. 이 과정이 drawX 함수입니다. drawX 함수는 만약 후보지가 비어 있다면 탐색 후 채워주고 후보지가 차 있다면 후보지에 X 표시를 그리는 함수입니다. 
draw 함수는 lx, ly, img를 활용하여 해당 기물의 자리에 기물 이미지를 띄웁니다. lx와 ㅣy는 0~7의 숫자로 이루어져 있습니다. 좌푯값에 80을 곱하고 8을 더한 위치에 이미지를 blit했습니다. 
moveclick 함수는 기물을 움직여주는 함수입니다. 움직일 때 2차원 리스트의 기존 위치에0을 넣고, 새로운 위치에 본인 팀 숫자를 넣어줍니다. self.lx, self.ly에 움직일 상대위치를 더해서 기물을 움직입니다. 그리고 입력값에 상대방 기물 리스트와 상대방 죽은 기물 리스트를 받아와서 만약 움직인 후의 위치에 상대방 기물이 있다면 상대방 기물 리스트에서 해당 기물을 삭제 시키고 죽은 기물 리스트에 기물을 추가해줍니다.
piece.py 에서는 게임에 쓰이는 기물들을 불러오고사이즈를 맞춰주는 작업을 했습니다. 모든 기물은(55, 55)로 사이즈를 맞추었습니다. 그리고 자식클래스의 하나하나의 개체를 만들었습니다.


  - 이동 관련 세부적인 코딩 스킬 (리스트)
기물의 이동을 구현할 때 여러 코딩 스킬이 필요했습니다. 8x8 크기의 2차원 리스트를 만들어서 각 기물의 위치를 확인했습니다. 리스트 내에서 1은 화이트, 0은 아무것도 없는 칸, -1은 블랙이 있는 칸입니다. 기물 이동 전에 리스트에서 위치하던 칸에 0을 삽입하고, 이동 후의 위치에 기물의 숫자를 삽입했습니다. 이 리스트를 활용하여 기물이 움직일 수 있는 칸을 완전탐색할 수 있었습니다.

4) 개발 과정 (음악)
게임 음악은 직접 작곡했습니다. 오랜 전통을 가지고 있는 체스 게임에는 클래식한 음악이 어울릴 것이라고 생각했습니다. 키보드를 사용하여 전자 피아노 기능으로 멜로디와 반주를 작곡하였습니다. C코드, A코드, F코드, A코드를 반복하여 반주를 깔았습니다. 이 반주를 통해 플레이어는 더 깊은 분위기에 빠져들 수 있습니다. 그리고 멜로디는 오케스트라 활동을 통해 기른 음악적 감각을 활용해 프리스타일로 만들었습니다. 또한 키보드 안의 드럼 기능으로 베이스 비트를 만들었습니다. 게임 효과음도 직접 녹음했습니다. 일상의 소리를 활용하여 체스 게임에 어울리는 소리를 찾아보았습니다. 기물이 움직이는 효과음은 펜으로 책상을 쳐서 내는 소리를 사용하였습니다. 이러한 예술적 노력과 창의성은 게임을 더욱 흥미롭고 풍부하게 만들 수 있었습니다.
5) 결과 및 향후 개발 계획
  - 프로젝트의 Scene
Ready, Gaming, Gameover 3가지 화면을 구현하였습니다


  - 프로젝트의 기능
체스 규칙에 맞게 각 기물들의 움직임을 구현하였으며 이동 가능한 구역들을 X로 표시하였습니다. 서로 공격하여 잡힌 기물은 따로 표시하며 자신의 차례에는 자신의 기물만 움직일 수 있도록 제약을 설정하였습니다. 또한 국제 체스 규칙과 동일하게 플레이어 두명 모두에게 20분의 시간 제한이 존재합니다. 승자에 따라 게임 오버 장면이 바뀌며 게임이 종료되지 않는 한 무한히 게임을 리플레이할 수 있습니니다.
  - 향후 추가 개발 계획
향후 소켓을 활용한 멀티플레이, 인공지능과의 대전, 3D 체스 게임 등을 만들어보고 싶습니다. 

6) 결론

  - 느낀점
기존의 체스 게임에서는 딱딱하고 고전적인 느낌을 추구하였다면 저는 더 개성 있고 자유로운분위기의 게임을 만들기 위해 노력했습니다. 비록 기존에 있는 게임을 바탕으로 만든 프로젝트이지만 개성 있는 기물, 음악, 디자인 등은 게임 플레이어에게 또 다른 재미를 줄 것입니다. 기물이 왜 이렇게 디자인되었을 지 상상하며 게임을 플레이하는 즐거움도 예상할 수 있습니다. 인터넷에 공유되어 있는 체스게임 코드들은 클래스 개념을 사용하지 않고 이해하기 어렵게 구성되어 있었습니다. 저는 클래스 개념을 사용, 간결하게 코드를 구성하였습니다. 게임을 만들며 어려운 부분도 많았고, 아이디어가 떠오르지 않아 포기 하고싶은 순간도 있었습니다. 하지만 사소한 기능 하나하나를 구현하고,제대로 작동하는 것을 볼 때 저는 큰 성취감을 느꼈습니다. 
