# vue

- node,vscode,yarn 설치
- npm install -g @vue/cli
- vue create 프로젝트명
- npm run serve

# 반복문 데이터바인딩

```
  <a v-for="반복문이름 in 반복횟수" :key="키값">내용</a>
//기본구성

<a v-for="작명 in menu" :key="작명">{{ 작명 }}</a>
     menu:['홈','상품','상세'],


  <div v-for="(v,i) in products" :key="i">
    <h4>{{ v }}</h4>
    <h3>50만원</h3>
  </div>


```
