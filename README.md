# Multi User Domain vocabularies

These vocabularies are created to support Multi User Domain applications and for the Multi User Domain project. Below is a short description of each vocabulary included in this repository. For more information on how to use a specific vocabulary, see the docs folder of this repository. For documentation on how to build games within our commons, see https://Multi-User-Domain.github.io/

## Core

The main directory contains the core ontologies for any game

### 2D Graphics

Definitions for directing the generation and application of video-game graphics in 2D

### MUD

The core ontology for Multi-User-Domain logic

### MUD Account

User data is stored and managed using a standard which leverages this ontology

### MUD World

An ontology for describing the properties basic to world data

### MUD Buildings

Describes some sub-types of Building and their properties

### MUD Card

Vocabulary containing terms for card games

### MUD Characters

All things to do with Characters, playable or otherwise

### MUD Events

An extension of the [time](https://www.w3.org/TR/owl-time/) ontology to provide context for time-bound events in MUD

### MUD Items

Common objects and items used in a game world

### MUD Logic

Vocabulary defines Tasks and Actions conducted by agents in a game world

### MUD Content

Vocabulary used to describe content displayed to the user in text and image format. A vocabulary ultimately for defining user _perspective_

### MUD Dialogue

Vocabulary used in the definitions of decentralised parts of dialogue with characters

### MUD Fantasy

Vocabulary containing terms for commonly used fantasy themes

### MUD Combat

Provides definitions for a commonly used combat system mechanics

## Common

The common directory contains ontologies which are expected to be used frequently between games, and reusable utilities

### Shape Conform

Defines Utilities for testing that objects conform to shapes, in various contexts

### Maritime

Contains naval logic - i.e. about ships

# Contributing

We aim to follow the Inrupt Guidelines for writing ontologies. At the time of writing these are still contained in a [pull request branch](https://github.com/pmcb55/public-documentation/blob/feat/add-rdf-vocab-guidelines/coding-conventions/rdf-vocabulary-guidelines.md)
