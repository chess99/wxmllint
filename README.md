# wxmllint

> An unofficial wxml linter and validator.  
> fork and modified from [htmllint](https://github.com/htmllint/htmllint)  

目前可用的rc文件 [.wxmllintrc](./.wxmllintrc)  

### TODO

- [x] "attr-bans"
- [x] "attr-name-ignore-regex"
- [x] "attr-name-style"
- [x] "attr-new-line"    --建议  3
- [x] "attr-no-dup"    --建议  true
- [x] "attr-no-unsafe-char"    --建议  true
- [x] "attr-order"    --建议 ["/^wx/", "/^(?!wx)/"]
- [x] "attr-quote-style"    --建议 "quoted"
- [x] "attr-req-value"    ----建议 false    ----booleanAttrs不能满足自定义属性的需求
- [x] "attr-validate"    --建议  true
- [ ] "button-req-content"
- [ ] "class-no-dup"
- [ ] "class-style"
- [ ] "doctype-first"
- [ ] "doctype-html5"
- [ ] "fieldset-contains-legend"
- [ ] "fig-req-figcaption"
- [ ] "focusable-tabindex-style"
- [ ] "head-req-title"
- [ ] "head-valid-content-model"
- [ ] "href-style"
- [ ] "html-req-lang"
- [ ] "html-valid-content-model"
- [ ] "id-class-ignore-regex"
- [ ] "id-class-no-ad"
- [ ] "id-class-style"
- [ ] "id-no-dup"
- [ ] "img-req-alt"
- [ ] "img-req-src"
- [ ] "indent-delta"
- [ ] "indent-style"
- [ ] "indent-width"
- [ ] "indent-width-cont"
- [ ] "input-btn-req-value-or-title"
- [ ] "input-radio-req-name"
- [ ] "input-req-label"
- [ ] "label-no-enc-textarea-or-select"
- [ ] "label-req-for"
- [ ] "lang-style"
- [ ] "line-end-style"
- [ ] "line-max-len"
- [ ] "line-max-len-ignore-regex"
- [ ] "line-no-trailing-whitespace"
- [ ] "link-min-length-4"
- [ ] "link-req-noopener"
- [ ] "maxerr"
- [ ] "raw-ignore-regex"
- [ ] "spec-char-escape"
- [ ] "table-req-caption"
- [ ] "table-req-header"
- [ ] "tag-bans"
- [x] "tag-close"
- [ ] "tag-name-lowercase"
- [ ] "tag-name-match"
- [x] "tag-req-attr"    --建议 {"image": [{"name": "src"}]}
        -- TODO: 实现个 "tag-no-attr" 来禁止 text 上的 class
- [ ] "tag-self-close"
- [ ] "text-ignore-regex"
- [ ] "title-max-len"
- [ ] "title-no-dup"

### wxml 中的 attribs

```
<view wx:if="{{conditionA}}" {{skuList.length}} bindtap="doSth"></view>

====>
wx:if ---- {{conditionA}}
{{skuList.length}} ---- 
bindtap ---- doSth
```

