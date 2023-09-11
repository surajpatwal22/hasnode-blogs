---
title: "React Fiber"
datePublished: Mon Sep 11 2023 14:04:05 GMT+0000 (Coordinated Universal Time)
cuid: clmeyg6o7000009jv36exd70x
slug: react-fiber
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/6f155320aa547818f2ab32b4be5d9ad6.jpeg
tags: reactjs, react-fiber

---

## INTRODUCTION

React Fiber is the core algorithm of React. The goal of react fiber is to increase its suitability for areas like animation, layout, and gesture. Its headline feature is **incremental rendering,** or the ability to split rendering work into chunks and spread it out over multiple frames.

Other key features include the ability to pause, abort, or reuse work as new updates come in, the ability to assign priority to different types of updates, and new concurrency primitives.

### What is reconciliation?

### **<mark>reconciliation</mark>**

The algorithm React uses to compare one tree with another to determine which parts need to be changed

Reconciliation is the algorithm behind what is popularly understood as the "virtual DOM." When you render a React application, a tree of nodes that describes the app is generated and saved in memory. This tree is then flushed to the rendering environment—for example, in the case of a browser application, it's translated to a set of DOM operations. When the app is updated (usually via iTunes`setState`), a new tree is generated. The new tree is compared with the previous tree to compute which operations are needed to update the rendered app.

### **<mark>Scheduling</mark>**

The process of determining when work should be performed.

The key points are:

* In a UI, every update doesn't need to be applied immediately; in fact, doing so can be wasteful, causing frames to drop and degrading the user experience.
    
* Different types of updates have different priorities — an animation update needs to be completed more quickly than, say, an update from a data store.
    
* A push-based approach requires the app (you, the programmer) to decide how to schedule work. A pull-based approach allows the framework (React) to be smart and make those decisions for you.
    

React doesn't currently take advantage of scheduling in a significant way; an update results in the entire subtree being re-rendered immediately. Overhauling React's core algorithm to take advantage of scheduling is the driving idea behind Fiber.

## What is a fiber?

We've established that a primary goal of Fiber is to enable React to take advantage of scheduling. Specifically, we need to be able to

* Pause work and come back to it later.
    
* assign priority to different types of work.
    
* reuse previously completed work.
    
* Abort work if it's no longer needed.
    

In order to do any of this, we first need a way to break work down into units. In one sense, that's what a fiber is. A fiber represents a **unit of work**.