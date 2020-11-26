### merge vs rebase

- merge
  작업 히스토리가 전부 남음
  작업한 내용의 사실 기록

-rebase
 브랜치를 병합할 때 이런 Merge commit을 남기지 않음
 마치 다른 브랜치는 없었던 것처럼 프로젝트의 작업 내용이 하나의 흐름으로 유지

브랜치를 합칠 때 Merge를 써야 하는지 Rebase를 써야 하는지에 대해서는 정답이 없습니다. 프로젝트나 팀의 상황에 따라 다른 전략을 사용할 수 있습니다. 
다만, 로컬에서는 히스토리 정리를 위해 Rebase를 할 수도 있지만 이미 원격 저장소에 Push된 커밋은 Rebase를 하지 않는 것이 일반적입니다.

[출처](https://velog.io/@godori/Git-Rebase)
