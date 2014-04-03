## 1.0.1

-  Поддержка `borschik.link()` в node.js.

## 1.0.0

- borschik теперь версионируется по semver.
- [Добавили поддержку wildcard для freeze_path](https://github.com/bem/borschik/issues/23). Это изменение ломает совместимость со старым поведением:
  - путь для фриза теперь относителен конфига `.borschik`, как и все остальные опции (`paths`, `follow_symlinks`)
  - вместо пути `./images` теперь надо писать `./images/**`. Например
  ```json
  "freeze_paths": {
        "./static/images/**": "./static/freeze"
  }
  ```
  т.е. все ресурсы из static/images будут зафрижены в static/freeze. Раньше надо было писать вот так
  ```json
  "freeze_paths": {
        "./static/images": "../freeze"
  }
  ```

- Добавили [поддержку для фриза во вложенные папки](https://github.com/bem/borschik/blob/master/docs/freeze/freeze.en.md#nesting-level).
- Добавили [новый параметр](https://github.com/bem/borschik/pull/56) --tech-options "<json>" для передачи любых параметров в технологию.
- Для инклюда js-файлов добавили [новый синтаксис](https://github.com/bem/borschik/pull/48) borschik.include('./path/to/file.js').

## 0.4.2

- Добавили поддержку инлайнинга jpg-файлов.
- Обновили зависимости: csso@1.3.10, uglify-js@2.4.6, vow@0.3.12.

## 0.4.1

- Добавили поддержку инлайнинга ttf-файлов.
- Добавили [вывод результатов в stdout при неудачной минификации](https://github.com/bem/borschik/issues/28).

## 0.4.0
Эта версия частично несовместима с 0.3.x.

- Обновили систему плагинов. Подробнее см. в [документации](https://github.com/bem/borschik/blob/master/docs/where-is-my-tech/where-is-my-tech.en.md).
- Добавили [поддержку инлайнинга ресурсов](https://github.com/bem/borschik/issues/9). Подробнее см. в [документации](https://github.com/bem/borschik/blob/master/docs/freeze/freeze.en.md#resource-inlining).
- Обновили [нотация js-include](https://github.com/bem/borschik/issues/16). Подробнее см. в [документации](https://github.com/bem/borschik/blob/master/docs/js-include/js-include.en.md).
- Для промисов используется [vow](https://github.com/dfilatov/jspromise) вместо [q](https://github.com/kriskowal/q).
- Удалены устаревшие технологии: `css-fast` и `js-link`.
- Технология `json-links` переименована в `json`.
- [OmetaJS](https://github.com/bem/borschik-tech-css-ometajs) и [CoffeeScript](https://github.com/bem/borschik-tech-js-coffee) вынесены из основного репозитория в плагины.
- Исправлены проблемы с freeze в технологии html ([#30](https://github.com/bem/borschik/issues/30), [#39](https://github.com/bem/borschik/issues/39)).
- UglifyJS обновлен до 2.4.0.

## 0.3.5
- Исправлена регрессия после https://github.com/bem/borschik/issues/7.

## 0.3.4
[Список задач к релизу 0.3.4](https://github.com/bem/borschik/issues?milestone=3&state=closed).

- [Исправлено поведение follow_symlinks](https://github.com/bem/borschik/issues/7).
- [Технология CSS удаляет дублирующие @import](https://github.com/bem/borschik/issues/4).
- Обновлена документация на русском и английском языках.

## 0.3.3
Обновлены зависимости:

- coa ~0.4.0
- inherit ~1.0.4
- q ~0.9.5
- ometajs ~3.2.4
- uglify-js ~2.3.6
- istanbul ~0.1.42
- mocha ~1.12.0

## 0.3.2
- UglifyJS обновлен до ~2.3.
- CSSO обновлен до 1.3.7.
- Исправлена проблема с freeze и mkdir (https://github.com/veged/borschik/issues/90).
- Объеденены технологии `js` и `js-link`. `js-link` устарела и будет удалена.

## 0.3.1
- Исправлены проблемы совместимости с Windows.