+++
date = "2016-12-24T07:47:40-05:00"
title = "gitflow"
draft = false

+++

#Elaborating on Git Flow, Gitlab Flow, GitHub Flow, and Hugo

## Resources
[this web site](http://analyticsangel.azurewebsites.net/index.html)
[markdown cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
### Hugo
[hugo quickstart](http://gohugo.io/overview/quickstart/)
[hugo beyond the defaults](https://npf.io/2014/08/hugo-beyond-the-defaults/)

### Git Workflow Patterns
[git flow cheat sheet](http://danielkummer.github.io/git-flow-cheatsheet/)
[github integrations](https://github.com/integrations)
[github workflows inside of a company](https://www.nczonline.net/blog/2013/05/21/github-workflows-inside-of-a-company/)
[Understanding the GitHub Flow](https://guides.github.com/introduction/flow/)
[GitLab Flow](https://about.gitlab.com/2014/09/29/gitlab-flow/)
[GitDMZ Flow](https://gist.github.com/djspiewak/9f2f91085607a4859a66)
### Working with Git Api
[oauth](https://github.com/Axosoft/oauthd)
[my starred repos json](https://api.github.com/users/asears/starred)

## My Starred Repos
Built from a Hugo JSON template & Git api

<ul class="ghStarred">
  {{ $url := .Get "https://api.github.com/users/asears/starred" }}
  {{ range getJSON $url }}
    {{ $p := . }}
    <li>
      <a href="{{$p.owner.html_url}}" target="_blank">
        <img src="{{$p.owner.avatar_url}}" alt="Avatar of {{$p.owner.login}}" title="Avatar of {{$p.owner.login}}">
      </a>
      {{$p.language}}: <strong>{{ $p.name }}</strong>
      <a href="{{ $p.html_url }}" target="_blank">{{ $p.full_name }}</a>
      <br>
      Stars: {{$p.stargazers_count}} | Forks: {{$p.forks_count}} | Size: {{$p.size}}<br>
      {{ $p.description }}
      <div class="clear"></div>
    </li>
    {{ end }}
</ul>