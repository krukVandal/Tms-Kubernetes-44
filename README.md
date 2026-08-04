# Цель: Углубленное изучение основных концепций Kubernetes, связанных с Namespaces, Pods и Controllers.

<img width="1358" height="841" alt="image" src="https://github.com/user-attachments/assets/0c14d49d-49d7-4594-98cd-137a65929b3c" />

Для наглядности решения задачи создаю 2 namespace и 3 разных контроллера и отдельный под.

В скриншоте выше kind Pod основная проблема такого решения -- если что-то случится с подом или насильно удалить его без контроллера он больше не поднимется

<img width="1411" height="846" alt="image" src="https://github.com/user-attachments/assets/154b67fb-5952-414d-b0c3-157e6ad990d5" />

Здесь несколько контроллеров в чем основная разница между ними:
- Deployment полностью автоматический контроллер который внутри создает replicaset и версирование что гибко позволяет плавно обновлять версии подов
- Replicaset делает все тоже самое 2 реплики но не имеет на борту истории версий внутри busybox который просто спит
- Service и statefulset и ему требуется ClusterIP для балансировки но здесь вставлена заглушка NONE и еще в отличии от контроллеров выше он может получать приятные глазу имена

<img width="1148" height="731" alt="image" src="https://github.com/user-attachments/assets/e70b1ddd-e866-4c5d-a2d6-65dc9b5395f2" />
