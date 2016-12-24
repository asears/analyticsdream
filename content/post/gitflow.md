+++
date = "2016-12-24T06:51:56-05:00"
title = "gitflow"
draft = true

+++

[this web site](http://analyticsangel.azurewebsites.net/index.html)
[markdown cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
[git flow cheat sheet](http://danielkummer.github.io/git-flow-cheatsheet/)
[hugo quickstart](http://gohugo.io/overview/quickstart/)
[hugo beyond the defaults](https://npf.io/2014/08/hugo-beyond-the-defaults/)
[github integrations](https://github.com/integrations)
[nsfw file watcher for Node](https://github.com/Axosoft/nsfw)
[oauth](https://github.com/Axosoft/oauthd)
[my starred repos](https://api.github.com/users/asears/starred)


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