# Running import-js in Emacs

1. Install import-js
  * `gem install import-js`
2. Configure import-js
  * See [Configuration](README.md#configuration)
2. Install import-js.el for Emacs
  * Install via [MELPA](https://melpa.org/#/import-js)
  * Alternatively, Copy plugins/import-js.el into your Emacs load-path and add
    `(require 'import-js)` to your config
3. Configure your project root
  * `(setq import-js-project-root "/path/to/project")`
4. Start the import js project
  * `(M-x) run-import-js`
5. Import a file!
  * You can use something like `(M-x) import-js-import` with your cursor over
    the desired module
  * It will be helpful to bind `import-js-import` to an easy-to-use binding,
    such as:

    ```
    (define-prefix-command 'my-keymap)
    (global-set-key (kbd "s-a") 'my-keymap)
    (define-key my-keymap (kbd "a u") 'import-js-import)
    ```
6. Go directly to a file
  * The import-js goto interface allows us to jump to a package
  * `(M-x) import-js-goto` will jump to the appropriate file found by import-js
  * This should also be bound to something useful:
    `(global-set-key (kbd "<f4>") 'import-js-goto)`
7. Fix your imports
  * Optionally, you can configure import-js to fix your imports for you, adding
    unknown variables and removing unused imports. import-js uses eslint to find
    these variables.
  * `eslint` must be in your PATH.
  * eslint plugins must be installed for that specific version of eslint (if
    eslint is a global eslint, you may need to install the plugins globally)
  * Run with `(M-x) import-js-fix`
  * You can also configure `import-js-fix` to run on save:
    `(add-hook 'after-save-hook 'import-js-fix)`
