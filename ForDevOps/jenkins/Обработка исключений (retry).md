Если нам надо чтобы при возникновении ошибки пайплайн продолжал выполнение мы можем добавить `catchError`
```groovy
pipeline{
	stages{
		stage("test"){
			steps{
				catchError(message: 'Skip because unstabilled'){ // тут если кетч поймает ошибку то ничего не произойдет, а в логах высветится сообщение
				sh 'exit 1'
				}
			}
		}
	
	}

}
```

Также в скобках `catchError` можно задать `buildResult` и `stageResult`.  Также можно задать `retry(5)` - этап будет пробовать собраться столько раз сколько укажем

```groovy
catchError(message: 'не собрался', buildResult:'unstable', stageResult:'unstable'){
	retry(5){
		<код>}
}
```



### Чтобы в скриптовом поймать ошибку надо использовать

```groovy
steps{
	script{
		try{
			retry(2){
			sh 'exit1'
			}
		}
		catch(e){
			currentbuild.result = 'Unstable'}
	}
}
```