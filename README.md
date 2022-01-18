Плейбук выполняет следующие задачи:
1. Устанавливает JDK на все хосты в директорию '/opt/jdk/{{ java_jdk_version }}'.  
Версия JDK задается в переменных для группы all: ***java_jdk_version***.  
При этом исходный файл заданной версии "jdk-{{ java_jdk_version }}_linux-x64_bin.tar.gz" загружается с control хоста и должен присутствовать в директории ***files***.  
Также на целевых хостах создается файл /etc/profile.d/jdk.sh, прописывающий в переменные среды JAVA_HOME и добавляющий путь к бинарям JDK в PATH.  
Все таски этого раздела помечены *тегом java*.  
2. Устанавливает Elasticsearch на хосты группы elasticsearch в директорию '/opt/elastic/{{ elastic_version }}'.  
Устанавливаемая версия Elasticsearch задается в переменных для группы elasticsearch: ***elastic_version***.  
Дистрибутив загружается напрямую с сайта https://artifacts.elastic.co.  
На целевых хостах создается файл /etc/profile.d/elk.sh, прописывающий в переменные среды ES_HOME и добавляющий путь к бинарям Elasticsearch в PATH.  
Все таски этого раздела помечены *тегом elastic*.  
3. Устанавливает Kibana на хосты группы kibana в директорию '/opt/kibana/{{ kibana_version }}'.  
Устанавливаемая версия Kibana задается в переменных для группы kibana: ***kibana_version***, сопровождается переменной ***kibana_checksum*** со значением хеша для проверки целостности устанавливаемого дистрибутива.  
Дистрибутив загружается напрямую с сайта https://artifacts.elastic.co.  
На целевых хостах создается файл /etc/profile.d/kibana.sh, прописывающий в переменные среды KIBANA_HOME и добавляющий путь к бинарям Kibana в PATH.  
Все таски этого раздела помечены *тегом kibana*.
