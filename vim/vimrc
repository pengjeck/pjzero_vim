"author: pjzero
"email: pjwhusir@gmail.com

" let backspace can delete
set nocompatible
set backspace=indent,eol,start

" Plugin
call plug#begin('~/.vim/plugged')
Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
Plug 'junegunn/fzf.vim'
Plug 'Valloric/YouCompleteMe'
Plug 'scrooloose/nerdtree'
Plug 'flazz/vim-colorschemes'
Plug 'jiangmiao/auto-pairs'
Plug 'ntpeters/vim-better-whitespace'
Plug 'tpope/vim-surround'
Plug 'vim-airline/vim-airline'
Plug 'w0rp/ale'
Plug 'Xuyuanp/nerdtree-git-plugin'
Plug 'scrooloose/nerdcommenter'
Plug 'tmhedberg/SimpylFold'
call plug#end()

" ==============
" map keys
" ==============
let mapleader = ";"
nmap <leader>w :w!<cr>
nmap <leader>q :q<cr>
nmap <leader>wq :wq<cr>
nmap <leader>tn :tabnew<cr>
nmap <leader>te :tabedit
nmap <leader>tc :tabclose<cr>
" =>Remove unwanted spaces
map <leader>c :%s/\s\+$//<cr>

" =>Removes highlight of your last search
noremap <C-h> :nohl<cr>
vnoremap <C-h> :nohl<cr>
inoremap <C-h> :nohl<cr>

" => code format using google/yapf
autocmd FileType python nnoremap <leader>= :0,$!yapf<CR>


" ==============
" end of map keys
" ==============


" ==============
" plug config
" ==============

" =>nerdtree config
map <C-n> :NERDTreeToggle<cr>
" + 当不带参数打开Vim时自动加载项目树
autocmd StdinReadPre * let s:std_in=1
autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif
" + 当所有文件关闭时关闭项目树窗格
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTreeType") && b:NERDTreeType == "primary") | q | endif
" + 不显示这些文件
let NERDTreeIgnore=['\.pyc$', '\~$', 'node_modules'] "ignore files in NERDTree
" + 不显示项目树上额外的信息，例如帮助、提示什么的
let NERDTreeMinimalUI=1

" =>vim-fzf
nnoremap <silent> <C-p> :Files<cr>

" => NERD Commenter
" Add spaces after comment delimiters by default
let g:NERDSpaceDelims = 1
" Use compact syntax for prettified multi-line comments
let g:NERDCompactSexyComs = 1
" Align line-wise comment delimiters flush left instead of following code indentation
let g:NERDDefaultAlign = 'left'
" Add your own custom formats or override the defaults
let g:NERDCustomDelimiters = { 'c': { 'left': '/**','right': '*/' } }
" Allow commenting and inverting empty lines (useful when commenting a region)
let g:NERDCommentEmptyLines = 1
" Enable trimming of trailing whitespace when uncommenting
let g:NERDTrimTrailingWhitespace = 1

" => SimpleFold
set foldmethod=indent
au BufWinLeave * silent mkview  " 保存文件的折叠状态
au BufRead * silent loadview    " 恢复文件的折叠状态
nnoremap <space> za             " 用空格来切换折叠状态

" => ale
let g:ale_sign_column_always = 1
let g:ale_sign_error = '>>'
let g:ale_sign_warning = '--'
let g:ale_lint_on_text_changed = 'never'
" let g:ale_lint_on_enter = 0

" =================
" end of plug
" =================


" vim 命令行模式自动补全
set wildmenu

" tab line
set showtabline=1

" show matching bracets when text indicator is over them
set showmatch

" [color scheme]
set background=light
set t_Co=256
let g:solarized_termcolors = 256
let g:solarized_visibility = "high"
let g:solarized_contrast = "high"
colorscheme solarized

" syntax highlight on
syntax on
set encoding=utf-8
set guifont=DejaVu\ Sans\ Mono\ 10

"FileType support
set filetype=on
filetype plugin indent on

" Highlight the screen line of the cursor with CursorLine
set cursorline

" Showing line numbers and length
set number  " show line numbers
set tw=79   " width of document (used by gd)
set colorcolumn=80

" Useful settings
set history=700
set undolevels=700

" Real programmers don't use TABs but spaces
set tabstop=4
set softtabstop=4
set shiftwidth=4
set shiftround
set smarttab
" set expandtab

" Make search case insensitive
set hlsearch
set incsearch   " 实时搜索功能开启
set ignorecase   " 搜索时忽略大小写
set smartcase

" Disable stupid backup and swap files - they trigger too many events
" for file system watchers
set nobackup
set nowritebackup
set noswapfile

" 基本解决乱码的问题
set fileencodings=ucs-bom,utf-8,utf-16,gbk,big5,gb18030,latin1