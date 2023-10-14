
# Actions

Actions represent changes to the game state made by a game actor. The basic classes are *Action* (an instant Action), and *Task*, an action which occupies the actor for some time to complete.

They are intended to be generic for use in different kinds of game - they represent changes to the game state made by an actor - for example in an action game an Action might be bound to a key pressed by the player, in a card or strategy game it might represent a card played, or an ability available to a character which has been selected.

## Action Bindings

Visualising an Action as a function, a change to game state which _gets done_, we can then think of an action's _Bindings_ as its parameters, indicated by an `ldp:Container` on the property `mudlogic:hasBindings`. Bindings are generally useful for the following purposes:

* Restricting Actions to specific situations (e.g. only vampires can perform _Vampiric Bite_).
* Modelling game state changes once an action has been completed (e.g. after performing _Vampiric Bite_ on a living human, the bound _Target_ of the action should be infected with the Vampire's Curse).

There are several types of Binding, which are treated differently by a given game:

* `ActorBinding`: The Actor conducting the action.
* `TargetBinding`: The object on which the action is being completed, if applicable.
* `WitnessBinding`: An object in the vicinity of an action being completed.
* `ConsumableBinding`: An object consumed in the performing of the action, e.g. fuel, oxygen and heat are needed to start a fire.
* `LocationBinding`: The local world state where the action is being performed. Intended to restrict where an action can be performed (e.g. to prevent fires from being completed underwater).

## Operations (Game State Changes)

*Operation* is a base class modelling changes to the world graph resulting from an action - the subclasses are *Post* or *Patch*. An action will indicate the resulting changes with the property `mudlogic:operationsOnComplete` and a Patch operation will indicate the changes made using the lists `inserts` and `deletes`.

### Triggering changes on entry to a space

A `mud:Locatable` (like a building), can have the property `mudlogic:changesTriggeredOnEntry`, containing operations which should be carried out on the buildings entry. It's up to the game to decide how to display this to the user

## Action Points

A common mechanism in turn-based strategy games relating to actions are Action Points, a cost associated to a particular move which limits how many moves can be made by a character on each turn. Action Points are missing from the `mudlogic` vocabularly, but these can be modelled using the classes available in the `mudcombat` vocabulary

# Effects

An Effect is an Action which is recurring, for example reccuring damage resulting from a prior action, Poison. By their nature these are only going to be used in certain games, and it shouldn't be assumed that a game will support them. The properties associated with this feature are `mudlogic:recursAfterSeconds`, `mudlogic:expiresAfterOccurences` (which dictate the functioning of recurrances) and `mudlogic:activeEffects` (which is stored on the object they are affecting).

# Tasks

As previously mentioned Tasks are Actions which take some time for the actor to complete. Their progress is modelled by the boolean `mudlogic:isComplete` and the floating point `mudlogic:progress` (0.0 - 1.0).

Before conducting a new task, a game should check whether the actor is preoccupied - indicated by the property `mudlogic:hasOngoingTask`.

# Action Discovery Endpoint

// TODO..
