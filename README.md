# zrepl
Репликация набора данных ZFS на удаленный хост

Команда:  
`zrepl [options] <dataset> <remote host>`  

Параметры запуска:  
`-C` Сжимать данные при передаче. Актуально для несжатых данных и низкоскоростных каналов передачи  
`-F` Принудительно откатывает файловую систему к самому последнему снимку перед выполнением операции приема. При невозможности осуществить разностное копирование будет сделано полное копирование  
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
`-h <identity file>` Файл, из которого считывается ssh индентификатор (закрытый ключ) для проверки подлинности  
`-i <chat id>` chat id для оповещения через телеграм об ошибке репликации  
`-k <api key>` api key для оповещения через телеграм об ошибке репликации  
`-l <log file>` Указать свой лог-файл  
`-p <destination pool>` Целевой пул  
  
Примеры:  
`zrepl -F pool1/data host1`  
Полное копирование набора данных pool1/data на удаленный хост host1  
  
`zrepl pool1/data host1`  
Разностное копирование набора данных pool1/data на удаленный хост host1  
