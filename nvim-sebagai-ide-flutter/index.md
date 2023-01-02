# Nvim Sebagai IDE Flutter


## Install Plugins

Untuk memakai Neovim sebagai IDE Flutter kita menambahkan beberapa plugin pada `init.vim`.	
```
Plug 'honza/vim-snippets'
Plug 'dart-lang/dart-vim-plugin'
Plug 'neoclide/coc.nvim', {'branch': 'release'}
```
Setelah neovim dijalankan dan menemui error seperti ini:
```
[coc.nvim] “node” is not executable, checkout https://nodejs.org/en/download/
```

Artinya kita perlu menginstall [nodejs](https://larrymarzanjr.github.io/2022-02-12-how-to-install-nodejs-npm-in-linux-debian/)

## Install Coc extension

Selanjutnya kita perlu install [coc-flutter](https://github.com/iamcco/coc-flutter)
extension yaitu dengan menambahkan variable dibawah pada file konfigurasi neovim di
`init.vim`. Dengan ini kita bisa mendapatkan fitur lengkap seperti snippet untuk flutter.
Pada saat menjalankan neovim berikutnya, ketiga extension yang ditambahkan pada variable
dibawah akan terinstall secara otomatis.
```
let g:coc_global_extensions = [
  \ 'coc-flutter',
  \ 'coc-snippets',
  \ 'coc-yaml',
  \]
```
> NOTE: Jika proses instalasi tidak berjalan otomatis, jalankan perintah `:CocInstall
> coc-flutter` pada nvim

## Coc Key Bindings untuk Flutter

Variable berikut akan menambahkan keymap TAB dan SHIFT+TAB untuk memilih atau membatalkan
pilihan dari _auto suggestion_ dari snippet yang muncul
> NOTE: Gunakan perintah `:verbose imap` untuk memastikan TAB tidak di mapping oleh plugin yang lain
```
inoremap <silent><expr> <TAB>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<TAB>" :
      \ coc#refresh()
inoremap <expr><S-TAB> pumvisible() ? "\<C-p>" : "\<C-h>"

function! s:check_back_space() abort
  	  let col = col('.') - 1
  	    return !col || getline('.')[col - 1]  =~# '\s'
endfunction
```
Tombol ENTER akan memilih secara otomatis snippet yang muncul, dengan menambahkan variable
berikut
```
inoremap <silent><expr> <cr> pumvisible() ? coc#_select_confirm()
                              \: "\<C-g>u\<CR>\<c-r>=coc#on_enter()\<CR>"
```

## Code Action binding

Next we bind keys for code action like wrap with widget,wrap with center etc.

```
xmap <leader>a  <Plug>(coc-codeaction-selected)
nmap <leader>a  <Plug>(coc-codeaction-selected)
```
So code action can be used like <leader>aap for current paragraph, <leader>aw for the current word. My leader key is SPACE.

## Atur Code Flutter pada saat save dan panjang kode maksimal 80 dalam baris
```
 let g:dart_format_on_save = 1
 let g:dartfmt_options = ['--fix', '--line-length 80']
```

## Coc commands

```
nmap <silent> gd <Plug>(coc-definition)
nmap <silent> gy <Plug>(coc-type-definition)
nmap <silent> gi <Plug>(coc-implementation)
nmap <silent> gr <Plug>(coc-references)
nmap <leader>rn <Plug>(coc-rename)
```
## Gunakan K untuk memanggil dokumentasi 

```
nnoremap <silent> K :call <SID>show_documentation()<CR>
function! s:show_documentation()
  if (index(['vim','help'], &filetype) >= 0)
    execute 'h '.expand('<cword>')
  elseif (coc#rpc#ready())
    call CocActionAsync('doHover')
  else
    execute '!' . &keywordprg . " " . expand('<cword>')
  endif
endfunction"
```

## Flutter commands
```
nnoremap <leader>fe :CocCommand flutter.emulators <CR>
nnoremap <leader>fd :below new output:///flutter-dev <CR>
nnoremap <leader>fr :CocCommand flutter.run <CR> 
```

Ada banyak Flutter commands lainnya yang dapat ditemukan di [coc-flutter](https://github.com/iamcco/coc-flutter).

## Referensi
[jsj's blog -$Setup Vim as a Flutter IDE using coc-nvim on windows](https://jithusjacob.github.io/post/vim_flutter_ide/)

