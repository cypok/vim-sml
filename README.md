My version of vim-sml
================

Syntax and indent files for Standard ML


Features
--------

There are some differences (features) from standard Vim 7.4 files.

- No line wrapping (`textwidth = 0`).

- Indent `case` as follows:

        case x of
          NONE => "none"
        | SOME of str => str

- Indent `handle` as follows:

        call_smth_dangerous
          handle Err1 => 41
               | Err2 => 42

- Indent functional pattern matching:

        fun length [] = 0
          | length _::xs = 1 + length xs

- Indent `let` after `fun`:

        fun double_sum (x, y) =
          let val sum = x + y
          in 2*sum end

- Fix indentation of `if/then/else` when using `=`.

- Fix highlighting of `=>`, `:=`.

- Highlight record fields in type declaration, record creation and record patterns.


Installation
------------

- [Vundle](https://github.com/gmarik/vundle) way, add the following to your $HOME/.vimrc file:

        Bundle 'cypok/vim-sml'

    And run inside of vim:

        :BundleInstall

- [Pathogen](https://github.com/tpope/vim-pathogen) way:

        $ git clone https://github.com/cypok/vim-sml.git ~/.vim/bundle/vim-sml

- Manual (simplest if you've never heard of vundle or pathogen), download the zip file generated from github and extract it to $HOME/.vim

        mv vim-sml*.zip $HOME/.vim
        cd $HOME/.vim && unzip vim-sml*.zip

    Update the help tags from vim:

        :helptags ~/.vim/doc/

