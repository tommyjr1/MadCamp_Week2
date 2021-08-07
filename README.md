# TheKAIST

더 지니어스의 <같은 숫자 찾기> 게임을 멀티 플레이 가능한 모바일 앱 게임으로 구현했다.

> 개발자: 송재현, 최종윤

## Login

<img src="image/main.jpg" height="400"> <img src="image/login.jpg" height="400"> <img src="image/signin.jpg" height="400">

+ LOG IN 버튼을 통해 회원가입 한 계정으로 접속할 수 있다.
+ SIGN UP 버튼을 통해 회원가입 할 수 있다.
+ 카카오 로그인 버튼을 통해 카카오 계정으로 회원가입/로그인 할 수 있다.

## Main

<img src="image/online.jpg" height="400"> <img src="image/challenge.jpg" height="400"> <img src="image/ranking.jpg" height="400"> <img src="image/profile.jpg" height="400">

+ Online 탭
  + 실시간 접속자들을 확인할 수 있다. 다른 유저와 게임을 하고있다면 Playing, 아니라면 Online이라고 표시가 된다.
  <br/> 게임할 상대를 클릭하고 하단의 게임요청 버튼을 누르면 상대방에게 게임을 요청할 수 있다. 상대방 화면에는 요청 수락/거절 알림창이 나타난다. 취소 시 메인으로 돌아가고, 수락 시 동시에 게임이 시작된다.
+ Ranking 탭
  + 전체 유저의 순위를 확인할 수 있다. 승리가 많은 순으로 정렬되고, 사용자의 프로필과 이름, 승패의 횟수가 보여진다.
+ Profile 탭
  + 본인의 프로필을 확인할 수 있다. 이름과 아이디, 프로필 사진이 보여지고 아래에 순서대로 세개의 버튼이 있다.
    1. 플레이 기록을 클릭하면 본인의 지금까지의 게임 기록이 보여진다. 게임 상대와 서로의 점수, 승자와 패자를 확인할 수 있다.
    2. 프로필 변경으로 들어간다면 본인의 이름과 비밀번호, 프로필 사진을 변경할 수 있다. 총 네 개의 기본 프로필 중에 하나를 골라 사용할 수 있다. 카카오 로그인을 한 경우, 카카오 프로필로 처음 기록되고 게임 사진으로 수정한다면 카카오 프로필사진과 다른 사진으로 변경된다. 또한 비밀번호 정보는 받아오지 않기때문에 수정에 영향을 끼치지 않는다.
    3. 로그아웃을 클릭한다면, 현재 로그인 된 계정이 로그아웃되면서 다른 유저의 Online 탭에서 Online 상태였던 본인의 정보가 사라진다.


## Game

<img src="image/game start.jpg" height="400"> <img src="image/game.jpg" height="400"> 

+ 게임 방법
  1. 게임 요청을 수락하면, 게임이 시작되면서 게임화면이 실행된다.
  2. 서로에게 뒷면의 숫자와 연산자가 10초간 보여지는데, 1~12의 숫자와 사칙연산자의 위치를 빠르게 확인하고 기억해야한다.
  3. 라운드가 시작되어 타켓 숫자가 나오면 숫자 카드, 연산자 카드, 다른 숫자 카드 세개로 만들어내는 것이 목표이다. 버저 버튼을 눌러 카트를 선택할 수 있다. 연속으로 버저를 누를 수 없다. 만약 틀리면 차례가 상대방에게로 넘어가면서 상대방의 버저버튼이 클릭 가능하게 된다. 차례는 이렇게 매 라운드마다 번갈아가면서 진행한다.
  4. 세 개의 카드를 눌러 확인하고, 만약 맞다면 점수가 올라가면서 다음 라운드로 넘어가 새로운 타겟 숫자를 받는다. 차례는 또 먼저 버저 버튼을 누른사람이 가져간다.
  5. 5점을 얻는 사람이 이기고, 게임이 종료된다.

+ 게임 화면 구성
  1. 맨 위에는 게임할 때 목표가 되는 타겟 숫자가 보여진다. 게임이 처음 연결될 때는 Wait, 10초간 뒷면의 숫자와 연산자를 보여줄 때에는 Show for 10 seconds, 이후 게임이 시작할 때 Game start 가 보였다가 타겟 숫자가 나타나게 된다.
  2. 그 아래에는 현재 함께 게임하는 상대방과 본인의 획득 점수(이긴 라운드 횟수)가 보여진다. 5점을 먼저 맞추면 게임이 종료된다.
  3. 화면 중앙에는 게임카드 16장이 보여진다. 카드의 앞면은 랜덤으로 정해진 알파벳, 뒷면은 숫자나 연산자로 이루어져 있다. 게임을 진행하면서 본인의 차례에는 세개의 카드를 클릭할 수 있고, 클릭하면 본인의 화면과 상대방의 화면에서 클릭된 카드가 뒤집히면서 숫자와 연산자를 확인할 수 있다.
  4. 아래에는 세 개의 이모지가 있다. 함께 게임하고 있는 상대에게 실시간으로 보낼 수 있는 이모지 메시지이다. 하나씩 클릭을 하면 상대방의 게임카드 위쪽에 본인이 보낸 이모지가 나타난다.
  5. 화면 밑에는 버저 버튼과 pass 버튼이 있다. 게임을 하면서 본인이 카드를 뒤집고 싶을 때에 먼저 버저 버튼을 눌러 차례를 얻어야 한다. 만약 자신이 버저 버튼을 누른다면 상대방의 버저 버튼은 비활성화 된다. <br/> 해당 라운드를 기권하고 다음 라운드로 넘어가기를 희망하면 pass 버튼을 누를 수 있다. 본인이 pass를 요청하면 상대방의 화면에 pass를 할 것인지 요청하는 알림창이 나타나고, 수락하면 다음 라운드로 넘어간다. 상대방이 거절한다면 상대방에게 한번의 기회가 주어지고 다음 라운드로 넘어간다.


## Implementation
+ MongoDB를 이용해 userAccount와 battle 두 개의 schema를 만들어 이용했다. 가입된 userAccount에서는 사용자의 id, 이름, 비밀번호, 프로필 이미지, 이긴 횟수, 진 횟수, 게임 진행 여부를 저장한다. battle에서는 게임아이디, 요청자의 id(ask), 수락자의 id(accept), 요청자의 점수 ask_scr, 수락자의 점수 accept_scr, 승자의 이름, 패배자의 이름이 기록된다.
+ Online 탭에서는 swipe refresh layout을 사용하여 DB에서 유저를 받아온 후 게임 중인 유저는 아래로, 온라인인 유저는 위로 표시한다.
+ Ranking 탭에서는 DB에서 모든 유저를 받아온 후 승리 수로 정렬하여 보여준다.
+ 게임 화면에서는 socket.io를 사용하여 실시간 게임 플레이를 구현했다. 
  + 클릭한 position을 서버로 보내면 broadcast로 상대방에게 같은 정보를 보내고 서로 카드가 뒤집히는 것을 볼 수 있다.
  + 세 개의 카드를 클릭하면 서버에서 evaluate 한 후 타켓 넘버와 비교하여 correct, wrong 중 하나를 양측에 보낸다.
  + turn, round 의 시작과 끝에 대한 정보들을 client와 server가 실시간으로 주고받는다.
  + 게임의 시작과 끝에는 userAccount schema, battle schema를 업데이트 한다.
