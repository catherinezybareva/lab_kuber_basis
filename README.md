# lab_kuber_basis №9
1. Для начала необходимо установить minikube на нашу ВМ
 
  а) Скачиваем и инсталлируем minikube
  
  б) Добавляем себе права
  
  в) Отключаем своп
  <img width="840" height="671" alt="image" src="https://github.com/user-attachments/assets/91043687-e684-417d-a2b9-5cfa3a08fe4f" />
  г) Запускаем minikube в режим однонодового кластера k8s
    <img width="834" height="199" alt="image" src="https://github.com/user-attachments/assets/500c9bf3-af05-4771-a2c1-1ad4c2ae0473" />
    <img width="848" height="198" alt="image" src="https://github.com/user-attachments/assets/5dc3e9b9-dacb-4661-bd92-f57695d1d705" />

2. Проверка minikube и k8s кластера на ВМ

   <img width="721" height="169" alt="image" src="https://github.com/user-attachments/assets/e5aefea4-e51c-493f-9165-0bed2e2f0235" />

3. Модифицируем приложение flask, т.е. добавляем вывод имени реплики приложения на веб-страницу

   <img width="1071" height="432" alt="image" src="https://github.com/user-attachments/assets/07ac9f9d-ec64-4eb7-b60e-0409980fd762" />

4. Готовим образы контейнеров и делаем их доступными в кластере k8s
    а) Производим сборку образа из исходников прямо внутри minikube
    <img width="961" height="422" alt="image" src="https://github.com/user-attachments/assets/dcbbb4c9-e19f-414b-ae4e-575ce89d1223" />

   б) Загружаем готовый образ redis внутрь кластера и просматриваем, что образы доступны

   <img width="796" height="303" alt="image" src="https://github.com/user-attachments/assets/7216e628-2290-41c0-8bb5-01ee931698c0" />

5. Готовим манифесты /flask_redis_k8s/flask.yml, /flask_redis_k8s/flask-service.yml, /flask_redis_k8s/redis.yml, /flask_redis_k8s/redis-service.yml

6. Применяем манифесты k8s, проверяем статус реплик и сервисы

   <img width="855" height="143" alt="image" src="https://github.com/user-attachments/assets/2e4e8a10-35a9-4adb-81dd-583dac4ac722" />
    <img width="676" height="214" alt="image" src="https://github.com/user-attachments/assets/c7fbaa64-f7b8-455a-9e10-bbb9aad08cf7" />
    <img width="895" height="153" alt="image" src="https://github.com/user-attachments/assets/a08b5767-286b-4e4a-8a91-2f95c99841fb" />

7. Производим проверку доступности вебсайта, предварительно запустив в отдельном окне терминала проброс трафика ВМ внутрь minikube

   <img width="1280" height="364" alt="image" src="https://github.com/user-attachments/assets/38282d6a-ee76-4b12-b93a-b406b2d7222b" />

8. Далее необходимо обновить приложение на новую версию

    <img width="622" height="494" alt="image" src="https://github.com/user-attachments/assets/57a79cb3-de77-4069-965f-9d1a23cf4ff9" />

9. Обновляем файл манифеста и применяем его заново

    <img width="951" height="240" alt="image" src="https://github.com/user-attachments/assets/985b2881-7c1a-403f-8a9c-8dda925f984a" />

10.   Затем необходимо пропатчить описание, а также видим как пересоздаются реплики подов

      <img width="872" height="621" alt="image" src="https://github.com/user-attachments/assets/4a685c26-73b1-48cd-9472-4e5f62832f8b" />
      <img width="859" height="79" alt="image" src="https://github.com/user-attachments/assets/fee7a3b5-7dcd-41eb-8fa8-8b23e6ac83e6" />

11. В конце проверяем обновленную версию нашего веб-сервиса

    <img width="1280" height="350" alt="image" src="https://github.com/user-attachments/assets/84d7815d-2be7-4ddc-9481-953739a6202f" />

12. Ну и видим, как заменяются старые версии подов на новые

   <img width="871" height="302" alt="image" src="https://github.com/user-attachments/assets/356e93e5-d323-40e2-a80f-b8ab9ce4331a" />
    <img width="1166" height="427" alt="image" src="https://github.com/user-attachments/assets/182e3010-3d95-4cb9-be59-28ee8e62e61c" />
