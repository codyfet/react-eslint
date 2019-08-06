# react-eslint
Содержит пример минимальной конфигурации eslint для разработки на react.

Для примера настройки eslint используется workspace, описанный здесь https://github.com/codyfet/react-workspace (router)

Установка и настройка eslint.

Установить eslint
```
npm --save-dev install eslint
```

Установить eslint-loader для webpack
```
npm --save-dev install eslint-loader
```

Настроить установленный лоадер в webpack.config.js
```
{
    test: /\.js$/,
    exclude: /node_modules/,
    use: ["babel-loader", 'eslint-loader']
}
```

Создать файл с настройками для eslint
```
touch .eslintrc
```

Содержимое .eslintrc
```
{
  "rules": {}
}
```

Установить babel-eslint (babel-loader должен быть уже установлен)
```
npm install --save-dev babel-eslint
```

Установить в настройках .eslintrc опцию parser
```
{
    "parser": "babel-eslint",
    "rules": {}
}
```

Теперь можно писать правила в секции rules в файле настройках .eslintrc
Полный список доступных правил см. http://eslint.org/docs/rules/

Установить плагин для настройки eslint правил для react
```
npm --save-dev install eslint-plugin-react
```

Изменить файл с настройками .eslintrc и добавить правила из плагина
Настроить окружение (browser и node)
Настроить применение дефолтных (рекомендуемых) правил 
```
{
    "parser": "babel-eslint",
    "plugins": [
        "react"
    ],
    "rules": {},
    "extends": [
        "eslint:recommended",
        "plugin:react/recommended"
     ],
     "env": {
         "browser": true,
         "node": true
     }
}
```

После того, как эти шаги были выполнены, необходимо запустить команду
```
npm run start
```
