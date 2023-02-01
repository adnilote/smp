# Cryptochat with Social Millionaire protocol
https://bitbucket.org/Enr1g/p2p_mpotr.js/src


## Zero-knowledge proof in cryptographic group chat authentication - Nguyen Linda


The paper considers the problem of authentication users for cryptographic group communication chats, built on the basis of asymmetric encryption systems, the main vulnerability of which is the possibility of substituting the public key one of the participants to another public key with a secret known to the adversary
half of this key ("man in the middle" attack). In such cases Diffie-Hellman type protocols are not applicable for a reliable solution authentication tasks, and in various systems use additional layer of authentication using algorithms for solving problems with zero-knowledge proof (ZKP). Zero-knowledge proof is an interactive probabilistic protocol that allows one of the parties (the Inspector) to verify the authenticity of some statement, without providing the second party (Proving) proof statements about the assertion itself.

The work investigated the Socialist Millionaire Protocol (SMP), allowing two users authenticate each other with a shared password [1]. Originalthe protocol of socialist millionaires makes it possible to check the knowledge of some each other's secret without disclosing any information about this secret, which allows you to resist the attack of the man in the middle.

The paper proposed a modification of the protocol for the case of N clients, where N > 2. The main idea of the protocol is the transitivity of authentication: if the first party authentic for the second, and the second for the third, then the first is authentic for the third. This assumption is valid, since the authenticity of the participant is determined by his knowledge of the password, which the participants in the conversation agreed on, so the case when the participant decides to share the password with another person is not considered. The proposed authentication algorithm is as follows: the participants organize a directed ring and initiate the authentication of the next participant using the socialist millionaire protocol. Depending on the authentication result, the verified participant is stored in the table of trusted users or a table of violators and send the tables to all participants. The user updates his tables of trusted and violators only if he
Receives authentication results from trusted users. Thus, the participant receives information about the authenticity of other users,
without authenticating them yourself. The participant authenticates the next unauthenticated participant until a successful authentication initialization is performed. After that, the participant will only work on receiving messages and updating tables. The algorithm ends when the authenticity of all participants is known.

### Results
The proposed group mutual authentication algorithm was implemented for the distributed cryptographic group communication chat mpOTR -https://bitbucket.org/Enr1g/p2p_mpotr.js/src, developed in Laborotory of Information Security at Moscow State Universtiry [2]. To evaluate experimentally the convergence time of the algorithm, testing was carried out for a different number of participants and its comparative analysis with a simple implementation of the millionaire socialist protocol for a group, in which each participant authenticates each. An experimental study showed the effectiveness of using the proposed circular authentication protocol, the gain in speed is about 3 times compared to another algorithm. An analysis of the stability of such an authentication protocol to the most obvious attacks was also carried out.

----

В работе рассматривается задача взаимной аутентификации
пользователей для криптографических чатов групповых коммуникаций, по-
строенных на основе асимметричных шифрсистем, основной уязвимостью ко-
торых является возможность осуществления подмены открытого ключа одно-
го из участников на другой открытый ключ с известной противнику секрет-
ной половиной этого ключа (атака человек в середине). В таких случаях
протоколы типа Диффи-Хеллмана не применимы для надежного решения
задачи аутентификации, и в различных системах используют дополнитель-
ный слой аутентификации с помощью алгоритмов решения задач с нулевым
разглашением (ZKP - zero knowledge problem). Доказательством с нулевым
разглашением называется интерактивный вероятностный протокол, который
позволяет убедиться одной из сторон (Проверяющему) в достоверности неко-
го утверждения, без предоставления второй стороне (Доказывающей) дока-
зательств о самом утверждении.

В работе был исследован протокол SMP Socialist Millionaire Protocol,
или протокол миллионеров-социалистов, позволяющий двум пользователям
аутентифицировать друг друга с помощью общего пароля [1]. Оригинальный
протокол миллионеров-социалистов позволяет проверить знание некоторого
секрета друг у друга, не разглашая никакой информации об этом секрете,
что позволяет противостоять атаке ѕчеловека в середине.

В работе была предложена модификация протокола для случая N клиен-
тов, где N > 2  протокол круговой аутентификации. Основная идея протокола заключается в транзитивности аутентификации: если первый участник
аутентичен для второго, а второй для третьего, то первый аутентичен для третьего. Данное предположение допустимо, так как аутентичность участника определяется его знанием пароля, о котором договорились участники беседы, поэтому случай, когда участник решит поделиться с другим человеком паролем не рассматривается. Алгоритм круговой аутентификации заключается в следующем: участники организуют ориентированное кольцо и инициирует аутентификацию следующего за ним участника с помощью протокола миллионеров-социалистов. В зависимости от результата аутентификации сохраняют проверенного участника в таблицу доверенных пользователей
или таблицу нарушителей и рассылают таблицы всем участникам. Пользователь обновляет свои таблицы доверенных и нарушителей только если полу-
чает результаты аутентификации от доверенных пользователей. Таким образом участник получает информацию об аутентичности других пользователей,
не аутентифицировав их самим. Участник аутентифицирует следующего не аутентифицированного участника до тех пор, пока не будет проведена успешная инициализация аутентификации. После этого участник будет работать только на прием сообщений и обновление таблиц. Алгоритм завершается, когда аутентичность всех участников становится известна.

Предложенный алгоритм групповой взаимной аутентификации был реализован для распределенного криптографического чата групповых коммуникаций mpOTR, разрабатываемого в ЛБИС [2]. Для оценки экспериментально время сходимости алгоритма было проведено тестирование для различного числа участников и его сравнительный анализ с простой реализацией протокола миллионеров-социалистов для группы, при которой каждый участник аутентифицирует каждого. Экспериментальное исследование показало эффективность использования предложенного протокола круговой аутентификации  выигрыш в скорости работы примерно в 3 раза по сравнению с другим алгоритмом. Так же был проведен анализ устойчивости такого протокола аутентификации к наиболее очевидным атакам.
