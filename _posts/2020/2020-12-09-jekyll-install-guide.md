---
toc: true
categories:
  - Tip
tags:
  - jekyll
---
> Windows 10 에서 jekyll 을 구동하려면, 여러가지 난관에 부딪히게 된다. 손쉬운 방법은 Windows 10 내의 Ubuntu 에 설치하면 되는데 아래의 순서를 따르면 된다.
>> 윈도우 설치 기준으로 작성하였지만, mac 에서도 같은 순서로 설치하면 된다.

## 필요 프로그램 설치하기
### apt-get update 및 필요 라이브러리 설치
```bash
 $ sudo apt-get update
 $ sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev nodejs
```

### rbenv 설치
```bash
$ git clone https://github.com/rbenv/rbenv.git ~/.rbenv
```

### rbenv 환경변수 설정
```bash
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(rbenv init -)"' >> ~/.bashrc
$ source ~/.bashrc
```

### ruby-build 설치
```bash
$ git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
$ echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
$ source ~/.bashrc
```

### rbenv rehash
```bash
$ rbenv rehash
```

### ruby 최신버전 확인 및 설치
현재 최신버전은 3.0.0 이다.
```bash
$ rbenv install --list
$ rbenv install 3.0.0 
$ rbenv global 3.0.0 
$ rbenv rehash
```

### jekyll 설치
```bash
$ gem install jekyll
```

### bundler 설치
```bash
$ gem install bundler
```

### ruby 3.0 이상 사용시, 미포함된 gem 설치
```bash
$ bundle add webrick
```

## Jekyll 실행하기
프로젝트 root 에서 실행한다.
```bash
$ bundle install
$ bundle exec jekyll serve
```

[참조] [Jekyll 에 Bundler 사용하기](https://jekyllrb-ko.github.io/tutorials/using-jekyll-with-bundler/)