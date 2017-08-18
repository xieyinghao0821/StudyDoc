# mysql数据导入hive中  
```
sqoop import --connect jdbc:mysql://118.190.114.142:3306/education --username education --password education
--table total_data_persistent --hive-import --hive-database education --hive-table total_data_persistent_bak
--fields-terminated-by '\t' --null-string '**' --null-non-string '**'
``
