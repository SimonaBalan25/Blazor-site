---
layout: default
title: About
permalink: /about/
---

This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/)

When you want to pass a value from a parent to multiple child components
Passing single parameter



Parent.razor
<CascadingValue Value=”@TextColor”>
    <ChildComponentOne />
    <ChildComponentTwo />
</CascadingValue>
@code{
    Public string TextColor {get;set;} =”red”;
}

ChildComponentOne.razor
<p style=”color:@PColor”>This is component one.</p>
@code{
    [CascadingParameter]
    Public string PColor {get;set;}
}


Passing multiple parameters (matching is done by type)


Parent.razor
<button @click=”OnChangeCounter” />                                                                                        public int Counter {get;set;}
<CascadingValue Value=”@TextColor”>                                                                                      public OnChangeCounter()
    <CascadingValue Value=”@Counter”>                                                                           {
        <ChildComponentOne />                                                                                         Counter++;
        <ChildComponentTwo />                                                                                    }
    </CascadingValue>                                                                                                      }
</CascadingValue>
@code{
    Public string TextColor=”red”;

