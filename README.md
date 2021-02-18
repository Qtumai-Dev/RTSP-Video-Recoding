# Frame_Transfer
RTSP영상을 저장하고 분석서버로 전송

video_recoding.py
working dir에 날짜 폴더를 생성하고 그 안에
rtsp프로토콜을 이용하여 프레임을 읽어 1분마다 시분.avi 파일로 저장
시작 종료 에러 로그 작성 추가 (시간, dvr번호, dvr 체널, 파일이름, 동작, 저장 프레임, 보낸 프레임, 에러내용) 
에러 종료시 루프 추가
클래스로 구성

frame_send.py
서버에 소켓 통신 시도
접속성공시
rtsp_write에서 저장된 영상을 차례대로 캡쳐하여 frame을 서버로 전송
전송이 완료된 파일은 삭제

frame_recv.py
포트 50001 오픈/Listen
릴레이서버에서 보낸 파일을 받아 imshow로 출력


### threading 추가 필요
### 실행파일 강제종료시 / 전원 off시 / 네트워크 끊겼을때 재접속시 이어진 시간 + 이어지는 프레임 전송필요