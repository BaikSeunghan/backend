![KakaoTalk_Photo_2022-09-15-23-54-01](https://user-images.githubusercontent.com/56210700/190436678-45237690-b3b5-4fa4-bd1a-f9b569cfc102.jpeg)
# 🍻술모꼬
항해99 X 동북 이노베이션, 실전 프로젝트 4조
> \* 서비스명 : 술모꼬 (*술 + 모꼬지(모임의 순우리말) = 🍻술모꼬🍻*)  
> 집에서도 손쉽게 술 모임을 가질수 있는 서비스 술모꼬입니다
    
- [\[사이트 바로가기\]](https://www.sulmoggo.live/)
- [\[시연영상 바로가기\]](https://youtu.be/cz1HbJZnBY0)

<br />

## 👥 멤버
- Back-end: [김태현](https://github.com/Tmoney2014), [백승한](https://github.com/BaikSeunghan)
- Front-end: [김원영](https://github.com/102wy), [노희정](https://github.com/imhjnoh)
- Design : 김해영

<br />

## 🗓 프로젝트 기간
- 2022년 8월 5일 ~

<br />

## :hammer_and_wrench: 기술 스택

### :boom: Back-end
![springboot](https://user-images.githubusercontent.com/89123240/190444793-a66ab960-fcfa-425b-a2cc-d034cf1b2d4a.png)
![mysql](https://user-images.githubusercontent.com/89123240/190444624-50b53ffa-88a3-4a71-88b3-f51613f622f0.png)
![redis](https://user-images.githubusercontent.com/89123240/190444683-570792ad-ca7f-4ded-bea3-7b354dc82dc1.png)
![ngnix](https://user-images.githubusercontent.com/89123240/190444770-d3c39126-ca48-4f44-b318-2fafbae60102.png)
![rds](https://user-images.githubusercontent.com/89123240/190444643-5583c570-f9e7-4bdc-85c1-ab35a59df43b.png)
### :boom: DevOps
![cloudformation](https://user-images.githubusercontent.com/89123240/190444735-3ad8e819-411f-4782-bc1f-8cf887ece2f8.png)
![ec2](https://user-images.githubusercontent.com/89123240/190444748-d3684def-5f65-4bba-b6bd-17196a276f9e.png)
![s3](https://user-images.githubusercontent.com/89123240/190444612-7271c0f0-015e-48e0-b2a0-93aba96acfc6.png)
![bibaton](https://user-images.githubusercontent.com/89123240/190444713-df513fab-d2c4-4212-97b9-5dffe4dcb5bb.png)
![firebasehosting](https://user-images.githubusercontent.com/89123240/190444812-222d8800-75ac-4e44-ab8f-498c11f74f2d.png)
![githubaction](https://user-images.githubusercontent.com/89123240/190444830-9f5465ac-c129-4b0b-800f-6e478d3e6c23.png)
<br />
<br />


## 🧩 Architecture

![architecture](https://user-images.githubusercontent.com/56210700/190443726-9aaf49b0-4c2d-4f62-bb03-516225e9bac5.png)


<br />


## 📌 API 명세서
<details>
<summary>API 명세서</summary>
<div markdown="1">
    <img src="https://user-images.githubusercontent.com/95524472/190453831-f093b829-dfb0-4416-8318-71a50523eab3.png" />
    <img src="https://user-images.githubusercontent.com/95524472/190453915-bc0a825b-4d26-483d-aa49-6cfdbf66aaef.png" />
    <img src="https://user-images.githubusercontent.com/95524472/190454013-2e010e3b-e7e8-4aa1-9fa8-a76184b3e3fc.png" />
</div>
</details>

<br />


## 🗺 ER Diagram
![image](https://user-images.githubusercontent.com/95524472/190455062-86733cb8-dc28-491c-a805-6750480f9bc6.png)

<br />
<br />



## ⛔️ Trouble Shooting


```
1. JPA에서 데이터 조회 시 발생하는 n+1 문제
```
> ![image](https://user-images.githubusercontent.com/95524472/190856075-7ea865e7-9e6e-469b-8f3c-9ed1462e0072.png)

<br />
<br />


```
2. 파일 업로드 시, 1mb 이상의 파일이 업로드 되지 않는 문제 (NginX)
```
> 
> ❗️ 문제 : 1mb 미만의 파일은 정상적으로 업로드 되지만, 1mb 이상은 업로드 되지 않음
>
> ❓ 원인 : NginX에서 디폴트 파일업로드 용량이 1MB  
>
> 💡 To-Be (nginx.conf 파일 수정을 통한 업로드 제한 용량 변경)  
>![image](https://user-images.githubusercontent.com/95524472/190855231-5a4b5bce-833e-4a02-a13b-7961effb6759.png)

<br />
<br />

```
3. 내용에 긴 글 작성이 되지 않을 경우
```
> 
> ❓ 원인 : MySql에서 Data Type이 VARCHAR()로 되어 있어서, 글자수 제한이 존재하였음
>
> 💡 To-Be (TEXT() 타입으로 변경하여 해결)  
> ![image](https://user-images.githubusercontent.com/95524472/190854664-6c3e87ad-986d-4232-8f6e-4ff657ba1d01.png)

<br />
<br />

```
4. 게시글, 채팅의 시간이 한국 시간과 9시간 차이가 나는 문제
```
> 
> ❓ 원인 : 시간 기본값이 UTC(협정세계시)으로 설정되어있기 때문
>
> 💡 To-Be (EC2 시간대 변경)   
> ![image](https://user-images.githubusercontent.com/95524472/190854698-d2691591-5720-457f-a26d-a9947547d85a.png)


<br />


```
5. Nginx 도입 이후 WebSocket handshake 에러
```

> ❓ 원인 : Nginx conf 설정
>
> 💡 To-Be 하단과 같이 Upgrade 헤더와 Connection 헤더를 같이 프록시에 전달하여 해결.
> ![image](https://user-images.githubusercontent.com/95524472/190855231-5a4b5bce-833e-4a02-a13b-7961effb6759.png)


<br />


## 🔓 기타 고려 사항이었지만 시간 관계상 적용하지 못한 점

> - 가독성 향상 및 타입 에러 방지를 위해 QueryDSL 적용
> - 서버에 과한 요청으로 부하를 주기 쉬운 like 요청



