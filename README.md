# Import/Export

## Легенда

Вы успешно настроили загрузку модулей с Webpack и сборку приложения. Пришло время всё грамотно разделить на модули!

## Описание

Разделите всё приложение на модули:
1. Модуль Domain - где будет храниться логика предметной области (персонажи, атаки и т.д.)
3. Модуль Game - отвечающий за работу приложения (загрузку и сохранение)
4. Модуль App - отвечающий за запуск приложения

Заглушки для модулей:

файл `domain.js`:
```javascript
class Character {
}
```

файл `game.js`
```javascript
class Game {
  start() {
    console.log('game started');
  }
}

class GameSavingData {
}

function readGameSaving() {
}

function writeGameSaving() {
}
```

файл `app.js`
```javascript
const game = new Game();
game.start();
```

Организуйте:
1. Из модуля `domain` экспорт класса `Character` в качестве `default`'ного
1. В модуле `game` импорт класса `Character`
1. Экспорт из модуля `game` класса `Game` в качестве дефолтного, класса `GameSavingData` и функций `readGameSaving` и `writeGameSaving`
1. В модуле `app.js` одним импортом импортируйте `Game`, `GameSavingData` и функции `readGameSaving`, `writeGameSaving` (их при импорте переименуйте в `loadGame` и `saveGame` соответственно)

С самими функциями и классами ничего делать не нужно, нужно только правильно расставить инструкции `import`/`export`.