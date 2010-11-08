---
layout: default
title: Use it
---


## How to use Jasmine-Species

To make use of the "grammar" component in Jasmine-Species, 
you simply need to include the "<code>jasmine-grammar.js</code>" file in your spec runner. Then 
you import (e.g. <code>Namespace.use('jasmine.grammar.FeatureStory.*')</code>) 
only the grammar components you need.

To experience the cleaner and richer ouput available from the reporting component, 
simply include the "<code>jasmine-reporting.js</code>" file in your spec runner. 
Then register the **StyledHtmlReporter** with Jasmine.

You can follow the quick steps below to start enjoying jasmine-species.

### 1. Add jasmine-grammar and jasmine-reporting to your runner page

{% highlight html %}
    <link rel="stylesheet" type="text/css" href="lib/jasmine-species/calm.css">

    <script type="text/javascript" src="lib/jasmine-species/jasmine-grammar.js"></script>
    <script type="text/javascript" src="lib/jasmine-species/jasmine-reporting.js"></script>
{% endhighlight %}

### 2. Import and use only the components you need

{% highlight javascript %}
    // import the relevant grammar modules
    Namespace.use('jasmine.grammar.FeatureStory.*');  // imports feature, scenario, ...
    Namespace.use('jasmine.grammar.GWT.*');   // imports given, when, ...
    
    // plug-in the StyledHtmlReporter to "prettify" your spec reports
    jasmine.getEnv().addReporter(new jasmine.reporting.StyledHtmlReporter());
{% endhighlight %}

### 3. Happy BDDing!

Create your specs with the extended grammar:

{% highlight javascript %}
feature('Number crunching', function() {
    scenario('Adding two positive integers', function() {
        var ans = 0;
        
        when('I sum the numbers 5 and 10', function() {
            ans = 5 + 10;
        });
        
        then('The answer should be 15', function() {
            expect(ans).toEqual(15);
        });
    });
});
{% endhighlight %}