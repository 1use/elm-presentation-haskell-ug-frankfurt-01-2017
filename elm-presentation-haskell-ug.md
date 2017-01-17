---
title: Elm Talk @ Frankfurt Haskell User Group
revealOptions:
    transition: 'fade'
---

# Elm
### uniquely functional & reactive

_Ali-Pasha Foroughi, January, 2017_

[Frankfurt Haskell User Group](https://www.meetup.com/Frankfurt-Haskell-User-Group/events/235299683/)


---

##  <span style="color:#42AFFA"> Intro 
### <span style="color:gray"> Elm Basics
#### <span style="color:gray"> Elm Architecture
##### <span style="color:gray"> ELM FRP?
##### <span style="color:gray"> Conclusion

Note: Outline is #TODO

---

## Ali-Pasha Foroughi
* Software Developer 
* IT Consultant
* Data Enthusiast

<img src="https://avatars1.githubusercontent.com/u/19994880" alt="hallo_frankfurt.de" style="width: 100px; height: 100px"/>
<br>
[hallofrankfurt.de](http://hallofrankfurt.de)

---

### <span style="color:white"> <span style="color:gray"> Intro
##  <span style="color:#42AFFA"> Elm Basics
### <span style="color:gray"> Elm Architecture
#### <span style="color:gray"> ELM FRP?
#### <span style="color:gray"> Conclusion

---

# Elm 
<img src="https://avatars0.githubusercontent.com/u/4359353" alt="Elm" style="width: 200px; height: 200px"/>
<br>

[elm-lang.org](http://elm-lang.org/)

Twitter: [@elmlang](https://twitter.com/elmlang)

Github: [@elm-lang](https://github.com/elm-lang/)

---

# Evan Czaplicki
<img src="https://avatars2.githubusercontent.com/u/1658058" alt="Evan Czaplicki" style="width: 200px; height: 200px"/>
<br>

[Elm - Concurrent FRP for Functional GUIs](https://www.seas.harvard.edu/sites/default/files/files/archived/Czaplicki.pdf)

Twitter: [@czaplic](https://twitter.com/czaplic)

Github: [@evancz](https://gihub.com/evancz)

Works at: [@noredink](https://twitter.com/noredink)

---

# Elm (0.18)

* Functional Language 
* Compiles to Javascript
* Slogan: No Runtime Errors

---

## Functional Language 
*  Pure Functions
*  Types
*  Managing Effects 

---

# REPL
[elm-repl](https://github.com/elm-lang/elm-repl)

---

#### <span style="color:gray"> Intro
### <span style="color:gray"> Elm Basics
##  <span style="color:#42AFFA"> Elm Architecture
### <span style="color:gray"> ELM FRP?
#### <span style="color:gray"> Conclusion

---

[The Elm Architecture + Effects](https://guide.elm-lang.org/architecture/effects/)

## Model

## Update

## View

---

# Model 

* immutable Data 
* represents the entire application State
* single Source of Truth

```elm
type alias Model =  { ... } -- some data structure
```

---

# Update 
 
* takes the current model 
* takes a message describing desired changes
* returns a revised model

```elm
update : Msg -> Model -> Model
```

---

# View 

* accepts the revised model 
* returns a representation of the desired DOM structure

```elm
view : Model -> Html Msg
```

---

![](https://guide.elm-lang.org/architecture/effects/beginnerProgram.svg)

```elm
--Model
type alias Model =  { ... } -- some data structure

--View
view : Model -> Html Msg

-- Update
view : Msg -> Model -> Model
```

---

# Demo

[Counter](http://elm-lang.org/examples/buttons)

---

#### <span style="color:gray"> Intro
### <span style="color:gray"> Elm Basics
### <span style="color:gray"> Elm Architecture
##  <span style="color:#42AFFA"> ELM FRP?
#### <span style="color:gray"> Conclusion

---

# André Staltz
<img src="https://avatars1.githubusercontent.com/u/90512" alt="André Staltz" style="width: 200px; height: 200px"/>
<br>
* author of  the Cycle.js framework
* core contributor to RxJS

[Why I cannot say FRP but I just did](https://medium.com/@andrestaltz/why-i-cannot-say-frp-but-i-just-did-d5ffaa23973b#.iv4jmiu4k)

[Unidirectional User Interface Architectures](http://staltz.com/unidirectional-user-interface-architectures.html)

---

# Strict Definition of FRP

> Reactive programs also maintain a continuous interaction with their environment, but at a speed which is determined by the environment, not by the program itself.
> --Conal Elliott

---

# Strict Definition of FRP


### Denotative, Continuous-Time Programming (DCTP)
(a more fiting term)

[The difference between Reactive and Functional-Reactive programming](http://stackoverflow.com/questions/5385377/the-difference-between-reactive-and-functional-reactive-programming/5386908#5386908)

---

## Initial Elm Definition

> FRP is a declarative programming paradigm for working with mutable values. 
> FRP recasts mutable values as time-varying values, better capturing the temporal aspect of mutability.

---

# Signals

> In FRP, time- varying values are called signals. 

[Visualization of Elm Signals](https://yang-wei.github.io/elmflux/)

---

# <span style='color:red;text-decoration:line-through'><span style='color:white'>Signals

[Migrating signal usage from Elm 0.16 to 0.17](http://noredink.github.io/posts/signalsmigration.html)

---

# Elm <span style='color:red;text-decoration:line-through'><span style='color:white'>FRP
[A Farewell to FRP](http://elm-lang.org/blog/farewell-to-frp)

## Introducing Subscriptions

---

# Subscriptions 

* components sit around and wait for messages 
* library code handles resource management 

```elm

-- subscriptions
subscriptions : Model -> Sub Msg

```

---

![](https://guide.elm-lang.org/architecture/effects/program.svg)

```elm
--Model
type alias Model =  { ... } -- some data structure

--View
view : Model -> Html Msg

-- subscriptions
subscriptions : Model -> Sub Msg

-- Update
update : Msg -> Model -> ( Model, Cmd Msg )
```

---

# Commands

## Demo

[Random](https://www.elm-tutorial.org/en/03-subs-cmds/02-commands.html)


---

# Subscriptions

## Demo

[Mouse & Keyboard](https://www.elm-tutorial.org/en/03-subs-cmds/01-subs.html)


---

###### <span style="color:gray"> Intro
##### <span style="color:gray"> Elm Basics
#### <span style="color:gray"> Elm Architecture
### <span style="color:gray"> ELM FRP?
## <span style="color:#42AFFA"> Conclusion

---

# Language-Level Reactivity

[Richard Feldman Oct 24, 2016](https://www.infoq.com/articles/language-reactivity-with-elm)


---

# Elm 

* just a functional language 

* takes concurrency very seriously

* managing effects behind the scenes

---

# Links Elm 

* [elm-lang.org](http://elm-lang.org/)
* [Elm on Github - @elm-lang](https://github.com/elm-lang/) 
* [The Elm Architecture + Effects](https://guide.elm-lang.org/architecture/effects/)
* [Evan Czaplicki - Elm - Concurrent FRP for Functional GUIs](https://www.seas.harvard.edu/sites/default/files/files/archived/Czaplicki.pdf)
* [Evan Czaplicki - A Farewell to FRP](http://elm-lang.org/blog/farewell-to-frp)
* [Richard Feldman - Language-Level Reactivity](https://www.infoq.com/articles/language-reactivity-with-elm)
* [Migrating signal usage from Elm 0.16 to 0.17](http://noredink.github.io/posts/signalsmigration.html)

---

# Links FRP

* [André Staltz - Why I cannot say FRP but I just did](https://medium.com/@andrestaltz/why-i-cannot-say-frp-but-i-just-did-d5ffaa23973b#.iv4jmiu4k)
* [André Staltz - Unidirectional User Interface Architectures](http://staltz.com/unidirectional-user-interface-architectures.html)
* [The difference between Reactive and Functional-Reactive programming](http://stackoverflow.com/questions/5385377/the-difference-between-reactive-and-functional-reactive-programming/5386908#5386908)
* [Visualization of Elm Signals](https://yang-wei.github.io/elmflux/)

---

# Links Examples

* [Counter (Buttons)](http://elm-lang.org/examples/buttons)
* [Commands (Random)](https://www.elm-tutorial.org/en/03-subs-cmds/02-commands.html)
* [Subscriptions (Mouse & Keyboard)](https://www.elm-tutorial.org/en/03-subs-cmds/01-subs.html)
* [SVG Clock](http://elm-lang.org/examples/time)
* [More Try Elm Examples](http://elm-lang.org/examples)

---

## Presentations as Markdown

[reveal-md](https://github.com/webpro/reveal-md/)

## See also

[reveal-js](http://lab.hakim.se/reveal-js/#/)

---

## Ali-Pasha Foroughi

Twitter: [@alipasha](https://twitter.com/alipasha)

Github: [@1use](https://gihub.com/1use) 

Tech & Startup Events Frankfurt RheinMain:

[hallofrankfurt.de](http://hallofrankfurt.de)

---

# Thank You!

## [Frankfurt Haskell User Group](https://www.meetup.com/Frankfurt-Haskell-User-Group/)
#### Peter Althainz
#### Nadja & Harald Vajkonny

## [Codecentric AG](https://www.codecentric.de/)