# wxmllint

> An unofficial wxml linter and validator.  
> fork and modified from [htmllint](https://github.com/htmllint/htmllint)  

目前可用的rc文件 [./lib/presets/default.js](./lib/presets/default.js)  
`wxmllint init`    

### TODO

- [x] "attr-bans"
- [x] "attr-name-ignore-regex"
- [x] "attr-name-style"  -- camelCase?
- [x] "attr-new-line"    --建议  3
- [x] "attr-no-dup"    --建议  true
- [x] "attr-no-unsafe-char"    --建议  true
- [x] "attr-order"    --建议 ["/^wx/", "/^(?!wx)/"]
- [x] "attr-quote-style"    --建议 "quoted"
- [x] "attr-req-value"    ----建议 false    ----booleanAttrs不能满足自定义属性的需求
- [x] "attr-validate"    --建议  true
- [x] "button-req-content"    --建议 false   --大量button只是为了open-type

- [ ] "class-no-dup"     
--模板语法不能正确解析 class="{{ a ? 'a' : 'b' }}"   
--配合 "id-class-ignore-regex": "{{.*?}}" 基本可以, 还是有部分class解析不对的情况:  
```
<view class="shop-icon">
     <view class="num {{cartSkuNum < 10 ? '' : cartSkuNum <= 99 ? 'numMiddle' : 'numLarge'}}"></view>
</view>
```

- [ ] "class-style"    --TODO
- [x] "doctype-first"    --建议 false
- [x] "doctype-html5"    -- false
- [ ] "fieldset-contains-legend"
- [x] "fig-req-figcaption"    -- false  小程序不适用
- [x] "focusable-tabindex-style"    -- false
- [x] "head-req-title"    -- false 小程序不适用
- [x] "head-valid-content-model"    -- false 小程序不适用
- [x] "href-style"    -- false
- [x] "html-req-lang"    -- false 小程序不适用
- [x] "html-valid-content-model"    -- false 小程序不适用
- [ ] "id-class-ignore-regex"  -- "{{.*?}}"   --部分情况似乎有bug, 见 "class-no-dup"
- [ ] "id-class-no-ad"  -- false
- [ ] "id-class-style"  -- false
- [ ] "id-no-dup"    -- true

- [x] "img-req-alt"    -- false
- [x] "img-req-src"    -- true
- [x] "indent-delta"    -- false
- [x] "indent-style"    -- false
- [x] "indent-width"    -- false
- [x] "indent-width-cont"    -- false
- [x] "input-btn-req-value-or-title"    -- true
- [x] "input-radio-req-name"    -- false
- [x] "input-req-label"    -- false
- [x] "label-no-enc-textarea-or-select"    -- true
- [x] "label-req-for"    -- false
- [x] "lang-style"    -- true
- [x] "line-end-style"    -- false
- [x] "line-max-len"    -- ?
- [x] "line-max-len-ignore-regex"
- [x] "line-no-trailing-whitespace"

- [ ] "link-min-length-4"  -- true   --TODO: 考虑mustache
- [ ] "link-req-noopener"    -- true 小程序应该不适用
- [x] "maxerr"
- [x] "raw-ignore-regex"    -- 解析有问题: "/\<\!-- htmllint ignore --\>[^]*?\<\!-- htmllint unignore --\>/"
- [ ] "spec-char-escape"    -- false   --TODO: mustache
- [x] "table-req-caption"    -- true
- [x] "table-req-header"    -- true
- [x] "tag-bans"    -- image?
- [x] "tag-close"    -- true
- [x] "tag-name-lowercase"    -- false 
- [x] ~~"tag-name-match"~~    -- 统一到 "tag-close"
- [x] "tag-req-attr"    --建议 {"image": [{"name": "src"}]}
        -- TODO: 实现个 "tag-no-attr" 来禁止 text 上的 class
- [x] ~~"tag-self-close"~~    -- 统一到 "tag-close"
- [x] "text-ignore-regex"
- [x] "title-max-len"    -- false 小程序不适用
- [x] "title-no-dup"    -- false 小程序不适用


- [ ] Tokenizer 中识别各处出现的 mustache  

### wxml 中的 attribs

```
<view wx:if="{{conditionA}}" {{skuList.length}} bindtap="doSth"></view>

====>
wx:if ---- {{conditionA}}
{{skuList.length}} ---- 
bindtap ---- doSth
```

