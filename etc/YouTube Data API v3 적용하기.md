# YouTube Data API v3 적용하기

### 1. Google Cloud Platform 프로젝트 등록

- https://console.cloud.google.com/

1. 새 프로젝트 생성하기
2. YouTube Data API v3 사용
3. API Key 생성

<br/>

### 2-1. YouTube API를 통해 동영상 리스트 가져오기

- https://developers.google.com/youtube/v3/docs/videos/list?hl=ko

<br/>

### 2-2. YouTube API 직접 작성하기

```js
const res = await axios.get("https://www.googleapis.com/youtube/v3/search", {
  params: {
    key: process.env.YOUTUBE_API_KEY, // 1-3에서 생성한 API Key
    q: "검색어", // 검색어
    part: "snippet",
    type: "video",
    maxResults: 25,
    fields: "items(id, snippet(title))",
    videoEmbeddable: true,
  },
});
```
