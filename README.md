# gitpitch-transitions
Showcase for eventual bug with gitpitch slide transitions

__Status: Bug solved!__

See claryfying comment/issue: https://github.com/gitpitch/gitpitch/issues/206#issuecomment-412846704

View working version here: https://gitpitch.com/ElpyDE/gitpitch-transitions/master

View non-working version here: https://gitpitch.com/ElpyDE/gitpitch-transitions/bug-exists  
and here: View working version here: https://gitpitch.com/ElpyDE/gitpitch-transitions/non-default

## Description

This very basic GitPitch presentation showcases a bug I found today (2018-08-11):

* The `PITCHME.yaml` file defines the default transition to be `transition:fade`
* :ok: Slides with no specific `@transition` shortcut use the default,  
  e.g. slides
  [ZERO](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/0),
  [ONE](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/1),
  [FIVE](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/5),
  [SEVEN](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/7),
  [NINE](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/9)
* :ok: Slides with a single `@transition[transition-type]` use this for their _slide-in_ and _slide-out_ transition as expected,  
  e.g. slides
  [TWO](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/2),
  [SIX](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/6)
* :x: Slides with distinct _slide-in_ and _slide-out_ transitions like `@transition[transition-type transition-type]` use the default for both which is not what I would expect from the docs,  
  e.g. slides
  [THREE](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/3),
  [FOUR](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/4),
  [EIGHT](https://gitpitch.com/ElpyDE/gitpitch-transitions/master#/8)

## GitPitch docs

* (default) [Transition Setting](https://gitpitch.com/docs/settings/transition)
* [Set Slide specific transition](https://gitpitch.com/docs/markdown-features/shortcuts#set-slide-specific-transition)
