Butter Knife
============

![Logo](website/static/logo.png)

Vincula��o de campos e m�dotos para views do Android usando anota��es para gerar c�digos "Clich�s" para voc�

 * Elimine chamadas `findViewById` usando `@Bind` nos campos.
 * Agrupe diversas views em uma lista ou array. Utilize em todos eles de uma vez com a��es,
   setters, ou properties.
 * Elimine inner-classes an�nimas para listeners usando anota��es `@OnClick` em m�todos.
 * Use anota��es nos campos para eliminar pesquisa de recursos.

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

Para consultar a documenta��o e informa��es adicionais veja [o site][3].

__Remember: A butter knife is like [a dagger][1] only infinitely less sharp.__



Download
--------

Baixe o [�ltimo JAR][2] ou via Maven:
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

Para a vers�o SNAPSHOT:
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

Snapshots da vers�o de desenvolvimento est�o dispon�veis no [reposit�rio `snapshots` de Sonatype][snap].

Licen�a
-------

    Copyright 2013 Jake Wharton

    Licenciado sob a licen�a do Apache, Vers�o 2.0 (a "Licen�a");
    voc� n�o pode usar este arquivo exceto em conformidade com a Licen�a.
    Voc� pode obter uma c�pia da Licen�a em

       http://www.apache.org/licenses/LICENSE-2.0

    A menos que seja exigido pela lei aplic�vel ou acordado por escrito, software
    distribu�do sob a Licen�a � distribu�do na base "AS IS",
    SEM GARANTIAS OU CONDI��ES DE QUALQUER NATUREZA, evidente ou impl�cita. 
    Veja a Licen�a para as permiss�es espec�ficas da linguagem e as limita��es
    sob a licen�a. 

 [1]: http://square.github.com/dagger/
 [2]: https://search.maven.org/remote_content?g=com.jakewharton&a=butterknife&v=LATEST
 [3]: http://jakewharton.github.com/butterknife/
 [snap]: https://oss.sonatype.org/content/repositories/snapshots/
