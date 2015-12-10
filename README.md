### Frontend Precommit Rules
Se trata de un conjunto de reglas que han de cumplirse **antes** de poder comitear nuestro código. Esta sesión está basada en las [Frontend Pre-commit Rules](https://github.com/scm-spain/frontend-pre-commit-rules) de Schibsted Engineers.

### Slides
Accede a las slides [aquí](http://davecarter.github.io/frontend-hangout/#/).

#### Para que sirven:

- Mejorar la calidad del código en un equipo
- Normalizar el estilo y las buenas prácticas personales.

#### Cual elegir?

- No existe una fórmula mágica
- Consensuar reglas entre miembros del equipo.

#### Cómo funcionan?

- Precommit Hook
- Otros tipos: Pre-Push Hook

#### Cómo la añado a mi proyecto?

Instalación manual:
Las FPCR están basadas en Eslint y Sass-lint (Ruby Gem)

- Creamos un proyecto nuevo:
```
$ npm init
```

- Inicializamos un repo Git:
```
$ git init
```
- Creamos un archivo .gitignore
```
// https://www.gitignore.io/  => [node][osx]
$ touch .gitignore
```

- Añadimos Git URL:
```
$ git remote ad origin ...
```

- Añadimos Dependencia NPM de las Precommit Rules:
```
$ npm i @schibstedspain/frontend-pre-commit-rules --save-dev
```

- Añadimos dependencias de linters:
```
$ npm i eslint eslint-plugin-react babel-eslint node-sass --save-dev

```

- Comprobamos instalación de Sass (Ruby)

- Añadimos pre-commit Hook al package.json:
```
  "pre-commit": [
    "lint"
  ]
```

- Añadimos los Scripts de linting asociados dentro de "scripts"
```
"lint": "npm run lint:eslint && npm run lint:sass",
"lint:eslint": "eslint --ext=.js --ext=.jsx ./src/ ./test/ ./docs/",
"lint:sass": "scss-lint src/"
```

- Añadimos resto de archivos del proyecto
- Probamos comitear archivos.

Instalación con Yeoman Generator

- Instalamos el Generador de forma Global:
```
npm install -g @schibstedspain/generator-sui-react
```
- Lo ejecutamos para instalar entorno
```
yo @schibstedspain/sui-react
```

#### Sobre Eslint
- [Eslint](http://eslint.org/)
- [Integraciones](http://eslint.org/docs/user-guide/integrations)
- Language options
- Parser (Babel)
- Rules ... ejemplos
- Archivo de configuración: .eslintrc.json
- [Linter Demo](http://eslint.org/demo/)

- Linting [React](https://github.com/yannickcr/eslint-plugin-react)

#### Sobre SASS
- [Integración con Editores de código](https://github.com/brigade/scss-lint#editor-integration)
- Sublime Text Plugin: [SublimeLinter-scss-lint](https://packagecontrol.io/packages/SublimeLinter-contrib-scss-lint)
- [Documentación Linters](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md)

### Caso práctico
- Crear un componente de React y ver funcionamiento del linter.
- Ver errores linting.
- Debuggar y solucionar errores/warnings.
- Lintar sólo SASS o sólo JS.
- Personalizar tus linting rules.

