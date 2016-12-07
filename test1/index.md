---
layout: default
---

# Testing [jekyll where-filter bug](https://github.com/jekyll/jekyll/issues/5586)

<dl>
	{% assign one = site.data.test | where: "name", "one" %}
	<dt>one:</dt>
	<dd>{{ one }}</dd>

	{% assign two = site.data.test | where: "name", "two-with-dashes" %}
	<dt>two:</dt>
	<dd>{{ two }}</dd>

	{% assign three = site.data.test | where: "name", "three with spaces" %}
	<dt>three</dt>
	<dd>{{ three }}</dd>

	{% assign four = site.data.test | where: "name", "four_with_underscore" %}
	<dt>four</dt>
	<dd>{{ four }}</dd>

	{% assign five = site.data.test | where: "name", "five+with%special#characters" %}
	<dt>five</dt>
	<dd>{{ five }}</dd>
</dl>