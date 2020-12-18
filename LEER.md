



syntax on
set mouse=a
set noerrorbells
set number relativenumber
set rnu
set nowrap
set noswapfile
set nobackup
set incsearch
set clipboard=unnamedplus
set encoding=utf-8
set ignorecase
set cursorline
set noshowmode
filetype plugin indent on
set scrolloff=7
set backspace=indent,eol,start

set tabstop=4
set softtabstop=4
set shiftwidth=4
set expandtab
set autoindent
set fileformat=unix


call plug#begin('~/.config/nvim/plugged')


Plug 'morhetz/gruvbox' 
Plug 'jiangmiao/auto-pairs'

Plug 'preservim/nerdtree'
Plug 'Yggdroot/indentLine'

Plug 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }
Plug 'Shougo/neco-syntax'  " Fuente general de auto completado

Plug 'ervandew/supertab'
Plug 'Shougo/echodoc.vim'

Plug 'sheerun/vim-polyglot'
Plug 'haya14busa/incsearch.vim'


call plug#end()

colorscheme gruvbox

let g:NERDTreeChDirMode = 2 
autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif

let g:indentLine_fileTypeExclude = ['text', 'sh', 'help', 'terminal']
let g:indentLine_bufNameExclude = ['NERD_tree.*', 'term:.*']


let g:deoplete#enable_at_startup = 1
augroup deopleteCompleteDoneAu
  autocmd!
  autocmd CompleteDone * silent! pclose!
augroup END

let g:SuperTabDefaultCompletionType = '<c-n>'


set noshowmode  " No mostrar el modo actual (echodoc hace uso de este espacio)

" Activar echodoc al iniciar Neovim
let g:echodoc_enable_at_startup = 1

" Maps requeridos
map /  <Plug>(incsearch-forward)
map ?  <Plug>(incsearch-backward)

" Quitar resaltado luego de buscar
let g:incsearch#auto_nohlsearch = 1
