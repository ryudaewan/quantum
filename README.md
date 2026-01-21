# quantum

이 깃허브 저장소는 OSGEO 서울 공부 집단 구성원들이 같이 공부하는 Udemy의 [챗GPT와 파이썬으로 주식 자동매매 앱 및 웹 투자 리포트 만들기](https://www.udemy.com/course/gpt-trading/) 강좌에 대한 실습 코드를 담고 있습니다.

강좌와 다른 점은 다음과 같습니다.

* 강좌는 키움증권의 OCX를 쓰기 때문에 반드시 윈도우에서 32비트 파이썬을 써야 하나 본 저장소 소스는 키움증권 REST API를 쓰므로 OS 제한이 없습니다.
* 키움증권 Rest API는 [키움증권 REST API 기초부터 실전까지](https://www.youtube.com/playlist?list=PLlbsy38S8CCyrKyL4JTTkBE4L9m1cw7No)를 참조 바랍니다.
* 강좌는 Anaconda를 사용하나 본 저장소 소스는 uv 기반으로 작성합니다. pip, venv도 쓸 필요 없습니다.

아래는 github 저장소에서 소스 코드를 내려받은 후 필요한 라이브러리를 내려받는 것까지 하는 예시입니다. 윈도우 아니고 유닉스 쉘 기준입니다.

```
$ git clone https://github.com/ryudaewan/quantum.git
Cloning into 'quantum'...
remote: Enumerating objects: 57, done.
remote: Counting objects: 100% (57/57), done.
remote: Compressing objects: 100% (37/37), done.
remote: Total 57 (delta 19), reused 45 (delta 10), pack-reused 0 (from 0)
Receiving objects: 100% (57/57), 20.10 KiB | 4.02 MiB/s, done.
Resolving deltas: 100% (19/19), done.

$ cd quantum

$ source .venv/Scripts/activate

(quantum) $ uv sync
Installed 7 packages in 231ms
 + certifi==2026.1      
 + charset-normalizer==3.4.4
 + idna==3.11
 + python-dotenv==1.2.1
 + requests==2.32.5
 + urllib3==2.6.3
 + websocket-client==1.9.0
```

uv sync를 하면 pyproject.toml을 읽어 필요한 라이브러리를 현 환경에 설치합니다.

윈도우에서도 유닉스 쉘을 쓸 수 있는데, 아래와 같은 방법이 있습니다.
* 윈도우용 Git 깔면 같이 깔리는 bash를 씁니다.
* WSL을 씁니다.