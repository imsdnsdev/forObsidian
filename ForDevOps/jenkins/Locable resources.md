### Если нам надо забрать доступ чего либо (например базы данных, то мы можем использоать лок)

#### Lock принимает `label` - метку ресурса, variable - название ресурса, quantity - количество ресурса

```groovy
steps{
		lock(label: 'database', variable: 'LOCKED_RESOURCE', quantity: 1){
			echo env.LOCKED_RESOURCE	
		}
}
```
### Этот код возьмет себе 1 любой ресурс с меткой database и даст ему название 'LOCKED_RESOURCE'
