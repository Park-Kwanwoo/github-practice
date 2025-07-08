# 깃 연습을 위한 저장소

## Git이란?

**Git**이란 리누스 토르발에 의해 만들어진 `버전 관리 시스템(VCS)`으로 분산 버전 관리 시스템(DVCS)의 방식으로 스냅샷(Snapshot)의 사용하는 버전 관리 시스템이다.

> 버전 관리 시스템(VCS)
> - 파일 변화를 시간에 따라 기록했다가 나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템
> - 각 파일을 통째로 이전 상태로 되돌릴 수 있고, 시간에 따라 수정 내용을 비교해 볼 수도 있으며, 누가 문제를 일으켰는지 추적도 가능하고, 누가 언제 만들어낸 이슈인지도 알 수 있다.

### Git을 특별하게 해주는 이유들

1. **분산 버전 관리 시스템(DVCS)** <br />
분산 버전 관리 시스템(DVCS)은 중앙집중식 버전관리나 로컬 버전 관리와 달리 저장소에 의존적이지 않고 유연하다.
DVCS 방식은 파일의 마지막 스냅샷을 Checkout하지 않고, 저장소의 히스토리(파일의 변화들) 전부를 복제하기에 서버에 문제가 생겨도 해당 복제물로 작업을 이어나갈 수 있기 때문이다.
또한, 모든 구성원들이 상태를 공유하기 때문에 협엽에 있어서도 유연하게 상호작용 할 수 있다. <br />
![Image](https://github.com/user-attachments/assets/37a99f38-9be7-4b6f-aaf5-ecc0b372e2e0)

2. **스냅샷(Snapshot)** <br />
스냅샷이란 데이터의 특정 시점 상태를 복사하여 저장하는 기술로, Git은 데이터의 변화가 일어나게 되면 변경의 최종 상태를 그대로 저장하는 방식인 스냅샷 방식을 통해 파일을 관리한다. 만약 여러 파일을 관리하고 있는 경우, 변경이 일어난 파일들은 변경 후의 파일을 저장하고, 그렇지 않은 파일들은 그 전 버전을 연결해서 그대로 가져와 저장소에 저장한다. <br />
![Image](https://github.com/user-attachments/assets/d57591d2-8a45-4d72-b76f-870469176229)


---

## 상태와 공간

<img width="752" alt="Image" src="https://github.com/user-attachments/assets/57f850ad-20d3-495b-bd51-dec6fb27bba6" />

깃은 ***Committed, Staged, Modified*** 라는 3개의 상태로 파일을 관리하고, 상태들은 Git 프로젝트의 세 가지 단계와 연결되어 있다.

### 상태

1. Committed <br />
    데이터가 로컬 데이터베이스에 안전하게 저장됐다는 것을 의미

2. Modified <br />
    수정한 데이터가 아직 로컬 데이터베이스에 커밋되지 않은 것을 의미

3. Staged <br />
    현재 수정한 파일을 곧 커밋할 것이라고 표시한 상태

### Git의 3가지 공간

1. Working Directory <br />
    수정 사항이 보관되는 디렉토리로 **Untracked** 파일과 **Tracked** 파일로 나뉘어진다. <br />
    Modified 상태의 파일들이 여기에 속한다.
    
> [!NOTE]
      Tracked와 Untracked<br />
      Tracked는 git에 의해 관리 및 추적되고 있는 파일들을 의미한다. (기존 파일) <br />
      Untracked는 git에 의해 관리 및 추적되지 않는 파일들을 의미한다. (새로운 파일)

2. Staging area <br />
    커밋을 위해 Working Directory에서 Add된 파일들을 위한 공간이다. <br />
    Staged 상태의 파일들이 여기에 속한다.

3. Repository <br />
    커밋된 파일들이 존재하는 공간이다. <br />
    Committed 상태의 파일들이 여기에 속한다.

---

## Github란?

GitHub는 Git 저장소를 웹에서 관리하고, 여러 사람이 함께 협업할 수 있도록 지원하는 서비스이다. <br />
Git으로 버전 관리를 수행하는 프로젝트의 **원격 저장소** 역할을 하며, 다양한 **사용자 친화적인 인터페이스**와 **협업 기능**을 제공한다.

예를 들어, Github는 다음과 같은 기능들을 보다 간편하게 사용할 수 있다.
- 버그 추적 (Issue)
- 기능 요청 (Feature request)
- 작업 관리 (Projects, Labels)
- Pull Request(PR)을 통한 코드 리뷰 및 병합
- 오픈 소스 프로젝트 기여

이처럼 Github는 소셜 기능과 협업 도구를 결합하여, 단순한 코드 저장소 이상의 역할을 수행한다.


### Git과 Github 차이점 정리
<br />

| 항목 | Git | Github |
| --- | --- | --- |
| 정의 | 분산 버전 관리 시스템(DVCS) | Git 저장소를 **웹에서 호스팅하고 협업**할 수 있는 서비스 |  
| 주요 역할 | 코드의 버전 관리 및 이력 추적 | Git 저장소를 클라우드에 저장, 공유 및 협업 |
| 위치 | 사용자의 로컬 PC or 서버 | 웹, 클라우드 서비스 |
| 주요 기능 | 커밋, 브랜치, 머지, 이력 추적 | Pull Request, 이슈 관리, 기능 요청 등 |


## Git 시작하기

### Git 설정 (CLI)

Git을 사용하기 위해 맨 처음에 사용자 정보를 설정해야 하는데, 이는 **commit 시 누가 작성했는지를 기록**하기 위함이다. <br />
<br />
**설정**

```bash
git config --global user.name "설정할 이름"
```
```bash
git config --global user.email "설정할 이메일"
```
**확인**

```bash
git config --global user.name
```
```bash
git config --global user.email
```

`--global` 옵션을 사용해 설정하게 되면, 현재 사용자 계정의 모든 Git 저장소에서 해당 설정이 사용된다. <br />
만약, 프로젝트마다 다르게 설정하고 싶다면 `--global` 옵션을 사용하지 않고 해당 저장소 디렉토리에서 다음과 같이 설정하면 된다.

```bash
git config user.name "설정할 이름"
```
```bash
git config user.email "설정할 이메일"
```

### Git 프로젝트 생성 및 Github 연동

```bash
git init
```

위 명령어는 현재 디렉토리를 git 저장소로 초기화하여, Git을 통해 버전 관리를 시작하겠다는 의미이다. <br />
명령어 실행 시 .git 폴더가 생성되는데, 이 폴더는 Git이 동작하는데 필요한 모든 메타데이터를 저장한다. <br />
예를 들어, 커밋 히스토리, 브랜치 정보, 스태이징 영역 정보, 리모트 저장소 정보 등이 모두 이곳에 저장된다. <br />
> [!WARNING]
    `.git` 폴더를 삭제하게 되면 프로젝트가 더 이상 git에 의해 관리되지 않으며, 버전 이력과 Git 설정 정보가 모두 사라진다.
<br />

`git init` 명령어를 통해, Git 저장소가 초기화되었으니, 이제 변경 사항을 추적하고 Git에 반영하는 기본 흐름을 알아보자.  <br />

프로젝트 내에서 변경사항이 발생하면, Git은 변경된 파일을 Modified, 새로 생성된 파일을 Untracked 상태로 분류한다. <br />
이러한 변경사항을 Git의 관리 대상으로 삼기 위해서는 다음과 같은 절차를 진행해야 한다.

1. Staging Area에 변경 사항 등록
    ```bash
    # . 변경된 모든 파일을 의미
    git add .
    ```
    or 
    ```bash
    # 수정파일.확장자 파일을 Staging Area에 등록
    git add 수정파일.확장자
    ```

2. 커밋을 통해 버전 저장소에 반영
    ```bash
    # 편집기를 통해 커밋 메시지 작성
    git commit
    ```
    or 
    ```bash
    # 해당 커밋 메시지로 커밋
    git commit -m '커밋 메시지'
    ```

이제 변경 사항이 Repository에 저장되고, 사용자는 변경 이력을 통해 변경 전과 현재를 오가며 버전을 관리할 수 있다. <br />
해당 내용은 #branch에서 자세히 알아보겠다. <br />

**다음은 Github와 연동하는 방법이다.**


1. 로컬의 Git 저장소와 연결할 Github 레포지토리(원격 저장소)를 생성한다.
    <img width="700" height="900" alt="Image" src="https://github.com/user-attachments/assets/7eea3177-d4c4-473e-9329-541cb21e5d24" />
2. 로컬 저장소(.git 폴더가 있는 위치에서) 원격 저장소와 연결하기 위해 원격 저장소에 대한 정보를 설정한다.
    ``` bash
    git remote add origin https://github.com/사용자명/저장소명.git
    ```
3. 로컬 저장소의 변경 이력을 원격 저장소로 푸시(push)한다.
    ``` bash
    git push -u origin main
    ```
4. 누군가의 변경 이력으로 인해 원격 저장소의 내용으로 최신화를 하고 싶다면 풀(pull) 한다.
    ```bash
    git pull orgin main
    ```

