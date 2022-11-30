opasm;l[dsmf;pdsmfpdsmpfmdspfmldspmf;sldmfs;dknf;kldsmf;sdmfs;mfopasm;l[dsmf;pdsmfpdsmpfmdspfmldspmf;sldmfs;dknf;kldsmf;sdmfs;mfopasm;l[dsmf;pdsmfpdsmpfmdspfmldspmf;sldmfs;dknf;kldsmf;sdmfs;mfopasm;l[dsmf;pdsmf
opasm;l[dsmf;pdsmfpdsmpfmdspfmldspmf;sldmfs;dknf;kldsmf;sdmfs;mfopasm;l[dsmf;pdsmfpdsmpfmdspfmldspmf;sldmfs;dknf;kldsmf;sdmfs;mfopasm;l[dsmf;pdsmfpdsmpfmdspfmldspmf;sldmfs;dknf;kldsm
Сертификаты
Установка в AD
Устанавливаем https://slproweb.com/download/Win64OpenSSL-3_0_1.exe
В папке bin копируем файл openssl.conf
opasm;l[dsmf;pdsmfpdsmpfmdspfmldspmf;sldmfs;dknf;kldsmf;sdmfs;mf
В Powershell
dsfafasgfd,g;ldfmgpmas,fpSNFKMASFMDASMFASMFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Далее вводим  .\openssl.exe genrsa -out root.key
 gpmas,fpSNFKMASFMDASMFASMFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Создаем новый конфиг openssl-1.cnf
.\openssl req -x509 -new -nodes -key root.key -sha256 -days 365 -out root.crt -config openssl-1.cnf -subj "/C=RU/ST=Moskow/L=Moslow/O=demo lab/OU=IT/CN=demo.lab/emailAddress=admin@demo.lab"
Открываем с помощью блокнота
gpmas,fpSNFKMASFMDASMFASMFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Добавляем промежуточный сервер iwtm
.\openssl.exe genrsa -out iwtm.key
.\openssl.exe req -new -sha256 -config openssl-1.cnf -key iwtm.key -out iwtm.csr
Создание приватного ключа сертификата
 gpmas,fpSNFKMASFMDASMFASMFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Проверим, что созданный запрос на подпись сертификата (CSR) содержит то, что нам нужно:
 ASDASFASFgpmas,fpSNFKMASFMDASMFASMFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Создаем файлы serial с содержимым “02” и пустой файл index без расширений!
 ADGFDGHHNBVgpmas,fpSNFKMASFMDASMFASMFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Подпись и создание сертификата
MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Добавляем пользователя arm
Создание приватного ключа сертификата
Создание запроса на подпись сертификата (CSR)
Подпись и создание сертификата
.\openssl x509 -req -in "iwtm.csr" -CA "root.crt" -CAkey "root.key" -CAcreateserial -out "iwtm.crt" -extensions v3_req -extfile "openssl-1.cnf" -subj "/C=RU/ST=Moskow/L=Moskow/O=demolab/OU=IT/CN=iwtm/emailAddress=iwtm@demo.lab"

.\openssl pkcs12 -export -in iwtm.crt -inkey iwtm.key -in root.crt -inkey root.key -out out.p12 -password pass:xxXX1234
 
Упаковка ключа и сертификата в файл PKCS12
 MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Упаковка всех ключей и сертификатов в out.p12
 MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Подключаемся к ТМ через WinCSP
 
Перекидываем наш сертификат
 MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Извлекаем из сертификата публичный ключ (считаем, что pfx-ключ находится в папке root)
Извлекаем из сертификата закрытый ключ
 
Переносим полученные файлы в папку сертификатов
 MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Изменяем файл конфигурации Nginx /etc/nginx/conf.d/iwtm.conf
 
Перезапускаем Nginx
 
systemctl restart nginx.service
MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Нажимаем установить сертификат

Выбираем Доверенные корневые центры
 MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Добавляем сертификат сервера в промежуточные доверенные центры сертификации

Далее также только в Личное

Видим путь сертификатов
 MSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDFMSD;'AMFKAMFLKSAMDFSLFMLSMDFSDF
Видим безопасное подключение к ТМ

 





