# Глава 3. Рабочие станции.

Обслуживание операционных систем на рабочих станциях сводится к выполнению трех основных задач: первоначальная установка системного программного обеспечения и приложений, обновление системного программного обеспечения и приложений, настройка сетевых параметров. Мы называем эти задачи «большой тройкой».

Рабочая станция в нашем понимании – компьютерное оборудование, выделенное для работы одного пользователя. Как правило, имеется в виду настольный компьютер или ноутбук пользователя. В современной сети у нас также есть среди  прочего  компьютеры  с  удаленным  доступом,  виртуальные  машины и ноутбуки с док-станциями.

Рабочие станции, как правило, используются в больших количествах и отличаются долгим жизненным циклом (рождение, использование, смерть).

![Жизненный цикл](1.png)

Новое состояние относится к совершенно новой машине.

- Чистое состояние относится к машине с установленной, но еще не настроенной ОС.
- Сконфигурированное состояние  означает,  что  система  настроена  и  функционирует должным образом.
- Неизвестное состояние относится к компьютеру, который был неправильно 
сконфигурирован или конфигурация которого устарела.
- Отключенное состояние относится к машине, которая была списана и отключена.

Энтропия– процесс нежелательной амортизации, приводящий компьютер в неизвестное состояние, которое можно исправить с помощью отладки.

Процесс восстановления – это процесс, при котором данные на машине стираются, и система заново устанавливается, возвращая машину к сконфигурированному состоянию.

Архитектурное решение, принятое системным администратором, может усилить или ослабить целостность операционной системы.

Установка вручную всегда предполагает возможность ошибок. Если ошибки возникают в процессе установки, узел сети начнет свой жизненный цикл с тенденцией к разрушению. Если процесс установки полностью автоматизирован, новые рабочие станции будут развернуты должным образом.

Переустановка (процесс восстановления) подобна установке с той разницей, что в первом случае, возможно, понадобится перенести старые данные и приложения.

В этой главе термин платформа используется для обозначения определенной комбинации поставщика оборудования и ОС. Вот некоторые примеры: персональный компьютер с процессором AMD Athlon под управлением Windows Vista, Mac с процессором PPC под управлением OS X 10.4, настольный компьютер с процессором Intel Xeon под управлением Ubuntu 6.10 Linux, Sun Sparc Ultra 40 под управлением Solaris 10 или Sun Enterprise 10000 под управлением Solaris 9. В некоторых компаниях компьютеры от разных поставщиков под управлением одной и той же операционной системы могут считать разными платформами.

# 3.1. Основы

С обслуживанием операционных систем рабочей станции связаны три критически важных аспекта:

1.  Первоначальная установка системного ПО и приложений.
2.  Обновление системного ПО и приложений.
3.  Настройка сетевых параметров.

Не всегда просто автоматизировать некоторые процессы. Когда поставщики пытаются продать нам новую продукцию, мы всегда интересуемся, можно ли автоматизировать ее работу и как это сделать.

# 3.1.1. Установка ОС

Автоматизация решает огромное количество проблем, но не все из них являются техническими. 

Во-первых, автоматизация экономит деньги. Разумеется, одним из основных преимуществ является время, выигранное за счет замены ручных процессов автоматическими. Кроме того, автоматизация устраняет два вида скрытых затрат. 

Первый относится к ошибкам: при ручном выполнении процессов существует вероятность ошибок. Второй тип скрытых затрат относится к неоднородности. Если вы вручную устанавливаете операционную систему, вы никогда не добьетесь той же конфигурации на другой машине.

Второй тип скрытых затрат относится к неоднородности. Если вы вручную устанавливаете операционную систему, вы никогда не добьетесь той же конфигурации на другой машине.

# 3.1.1.1. Удостоверьтесь, что ваша автоматизированная система действительно автоматизирована

Самый важный аспект автоматизации заключается в том, что установка должна быть полностью автоматизирована.

Процедуру, требующую возвращения человека посреди установки для ответа на тот или иной вопрос, нельзя назвать полностью автоматизированной, и она теряет эффективность.

Когда вы решите, что закончили автоматизацию того или иного процесса, попросите опробовать вашу систему какого-нибудь человека, незнакомого с вашей работой. Проинструктируйте его одним предложением и больше ему не помогайте. Если у него возникнут проблемы, значит, вам необходимо улучшить данный аспект вашей системы. Повторяйте эту процедуру до тех пор, пока ваш помощник не сможет самостоятельно использовать систему.

# 3.1.1.2. Частично автоматизированная установка

Частичная автоматизация лучше, чем ее полное отсутствие. До тех пор пока система установки не будет работать идеально, необходимо обеспечить какие-то временные средства для некоторых этапов. Автоматизация оставшегося 1% может занять больше времени, чем автоматизация первых 99%.

