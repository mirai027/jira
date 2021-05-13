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
