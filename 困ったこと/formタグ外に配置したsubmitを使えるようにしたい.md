
# はじめに


# 問題
formタグの外に定義した\<input type="submit" />を使用したい

# 解決方法
formタグ内にid

inputタグ内にformを定義する

```tsx
<form

            id="additives-search-form"

            onSubmit={handleSubmit(onAdditivesSubmit)}

            className="w-full space-y-6"

          >
          </form>
          <button

                  type="submit"

                  form="additives-search-form"

                  data-testid="search_buttond"

                  className="bg-gradient-to-r from-brand-blue to-brand-teal text-white rounded-xl transition-all duration-300 ease-in-out transform hover:scale-105 jp-text text-lg font-semibold h-12 shadow-lg hover:shadow-xl flex items-center justify-center px-6 mx-3"

                >

                  <CiSearch className="mr-3 h-5 w-5" />

                  検索する

                </button>
          
```

form属性は<form>のDOM配置に関係なく、関連付けることができる。