Основная временная мера – документирование всего процесса, которое позволит впоследствии воспроизводить его в точности.

Можно автоматизировать различные этапы установки. Некоторые из них отлично поддаются автоматизации.

# 3.1.1.3. Клонирование и другие методы

В некоторых сетях для создания новых машин используется клонирование жестких дисков. Клонирование жесткого диска подразумевает создание узла с точной конфигурацией ПО, которая необходима для всех развертываемых узлов. Затем жесткий диск этого узла клонируется (копируется) на все новые компьютеры. Первую машину часто называют «золотым узлом». Вместо того чтобы снова и снова копировать жесткий диск, его содержимое можно скопировать на компакт-диск, ленточный накопитель или файловый сервер, которые впоследствии будут использоваться при установке.

Мы предпочитаем автоматизированный процесс установки копированию диска по нескольким причинам. Во-первых, если по аппаратному обеспечению новая машина значительно отличается от старой, необходимо создать отдельный мастер-образ. Даже при отсутствии воображения можно представить себе огромное количество мастер-образов, которое может понадобиться в итоге. И наконец, наличие резервных машин для каждого типа оборудования, требующего новых образов, значительно повышает расходы и усилия, необходимые для установки.

Поставщики некоторых ОС не поддерживают клонированные диски, так как процесс установки может изменяться на основе таких факторов, как тип обнаруженного оборудования.Можно достичь золотой середины, применяя как автоматизацию, так и клонирование.

Некоторые поставщики ОС не предоставляют возможности автоматизировать установку. Однако можно найти способы усовершенствовать этот процесс.

# 3.1.1.4. Стоит ли доверять установкам от поставщиков

Переустановка ОС с нуля предпочтительнее по нескольким причинам. Во-первых, прежде чем машина сможет работать в вашей сети, вам, вероятно, потребуется установить другие приложения и локализации поверх установленной поставщиком ОС. Автоматизация всего процесса установки с нуля зачастую проще, чем установка приложений и конфигурирование предустановленной ОС. Во-вторых, поставщики вносят изменения в конфигурацию предустановленной ОС в собственных целях, никого об этом не уведомляя. Установка с нуля дает вам известное состояние каждой машины. Использование предустановленной ОС означает отклонения от вашей стандартной конфигурации. Порой эти отклонения могут вызвать проблемы.

Другая причина для отказа от использования предустановленной ОС – то, что время от времени ОС узлов сети приходится переустанавливать.

# 3.1.1.5. Контрольные списки при установке

Какой бы способ установки ОС вы ни использовали – ручной или полностью автоматизированный, – вы можете улучшить согласованность процесса с помощью контрольных списков. Эти списки помогают удостовериться, что техники не пропустят ни одного этапа. Польза таких списков очевидна, если процесс установки полностью выполняется вручную.

Даже если процесс установки ОС полностью автоматизирован, грамотный контрольный список все же может принести пользу. Некоторые действия невозможно автоматизировать, так как их необходимо выполнить физически (например, запустить процесс установки; удостовериться, что мышь работает; протереть экран монитора; предоставить пользователю на выбор несколько ковриков для мыши).

# 3.1.2. Обновление системного ПО и приложений

Системы обновления ПО должны быть достаточно универсальными, чтобы они позволяли устанавливать новые приложения и обновлять уже имеющиеся, а также устанавливать патчи ОС. Если система способна только устанавливать патчи, новые приложения можно упаковать и использовать их в качестве патчей. Такие системы также можно использовать для внесения незначительных изменений на большом количестве узлов сети. Небольшие изменения конфигурации, такие как новый файл /etc/ntp.conf, можно упаковать в патч и установить автоматически. Большинство систем позволяет включать постустановочные скрипты – программы, которые при запуске выполняют изменения, необходимые для установки пакета. Для внесения сложных изменений можно даже создать отдельный пакет, содержащий только постустановочный скрипт.

# 3.1.2.1. Процесс обновления отличается от установки

Автоматизация обновления ПО схожа с автоматизацией первичной установки, но между ними есть и несколько существенных различий.

