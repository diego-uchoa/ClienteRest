# ClienteRest
Para executar a aplicação basta chamar da raiz da mesma a instrução:
```
$ mvn exec:java
```
Esta instrução executa a classe RestExample.java

```
public static void main(String[] args) throws IOException {
        //Note que o nome do cache é "cacheCelepar" e a chave será key+i (este i vem do for logo abaixo)
        String serverUrl = "http://10.15.96.229:8080/rest/cacheCelepar/key";
        RestExample restExample = new RestExample();
        //Loading keys/values on cache
        for (int i = 0; i < 300; i++){
        	//Incluir os 300 registros
            //restExample.putMethod(serverUrl+i, "Teste de input via rest para a key" + i);
            //Recuperar os registros
            restExample.getMethod(serverUrl+i);
            //Deletar todos os registros
            //restExample.delMethod(serverUrl+i);
        }
    }
```

Verifique que no método main da classe citada existem 3 chamadas, uma para inclusão, uma para busca e outra para exclusão.
Por padrão a chamada que vem descomentada é a de busca, caso não existam registros, basta descomentar a chamada de inclusão e executar novamente a instrução maven passada acima.
