Итак стоит задача например на двух хостах (двух слейвах) собрать мавеном джава приложение (слейв-1) и развернуть его (слейв-2)
На первом необходимо установить мавен и гит. На втором томкат и задеплоить туда получившийся артефакт.
1. В домашнем каталоге мастера создать папку roles и перейти туда
mkdir roles
cd roles
2. Создать роль для сборочного хоста
ansible-galaxy init build
3. Перейти в директорию build/default и в ней добавить в main.yml следующее содержание:
https://github.com/summerinstockholm/ansible_galaxy_boxfuse/blob/main/build/defaults/main.yml
4. Перейти в директорию build/tasks и в ней добавить в main.yml следующее содержание:
https://github.com/summerinstockholm/ansible_galaxy_boxfuse/blob/main/build/tasks/main.yml
3. Создать роль для хоста на котором будем деплоить Java артефакт
ansible-galaxy init deploy
4. Перейти в директорию deploy/default и в ней добавить в main.yml следующее содержание:
https://github.com/summerinstockholm/ansible_galaxy_boxfuse/blob/main/deploy/defaults/main.yml
5. Перейти в директорию deploy/handlers и в ней добавить в main.yml следующее содержание:
https://github.com/summerinstockholm/ansible_galaxy_boxfuse/blob/main/deploy/handlers/main.yml
6. Перейти в директорию deploy/tasks и в ней добавить в main.yml следующее содержание:
https://github.com/summerinstockholm/ansible_galaxy_boxfuse/blob/main/deploy/tasks/main.yml
7. Создать результирующий плейбук на уровне директории с ролями со следующим содержанием:
https://github.com/summerinstockholm/ansible_galaxy_boxfuse/blob/main/roles.yml
8. Запустить в директории с ролями результирующий плейбук:
ansible-playbook roles.yml