- _Узел сети находится в рабочем состоянии._ Обновление устанавливается на машины, которые находятся в рабочем состоянии, а при первичной установке необходимо выполнить ряд дополнительных задач, таких как создание разделов на дисках и определение сетевых параметров.
- _Узел сети находится в офисе._ Система обновления должна быть способна выполнять задачи в собственной сети узла.
- _Отсутствует необходимость в физическом доступе._ При обновлении ПО нет необходимости в физическом доступе к рабочей станции (что может помешать работе пользователей). Физический  доступ  к  компьютерам автоматизировать нельзя.
- _Узел сети уже используется._ Обновление ПО проводится на машинах, которые используются на протяжении какого-то времени.
- _Узел сети может не находиться в «известном состоянии»._ Поэтому автоматизация должна быть более точной, так как с момента первичной установки в ОС могли возникнуть ошибки.
- _Узел сети может использоваться сотрудниками в процессе обновления._ Некоторые обновления невозможно установить в то время, когда машина используется.
- _Узел сети может отсутствовать._ В эпоху ноутбуков есть большая вероятность того, что узел не присутствует в сети в момент установки обновлений.
- _Узел сети может иметь мультисистемную загрузку._ В эпоху узлов с  мультисистемной  загрузкой  система  обновления,  предназначенная  для настольных компьютеров, должна точно контролировать доступ к нужной ОС.

# 3.1.2.2. Одна, несколько, много

Вы можете снизить риск ошибок обновления, применив метод «одна, несколько, много».

- __Одна.__ Прежде всего установите патч на одну машину. Лучше всего на свою собственную – тогда у вас будет дополнительный стимул все сделать правильно. Если при обновлении возникнут ошибки, вносите в процесс изменения до тех пор, пока он не будет работать на одной машине без ошибок.
- __Несколько.__ Далее попробуйте установить патч на несколько других машин. Если это возможно, стоит протестировать автоматизированный процесс обновления  на  рабочих  станциях  остальных  системных  администраторов, прежде чем задействовать машины пользователей. Системные администраторы проявляют чуть больше понимания. Затем протестируйте систему на нескольких  машинах  дружелюбно  настроенных  к  вам  пользователей  (не системных администраторов).
- __Много.__ Протестировав свою систему и убедившись, что она не уничтожит ничей  жесткий  диск,  начинайте  постепенно  переходить  ко  все  большим и большим группам пользователей, нетерпимых к риску.

# 3.1.3. Конфигурирование сети

Третий компонент, необходимый для сетей, объединяющих большое количество рабочих станций, – это способ автоматизации обновления сетевых параметров– тех считанных битов информации, от которой часто зависит загрузка компьютеров и их объединение в сеть.

Наиболее распространенная система автоматизации этого процесса – DHCP.

# 3.1.3.1. Используйте шаблоны, а не конфигурируйте каждый отдельный узел

Системы DHCP должны иметь систему шаблонов. Некоторые системы DHCP хранят отдельные параметры, присвоенные каждому отдельному узлу сети. Другие системы DHCP хранят шаблоны, описывающие, какие параметры присваиваются узлам различных классов. Преимущество шаблонов в том, что при внесении изменений на множестве узлов вам нужно будет просто изменить шаблон, что значительно лучше, чем прокручивать длинный список узлов сети, пытаясь найти те, которые требуется изменить. Еще одно преимущество в том, что значительно уменьшается вероятность появления ошибки в синтаксисе, если конфигурационный файл генерируется программой. Исходя из того, что шаблоны синтаксически правильны, конфигурация тоже будет верной.

# 3.1.3.2. Когда применять динамическую аренду адресов

Как правило, DHCP назначает отдельный IP-адрес каждому узлу сети. Функция динамической аренды адресов позволяет вам указать диапазон IP-адресов, которые можно присваивать узлам сети. Эти узлы смогут при каждом подключении к сети получать новый IP-адрес. Преимущество в том, что облегчается работа администраторов и повышается удобство для пользователей.

Динамическое распределение следует использовать в случаях, когда много узлов конкурируют за малое количество IP-адресов. Типичная офисная локальная сеть лучше подходит для динамически назначаемой аренды.

Причина для назначения статических IP-адресов – повышение удобства использования файлов журнала. Использование только статических IP-адресов не является достаточной мерой для безопасности.

# 3.1.3.3. Использование DHCP в сетях общего пользования

Многие использовали подобные решения еще до изобретения стандарта 802.1x. Наверняка вы бывали в местах, где сеть была сконфигурирована следующим образом: в сеть выйти очень легко, но можно получить  доступ  только  к  веб-странице  авторизации.  После  авторизации (с помощью либо какого-то способа идентификации, либо платежа с кредитной карты) можно получить полный доступ. В таких ситуациях системные администраторы предпочитают решение plug-in-and-go (подключись-и-работай) для выделения пространства адресов, но при этом должна быть возможность проверки, есть ли у пользователей разрешение на использование ресурсов корпорации, университета или отеля.

# 3.1.4. Старайтесь не использовать динамический DNS -сервер с DHCP

Старайтесь не допускать ситуаций, в которых простые ошибки одних пользователей могут помешать работе других. Архитекторы локальной сети давно поняли это в отношении разрешения клиентам самим устанавливать IP-адреса. И нам не стоит повторять эту ошибку, позволяя клиентам выбирать собственные имена узлов. До появления DHCP пользователи часто «вешали» локальную сеть, случайно устанавливая IP-адрес, аналогичный IP-адресу маршрутизатора.

