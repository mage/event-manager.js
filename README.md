#mage-event-manager.js

dot-notation event emission

## What does that mean?

Standard javascripts objects use a dot-notation to denote hierarchy. For example:

`food.soup.chickenNoodle`

The parent object: `food` has a child object: `stew` which has a child object: `chickenNoodle`

With the event manager, you can emit events at every level of the hierarchy.

``` javascript
emit('food.soup.chickenNoodle');
```

Will emit at `food.soup.chickenNoodle`, `food.soup`,  and `food`. So if you want to listen for all
events related to `food`, you could listen on `food` and your event listener would trigger on
`food.pasta.macaroni`, `food.canned.pears`, and `food`. If you only care about `soup`, you could
listen only on `food.soup` and then you'd only hear about `food.soup.minestrone`, `food.soup.tomato`,
and `food.soup`
