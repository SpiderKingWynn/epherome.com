# 对 Epherome 进行本地化/国际化

Epherome代码中有一个国际化系统。您可以在Epherome的常规设置中修改*显示语言*。

## 简介

关于本地化/国际化系统的代码位于 `src/intl`。

- `src/intl/index.ts` 是该系统的核心实现。
- `src/intl/root.ts` 是*英语（全球）*（`en-ww`）的定义文件，它还定义了类型 `LanguageMessages`。

## 完善现有语言

- `src/intl/{language-code}.ts` 是语言定义文件。若要修改文本，只需填写其中的 `messages`。

> 有两种类型的i18n消息，`string` 和 `function`。
>
> 如果您不知道如何操作，最好的方法是参考 `src/intl/root.ts` 的做法。

## 创建新的语言文件

- 创建一个新文件 `src/intl/{language-code}.ts`。
- 将以下内容写入文件中：
```typescript
export default {
  name: "{language-name}",
  code: "{language-code}",
  messages: {
    // ...
  },
}
```

在上述文件中，*language-name* 是语言本身的名称。例如，希腊语的 *language-name* 是 `Ελληνικά`，而希腊语的 *language-code* 是 `el-gr`。