Think the cogs in big machines
Do they have any internal state?
Do they change colour per current mode?
Or all they have are pre-defined size and teeth?

They transfer motions from a power source
Through a chain of reaction and engagement
They run your watch your car your city
They are the universal reusable components

Now think the function of cogs
Can they also run your computers?
Yes they can if you program them
In a way the cogs work in the virtual space

Remember the cogs have no state
They are reasonably reactive and reusable
Think rid of mindset of OOP
Where stateful models knit unstable society

Let start with figwheel
That forces us design cogwheel
Then we build JS with React
In a touch of the exotic ClojureScript

Open your terminal fellows
lein new figwheel cog
I shall not teach you google
If you have stuck in the middle

cd cog && lein figwheel
Open your browser at localhost:3449
See the message to your console?
The println on every save is your REPL

Each cljs compiles to a JS file
Browser reloads only the one  touched
If we separate the state and behaviour
Each file can be a virtual cog

Open src/cog/core.cljs
Change that println string to "a cog!"
Upon you save your hard work
Your console shouts "a cog!" as for sure

Let we have two separate files
One for UI and one for the data
Open src/cog/state.cljs and put
(ns cog.state) (def cog "is a cog")

Go back to core.cljs and insert after :require
[cog.state :as state]
Then change println to be
(println "a cog" state/cog)

So two cogs we have built to be engaged
So change one would trigger another?
Not if you don't put that println after :on-jsload
As only that triggers on each reload

We can (def cog [:cog 1 2 3])
This is a vector or say an array
We can (def cog {:cog 1 2 3})
This is a map or say a dictionary

So we see most data blocks
1 number "a" string [vector] {:or map}
Remember they are all immutable
Means no eraser for grown-ups

Say we (def v [1 2 3])
And (defn cog [] (map inc v))
The console shouts a cog is a function
Exactly what I wanted your attention

Math is LISP and C is for counting bean
Believe in math brings the pure beauty
I rather prefer (. V .) to any one of the o.V()
The equalitarian objects imperative value manipulation

LISP and ClojureScript are used to paren
So used as we used to any punctuation
We read the first position calls a function
Using the rest as zero or more arguments

To check the result of function of cog
Either we (println (cog)) or defn a helper
(defn cogn [] (reduce + (map inc v)))
Then (def cog (str "is " (cogn) "s"))

Spare yourself 20 years trial and error
Checkout Reactjs and ClojureScript
Let us go straight to the sweet point
May the force be with you ever

In index.html uncomment the script tag
Check the react.js version is the latest
Add below to core.cljs and save your work
(js/React.render (js/React.DOM.p nil state/cog) (.-body js/document))

Voila you know the secret of Om and Rum
For sure there are miracles and magic
But I shall stop here not to spoil your fun
Follow them and tweet funcog if you can

PS, code listing:

(ns cog.core
  (:require
  [cog.state :as state]
  [figwheel.client :as fw]))
(enable-console-print!)
(fw/start { :on-jsload (fn []
(js/React.render (js/React.DOM.p nil state/cog) (.-body js/document))
(println "a cog" state/cog))})

(ns cog.state)
(def v [1 2 3])
(defn cogn [] (reduce + (map inc v)))
(def cog (str "is " (cogn) "s"))
