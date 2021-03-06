# Структура CSS

## Один Компонент на файл
Разместите каждый Компонент в его собственном файле.

  ```scss
  /* css/components/search-form.scss */
  .search-form {
    > .button { /* ... */ }
    > .field { /* ... */ }
    > .label { /* ... */ }

    // Варианты
    &.-small { /* ... */ }
    &.-wide { /* ... */ }
  }
  ```

## Используйте общую папку
Тогда в sass-rails и stylus, их можно включать очень просто:

  ```scss
  @import 'components/*';
  ```

## Избегайте большой вложенности
Используйте не более 1 уровня вложения. Очень просто потеряться, имея большую вложенность.

  ```scss
  /* ✗ Избегайте это: 3 уровня вложенности */
  .image-frame {
    > .description {
      /* ... */

      > .icon {
        /* ... */
      }
    }
  }

  /* ✓ Прекрасно: 2 уровня */
  .image-frame {
    > .description { /* ... */ }
    > .description > .icon { /* ... */ }
  }
  ```
