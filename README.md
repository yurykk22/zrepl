# zrepl
Репликация набора данных ZFS на удаленный хост

Команда:

`zrepl [-F] [-L] [-R] [-U] [-c] [-d] [-r] [-s] [-t] [-u] [-w] [-h \<ssh identity file\>] [-i \<CHAT_ID\>] [-k \<API_KEY\>] [-l \<logfile\>] [-p \<destinationpool\>] \<dataset\> \<remotehost\>`  
  `-F` Принудительно откатывает файловую систему к самому последнему снимку перед выполнением операции приема  
  При невозможности осуществить разностное копирование будет сделано полное копирование  
  `-L` Отключить логирование  
  `-R` Файловая система реплицируется, включая все дочерние файловые системы и снимки  
  `-U` Устанавливается запрет на монтирование файловой системы, связанной с полученным потоком  
  `-c` Передается более компактным потоком, используя сжатые данные  
  `-d` Удалить снимки в целевой файловой системе, отсутствующие в исходной  
  `-r` Файловая система, связанная с полученным потоком, переводится в режим только для чтения  
  `-s` Реверсная репликация с удаленного хоста на текущий  
  `-t` Отслеживать список изменяемых данных  
  `-u` Файловая система, связанная с полученным потоком, не монтируется  
  `-w` Передача зашифрованного потока  
  `-h` Файл, из которого считывается ssh индентификатор (закрытый ключ) для проверки подлинности  
  `-i` CHAT ID для оповещения через телеграм об ошибке репликации  
  `-k` API KEY для оповещения через телеграм об ошибке репликации  
  `-l` Указать свой лог-файл  
  `-p` Пул назначения. Если пул не указан, то он совпадает с источником  
  
 Примеры:  
  `zrepl -F pool1/data host1`  
  Полное копирование набора данных pool1/data на удаленный хост host1  
  
  `zrepl pool1/data host1`  
  Разностное копирование набора данных pool1/data на удаленный хост host1  
