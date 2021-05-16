## CI

- yarn add --dev --exact prettier

- echo > .prettierrc.json

- touch .prettierignore

  - \# Ignore artifacts:
  - build
  - coverage

- yarn add eslint-config-prettier -D

- add `"prettier"` to the "extends" array in your `.eslintrc.*` file. Make sure to put it **last,** so it gets the chance to override other configs.

  - ```json
    {
      "extends": ["some-other-config-you-use", "prettier"]
    }
    ```

- npx mrm lint-staged

- yarn add @commitlint/config-conventional @commitlint/cli -D

- echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js

- npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'

## Mock

- 本地写死 JSON
  - 和其他方案比 Mock 效果不好。
  - 与真实 Server 环境的切换非常麻烦，一切需要侵入代码切换环境的行为都是不好的。
- Mock.js
  - 不维护了
- yapi, swagger
  - 配置复杂，依赖后端
- json-server
  - 自定义程度高，一切尽在掌控中。
  - 增删改查真实模拟
  - ~~与接口管理工具相比，无法随着后端 API 的修改而自动修改。~~

## Custom Hook

## TypeScript

- string, number, boolean, array, any, unknown, null, undefined, never, object, void, tuple, enum
- 类型推断
- .d.ts
  - 业务代码一般不会用上。一般都是在编写 js 库的时候，另外写一个 @type/xxx 来补上类型
