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



