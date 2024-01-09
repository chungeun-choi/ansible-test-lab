# Ansible-test-lab

로컬 환경에서 앤서블 테스트를 진행하기 위한 레파지토리 입니다.

총 2개의 VM(가칭)을 관리할 수 있는 토폴로지로 구성되어져 있습니다

![image](https://github.com/chungeun-choi/ansible-test-lab/assets/65060314/a2e7a567-fd4f-44f4-bab4-1db935c18231)


----

### 테스트 랩 실행 방법

1.  레파지토리 클론
    
    ```bash
    git clone git@github.com:chungeun-choi/ansible-test-lab.git
    ```
    
2. '.env' 파일 생성
    ```
    vi ./.env
   ```
   파일 내용
   ```
   PASS={VM 비밀번호 설정}
   ```
3. **docker-compose 파일 실행**
    
    ```bash
    docker-compose up -d
    ```
    
4. **ssh 접속 확인 및 known_hosts에 public key 추가**
   
    ```bash
    # VM1 ssh 접속 명령어 실행 후 '.env' 파일에 명시한 비밀번호로 접속
    ssh root@localhost -p 220
    # VM2 ssh 접속 명령어 실행 후 '.env' 파일에 명시한 비밀번호로 접속
    ssh root@localhost -p 221
    ```
    >💡 **public key 추가 방법**
   > 
   > 위의 내용을 바탕으로 연결 시 아래와 같이 출력됩니다(mac 기준) 
   > <img width="563" alt="image" src="https://github.com/chungeun-choi/ansible-test-lab/assets/65060314/669375db-a528-430b-bf13-5c4d2e8ec68c">
   > 
   > 해당 응답으로 ‘yes’를 입력했을 때 ‘~/. ssh/known_hosts’에 public key가 자동으로 추가됩니다.
   > 
   > 해당 작업을 진행하지 않았을 때 앤서블을 통한 작업에 제한이 생길 수 있음에 따라 필수 적으로 진행하시길 바랍니다

---
### ansible 예제 코드 실행
