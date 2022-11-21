# Code Block for Volto (@plonegovbr/volto-code-block)

Addon implementing a code block with syntax highlight for [Plone](https://plone.org) projects with [Volto](https://github.com/plone/volto).

[![npm](https://img.shields.io/npm/v/@plonegovbr/volto-code-block)](https://www.npmjs.com/package/@plonegovbr/volto-code-block)
[![](https://img.shields.io/badge/-Storybook-ff4785?logo=Storybook&logoColor=white&style=flat-square)](https://plonegovbr.github.io/volto-code-block/)
[![Code analysis checks](https://github.com/plonegovbr/volto-code-block/actions/workflows/code.yml/badge.svg)](https://github.com/plonegovbr/volto-code-block/actions/workflows/code.yml)
[![Unit tests](https://github.com/plonegovbr/volto-code-block/actions/workflows/unit.yml/badge.svg)](https://github.com/plonegovbr/volto-code-block/actions/workflows/unit.yml)

## Screenshots

### Code Block with Dark style

<img alt="Screenshot" src="./docs/block-dark.png" width="500" />

### Code Block with Light style

<img alt="Screenshot" src="./docs/block-light.png" width="500" />

## Examples

@plonegovbr/volto-code-block can be seen in action at the following sites:

- [Plone Brasil](https://plone.org.br)

You can also check its [Storybook](https://plonegovbr.github.io/volto-code-block/).

## Install

### New Volto Project

Create a Volto project

```shell
npm install -g yo @plone/generator-volto
yo @plone/volto my-volto-project --addon @plonegovbr/volto-code-block
cd my-volto-project
```

Install new add-on and restart Volto:

```shell
yarn install
yarn start
```

### Existing Volto Project

If you already have a Volto project, just update `package.json`:

```JSON
"addons": [
    "@plonegovbr/volto-code-block"
],

"dependencies": {
    "@plonegovbr/volto-code-block": "*"
}
```

### Configure language available in block setting

You can specify the language available in the setting by changing in you config.js (or index.js) by modify the list in `config.settings.codeBlock.languages`. Each item of the list is compose of a list :
* index 0 : language id
* index 1 : language title
* index 2 : module use for syntax highlight import from `react-syntax-highlighter/dist/cjs/languages/hljs`

Exemple:
```javascript
import bash from 'react-syntax-highlighter/dist/cjs/languages/hljs/bash';
import css from 'react-syntax-highlighter/dist/cjs/languages/hljs/css';
import dockerfile from 'react-syntax-highlighter/dist/cjs/languages/hljs/dockerfile';
import javascript from 'react-syntax-highlighter/dist/cjs/languages/hljs/javascript';
import json from 'react-syntax-highlighter/dist/cjs/languages/hljs/json';
import less from 'react-syntax-highlighter/dist/cjs/languages/hljs/less';
import markdown from 'react-syntax-highlighter/dist/cjs/languages/hljs/markdown';
import nginx from 'react-syntax-highlighter/dist/cjs/languages/hljs/nginx';
import python from 'react-syntax-highlighter/dist/cjs/languages/hljs/python';
import scss from 'react-syntax-highlighter/dist/cjs/languages/hljs/scss';
import yaml from 'react-syntax-highlighter/dist/cjs/languages/hljs/yaml';
import xml from 'react-syntax-highlighter/dist/cjs/languages/hljs/xml';

const applyConfig = (config) => {
    config.settings['codeBlock'] = {
        languages: [
        ['bash', 'Bash', bash],
        ['css', 'CSS', css],
        ['dockerfile', 'Dockerfile', dockerfile],
        ['javascript', 'Javascript', javascript],
        ['json', 'JSON', json],
        ['less', 'LESS', less],
        ['markdown', 'Markdown', markdown],
        ['nginx', 'nginx', nginx],
        ['python', 'Python', python],
        ['scss', 'SCSS', scss],
        ['yaml', 'Yaml', yaml],
        ['xml', 'XML', xml],
        ],
    };

    return config;
};

export default applyConfig;
```

### Test it

Go to http://localhost:3000/

## Credits

The development of this add on was sponsored by the Brazilian Plone Community

[![PloneGov-Br](docs/plonegovbr.png)](https://plone.org.br/)
