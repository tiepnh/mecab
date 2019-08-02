# mecab
Build new dictionary 
## 1. Prepare data
- Recommend to use base dic is mecab-ipadic
- Modify mecab-ipadic list word / or make new file as below format (for each row)
{Word},-1,-1,100,名詞,固有名詞,地域,一般,*,*,{Word},*,*  (for noun - location)
## 2. Build new dic
- Change file configure

``
  MECAB_DICDIR="`$MECAB_CONFIG --dicdir`/ipadic"
``

--> ``MECAB_DICDIR="`$MECAB_CONFIG --dicdir`/ipadic-utf8-xxx"``
  - Run 

`./configure --with-charset=utf8`

`make`

--> new dictionary will be created at /usr/local/lib/mecab/dic/ipadic-utf8-xxx