Использование DHCP в значительной мере снижает шанс повторения подобной ситуации. Разрешение клиентам устанавливать собственное имя узла – один из вариантов той же ситуации, который приведет к подобным результатам.

Динамический DNS-сервер с DHCP создает систему, которая является более запутанной, более сложной для управления, более подверженной сбоям и менее безопасной.

Ограничение распространения означает ограничение риска безопасности таким образом, чтобы он распространялся только в пределах определенной области. Рекомендуем ограничивать динамический DNS-сервер определенными сетевыми субдоменами, от которых не требуется высокая надежность.

# 3.1.4.1. Управление сроками аренды DHCP

Управление сроками аренды может помочь в распределении обновлений. DHCP-клиентам задается определенный набор параметров, который будет использоваться в течение определенного периода времени. По истечении этого периода они должны обновить свою аренду. Изменения вносятся во время обновления.

# 3.2. Тонкости

Как правило, рабочие станции – самые распространенные машины в компании. Любое, даже незначительное снижение нагрузки на поддержку рабочих станций имеет огромное значение.

# 3.2.1. Полная уверенность в завершении

Существуют автоматизированные процессы, но помимо этого есть и автоматизация процесса. Если мы абсолютно уверены в процессе, мы избавлены от необходимости беспокоиться об ошибках.

# 3.2.2. Вовлечение пользователей в процесс стандартизации

В идеале пользователи должны принимать участие в процессе разработки с самого начала. Назначенные представители или заинтересованные руководители могли бы выбирать приложения, которые будут включены в конфигурацию. Для каждого приложения составляется соглашение об уровне обслуживания, в ко-тором описывается уровень обслуживания со стороны системных администраторов. Новые версии ОС и приложений отслеживаются и одобряются. Контролируемое внедрение новых версий аналогично описанному автоматизированному процессу обновления.

Однако в реальности платформы контролируются либо руководством,  либо отделом системного администрирования, отвечающим за предоставление основной платформы, которую пользователи могут настраивать под себя. В первом случае примером может служить офис приема заказов по телефону, где операторы работают со строго определенным набором приложений. Системные администраторы совместно с руководством определяют, какие именно приложения будут установлены, когда именно будет проведено обновление и т. д.

Вторые случаи более распространенны. В одной сети стандартной платформой для персонального компьютера считается его операционная система; самые необходимые приложения; приложения, требуемые компанией-учредителем; утилиты, которые наиболее часто просят установить пользователи и которые можно лицензировать оптом. Такая среда является очень открытой.

Для некоторых приложений предусмотрены более формальные процессы.

# 3.2.3. Разнообразие стандартных конфигураций

Чем больше стандартных конфигураций используется в корпоративной сети, тем труднее все их обслуживать. Один из способов создать большое количество разнообразных конфигураций – использовать для всех конфигураций один и тот же сервер и механизмы, вместо того чтобы выделить отдельный сервер для каждого стандарта. Однако можно потратить время и создать единую обобщенную систему, способную производить множественные конфигурации и поддаваться масштабированию.

Общее понятие управляемых стандартизированных конфигураций часто носит название «управление конфигурацией программного обеспечения»(Software Configuration Management, SCM). Этот процесс относится как к серверам, так и настольным компьютерам.

Стандартные конфигурации также могут облегчить процесс обновления ОС.

# 3.3. Заключение

Настольные компьютеры, в отличие от серверов, как правило, развертываются в больших количествах, и все они обладают практически одной и той же конфигурацией. У каждого компьютера есть свой жизненный цикл, который начинается с установки ОС и заканчивается в тот момент, когда машину выключают в самый последний раз. В этот период программное обеспечение компьютера постепенно приходит в негодность в результате энтропии, обновляется и заново переустанавливается в начале нового цикла. В идеале все узлы сети, относящиеся к определенной платформе, в начале своего жизненного цикла должны иметь одну и ту же конфигурацию. Обновляться они должны параллельно. Некоторые стадии жизненного цикла важнее для пользователей, чем другие. Мы стремимся увеличить продолжительность более важных стадий и сократить продолжительность менее значительных.

Основу всего, чему посвящена данная глава, составляют три процесса:

1.	Первичная установка ОС должна быть автоматизирована.
2.	Обновление программного обеспечения должно быть автоматизировано.
3.	Конфигурация сети должна администрироваться централизованно с помощью такой системы, как DHCP.

Эти три задачи имеют критическое значение для экономного управления. Грамотное их выполнение позволит всем последующим процессам проходить более гладко.
