# Задача №1

За основу берем ранее сверстанный макет: https://www.figma.com/design/gbFVsmFWfYr8vvzkWR6SPD/JS-TASK-%231?node-id=0-1&node-type=canvas&t=VeDLWK2d1yDnIvBO-0

##  Задача
1) Изначально на экране не должно быть карточек с фактами, только кнопка "+"
2) При нажатии на "+" должна добавляться случайная карточка из массива facts в card.json 
3) При нажатии на "-" в карточке, она должна удаляться
4) Факты не могут повторяться
5) При заполнении всех фактов (10 штук) кнопка "+" убирается и остается возможность только удалить факты
6) Состояние фактов должно сохраняться при обновлении страницы и сбрасываться при открытии в новой вкладке

### Содержание файла card.json (нужно создать и добавить в проект)
```
{
  "status": 200,
  "data": {
    "facts": [
      "CSS помогает стилизовать страницы",
      "Vue оптимизирует рендеринг компонентов",
      "Flexbox упрощает выравнивание элементов",
      "Webpack собирает фронтенд-проекты",
      "JavaScript добавляет интерактивность страницам",
      "HTML создаёт структуру веб-документов",
      "TypeScript улучшает читаемость кода",
      "UI/UX влияет на пользовательский опыт",
      "REST API связывает фронтенд и бэкенд",
      "Браузеры интерпретируют HTML и CSS"
    ]
  }
}
```
## Как лучше разбить решение на подзадачи
1) В коде получить доступ к информации из .json (полученный массив просто вывести в консоль)
2) На основе полученных данных отрисовать сразу все карточки (изначально просто будет пустой div в котором должны будут храниться карточки и для каждого элемента в массиве фактов нужно создать ребенка (карточку) и добавить его в этот div)
3) Как отрисовывать карточки выборочно (создать еще 1 массив, activeFacts который будет отображать не все факты которые есть, а только активные) (чтобы проверить что все получилось в activeFacts тестово закинуть со старта пару названий)
4) Продумать механизм добавления и перерисовки контейнера с карточками, шаги:
4.1)  Удалить всех детей у контейнера
4.2) Добавить в activeFacts новый факт
4.3) На основе activeFacts заново отрисовать их на экране обновленные факты
4.4) Если нужно, отрисовать "+" для добавления нового факта
5) Продумать механизм Удаления карточки (сложность в том, чтобы определить, какую именно карточку нужно удалить. для этого рекомендуется добавить слушатель 'click' на этапе создания карточки, чтобы можно было аргументом передать текст, и уже потом на основе этого текста будет удаляться нужная карточка)
6) Продумать как можно сохранить состояние карточек (сохранять состояние карточек при перерисовке, получать состояние карточек из хранилища при начальной загрузке)
