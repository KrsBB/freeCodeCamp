---
title: Managing Ruby versions
localeTitle: Управление версиями Ruby
---
## Ruby со временем изменилась

Ruby был в постоянном развитии с 1990-х годов и, как и многие языки, произошли синтаксические изменения в разных версиях, поэтому важно быть четкими о том, какую версию Ruby ожидает ваш код.

Вероятно, наиболее заметные изменения произошли с Ruby 1.9; ранее мы писали хэши:

```ruby
  { :one => 1, :two => 2, :three => 3 } 
```

Это использование оператора «hashrocket» ( `=>` ) было настолько распространенным, что Ruby 1.9 при условии сокращения:
```
  { one: 1, two: 2, three: 3 } 
```

Этот старый код запускается на любой версии, но новый синтаксис будет работать только на Ruby 1.9+.

## Как это вызывает проблемы?

Например, вы, возможно, решили использовать драгоценный камень, который Возможности Ruby 1.9; это означает, что ваш проект теперь также зависит от Ruby 1.9 функции.

Если вы не укажете, какую версию Ruby требуется вашему проекту, это может быть очень путают, когда код работает на одной машине, но не другой.

Как и в большинстве языков, считается хорошей практикой указывать версию Ruby, который ожидает ваш код. Это упрощает управление несколькими проектов на вашей машине разработки, каждый из которых ожидает другую версию Рубин.

## Как указать мою версию Ruby?

Есть несколько инструментов, которые популярны для этого, но оба согласились совместно использовать общий файл. Многие проекты Ruby (или Rails) будут включать в себя простой `.ruby-version` , который просто указывает номер версии, _например_ :
```
2.4.2 
```

Популярные инструменты, которые помогут вам управлять вашей версией Ruby:

*   [Менеджер версий Ruby (RVM)](https://rvm.io)
*   [rbenv](https://github.com/rbenv/rbenv)

Давайте посмотрим на RVM.

### Использование RVM

RVM обычно устанавливается ( [ссылка](https://rvm.io) ) на Linux, Unix или MacOS машина, и очень удобна, поскольку она перехватывает в `cd` ( `c` hange `d` directory) поэтому, когда вы переходите к новому проекту, ваша `.ruby-version` читается автоматически, и вы автоматически переключаетесь на правильную версию Ruby прежде чем вы начнете работать.

Например, у вас может быть такая последовательность:

```shell
% cd ~/projects/older-project 
 % ruby --version 
 
 ruby 2.3.5p376 (2017-09-14 revision 59905) [x86_64-darwin16] 
 
 % cd ~/projects/newer-project 
 % ruby --version 
 
 ruby 2.4.2p198 (2017-09-14 revision 59899) [x86_64-darwin16] 
```

(Эти примеры взяты из машины MacOS)