Butter Knife
============

![Logo](website/static/logo.png)

Vinculação de campos e médotos para views do Android usando anotações para gerar códigos "Clichês" para você

 * Elimine chamadas `findViewById` usando `@Bind` nos campos.
 * Agrupe diversas views em uma lista ou array. Utilize em todos eles de uma vez com ações,
   setters, ou properties.
 * Elimine inner-classes anônimas para listeners usando anotações `@OnClick` em métodos.
 * Use anotações nos campos para eliminar pesquisa de recursos.

```java
class ExampleActivity extends Activity {
  @Bind(R.id.user) EditText username;
  @Bind(R.id.pass) EditText password;

  @BindString(R.string.login_error)
  String loginErrorMessage;

  @OnClick(R.id.submit) void submit() {
    // TODO call server...
  }

  @Override public void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.simple_activity);
    ButterKnife.bind(this);
    // TODO Use fields...
  }
}
```

Para consultar a documentação e informações adicionais veja [o site][3].

__Remember: A butter knife is like [a dagger][1] only infinitely less sharp.__



Download
--------

Baixe o [último JAR][2] ou via Maven:
```xml
<dependency>
  <groupId>com.jakewharton</groupId>
  <artifactId>butterknife</artifactId>
  <version>7.0.1</version>
</dependency>
```
ou Gradle:
```groovy
compile 'com.jakewharton:butterknife:7.0.1'
```

Para a versão SNAPSHOT:
```xml
<dependency>
  <groupId>com.jakewharton</groupId>
  <artifactId>butterknife</artifactId>
  <version>8.0.0-SNAPSHOT</version>
</dependency>
<dependency>
  <groupId>com.jakewharton</groupId>
  <artifactId>butterknife-compiler</artifactId>
  <version>8.0.0-SNAPSHOT</version>
  <optional>true</optional>
</dependency>
```
ou Gradle:
```groovy
buildscript {
  dependencies {
    classpath 'com.neenbedankt.gradle.plugins:android-apt:1.8'
  }
}

allprojects {
  repositories {
    maven { url "https://oss.sonatype.org/content/repositories/snapshots" }
  }
}
```
```groovy
apply plugin: 'com.neenbedankt.android-apt'

dependencies {
  compile 'com.jakewharton:butterknife:8.0.0-SNAPSHOT'
  apt 'com.jakewharton:butterknife-compiler:8.0.0-SNAPSHOT'
}
```

Snapshots da versão de desenvolvimento estão disponíveis no [repositório `snapshots` de Sonatype][snap].

Licença
-------

    Copyright 2013 Jake Wharton

    Licenciado sob a licença do Apache, Versão 2.0 (a "Licença");
    você não pode usar este arquivo exceto em conformidade com a Licença.
    Você pode obter uma cópia da Licença em

       http://www.apache.org/licenses/LICENSE-2.0

    A menos que seja exigido pela lei aplicável ou acordado por escrito, software
    distribuído sob a Licença é distribuído na base "AS IS",
    SEM GARANTIAS OU CONDIÇÕES DE QUALQUER NATUREZA, evidente ou implícita. 
    Veja a Licença para as permissões específicas da linguagem e as limitações
    sob a licença. 

 [1]: http://square.github.com/dagger/
 [2]: https://search.maven.org/remote_content?g=com.jakewharton&a=butterknife&v=LATEST
 [3]: http://jakewharton.github.com/butterknife/
 [snap]: https://oss.sonatype.org/content/repositories/snapshots/
