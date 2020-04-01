# common tip  
- 긴 명령어 별명 지정  
alias {var}="{command}"  
ex) alias k="kubectl"  


# docker 
[공식문서링크](https://docs.docker.com/engine/reference/commandline/cli/)  
- 실행중인 컨테이너 리스트  
docker ps  
  
- 모든 컨테이너 리스트  
docker ps -a  
  
- 이미지 리스트  
docker image ls  
  
- 서비스 리스트  
docker service ls  
  
- 사용하지않는 자원 전부 삭제  
docker system prune -a  
  
- 빌드  
docker build -t {image-name} {path}  
ex) docker build -t gcr.io/proj/ff:v1 .  
  
- 실행  
docker run --name {name} -p {host-port}:{container-port} {image-id}  
ex) docker run --name my-redis -p 6379:6379 redis:latest  
  
- 백그라운드 실행    
docker run -d --name {name} -p {host-port}:{container-port} {image-id}    
ex) docker run -d --name my-redis -p 6379:6379 redis:latest  

- 연결   
docker exec -it {container-id} {image-id}
ex) docker exec -it mongodb mongo

# docker-compose 
[공식문서링크](https://docs.docker.com/compose/reference/)   
- 실행  
docker-compose up  

# kubernetes-kompose 
[공식문서링크](https://kubernetes.io/docs/tasks/configure-pod-container/translate-compose-kubernetes/)  
- 변환  
kompose convert  
  
# gcloud 
[공식문서링크](https://cloud.google.com/sdk/gcloud?hl=ko)  
- 초기화  
gloud init  
  
- 프로젝트 선택  
gcloud config set project {project-id}  
  
- 현재 프로젝트 정보  
gcloud compute project-info describe --project {project-id}  
  
- 리전 설정    
gcloud config set compute/region {region-id}  
ex) gcloud config set compute/region us-central1-c  
  
- 존 설정    
gcloud config set compute/zone {zone-id}  
ex) gcloud config set compute/zone us-central1-c  
  
- 클러스터 생성  
gcloud container clusters create {cluster-name}  
ex) gcloud container clusters create my-first-cluster  
  
- 클러스터 목록  
ex) gcloud container clusters list  
  
- 컨텍스트 설정  
gcloud container clusters get-credentials {cluster-name}  
ex) gcloud container clusters get-credentials first-cluster  
  
- 도커 권한 설정  
ex) gcloud auth configure-docker  
  
- 도커이미지 등록 (이미지생성시 이름규칙을 따라야한다)  
docker push {region-id}/{project-id}/{name}:{tag}  
ex) docker push gcr.io/myproj-271309/mygame:v1    

# kubectl 
[공식문서링크](https://kubernetes.io/ko/docs/reference/kubectl/cheatsheet/)  
- 설정 보기  
kubectl config view    
  
- 클러스터, 디플로이먼트, 서비스, 파드정보 리스트  
kubectl get all  
  
- 실행  
kubectl apply -f {yaml-file}  
ex) kubectl apply -f ./my-service.yaml  


# mongodb 
[공식문서링크](https://docs.mongodb.com/manual/mongo/)  
- 데이터베이스 선택  
use {database-name}  
ex)use admin  
  
- 인증  
db.auth("{name}", "{pwd}")  
ex) db.auth("id","password")  
  
- 데이터베이스 모든사용자 정보  
db.getUsers()  
  
- 데이터베이스 사용자 생성 (파라미터 넣는 방법은 따로 검색)  
db.createUser(...)     
  
- 모든 데이터베이스 리스트   
show dbs  
show databases  
  
- 모든 테이블 리스트  
show tables  
show collections  
  
- 데이터 베이스 삭제  
db.dropDatabase()  

# redis 
[공식문서링크](https://redis.io/topics/rediscli)  
- 인증  
auth {password}  

- 비밀번호 체크  
config get requirepass  

- 비밀번호 설정  
config set requirepass {password}  
  
- 모든 데이터 삭제  
flushall  




# git
- 풀 리퀘스트
1. 깃허브에서 대상프로젝트 Fork     
2. git clone <fork저장소>  
3. git checkout -b <branch이름>   
4. 코드변경  
5. git add .  
6. git commit -m "message"  
7. git push origin <branch이름>  
8. 깃허브에서 Pull Request  
9. git checkout origin  
10. git branch -D <branch이름>
11. git push --delete origin <branch이름>
