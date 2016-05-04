# NeoBundle's autoclose plugin prevents japanese writing


`autoclose plugin`の問題というよりは、Mac用のKaoriya
gVimの問題?

- http://www.mogumagu.com/wp/wordpress/archives/1225

- http://qiita.com/m_mysht/items/56e5d5a17d07a64d8b65

`.vimrc`にて以下のようにコメントアウトすることで、日本語入力できるようになった。

```
# NeoBundle 'Townk/vim-autoclose'
```

代わりに`.gvimrc`にて以下を設定。
閉じカッコをオートで消したいけど、たぶんそこで問題がでちゃうのだろう。

```
inoremap { {}<LEFT>
inoremap ( ()<LEFT>
inoremap [ []<LEFT>
inoremap " ""<LEFT>
inoremap ' ''<LEFT>
vnoremap { "zdi^V{<C-R>z}<ESC>
vnoremap [ "zdi^V[<C-R>z]<ESC>
vnoremap ( "zdi^V(<C-R>z)<ESC>
vnoremap " "zdi^V"<C-R>z^V"<ESC>
vnoremap ' "zdi'<C-R>z'<ESC
```
