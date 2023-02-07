---
layout: single
title:  "Delegates and Events in C# "
categories: C#
tag: [C#, Delegates, Events]
toc: false
author_profile: false
sidebar:
    nav: "counts"
---

C# is a powerful language that provides plenty of features for developers to work with. One of those features is delegates and events. Delegates are powerful type-safe functions that can be used for many things including events and callbacks. Events, on the other hand, provide a way for objects to communicate with each other by raising events and handling them. In this article, we'll explore what delegates and events are and how to use them in C#.

## What are Delegates?

Delegates are special types of objects that allow developers to store a reference to a function in a variable. This function can then be called upon whenever needed. In C#, delegates are declared using the `delegate` keyword, followed by the return type and parameters of the function that the delegate is referencing.

For example, consider the following delegate declaration:

```csharp
public delegate void MyDelegate(string message);
```

This declaration creates a delegate type called `MyDelegate` which can store a reference to any function with a `string` parameter and a `void` return type. To create an instance of this delegate, we use the `new` keyword and pass in the function that we want the delegate to reference.

For example, consider the following function:

```csharp
public void PrintMessage(string message)
{
    Console.WriteLine(message);
}
```

We can create an instance of `MyDelegate` and set it to reference this function as follows:

```csharp
MyDelegate myDelegate = new MyDelegate(PrintMessage);
```

We can then call the delegate instance by using the `Invoke` method as follows:

```csharp
myDelegate.Invoke("Hello World!");
```

The above code will print the message `Hello World!` to the console.

## What are Events?

Events are a way for objects to communicate with each other. An object can raise an event to notify other objects in the system of something that has happened. Those objects can then handle the event and take appropriate action. In C#, events are declared using the `event` keyword, followed by the type of the event and then the name of the event.

For example, consider the following event declaration:

```csharp
public event EventHandler<MessageEventArgs> MessageReceived;
```

This declaration creates an event called `MessageReceived` of type `EventHandler<MessageEventArgs>`. This event can then be raised whenever an object wants to notify other objects of a message being received.

To raise the event, we use the `RaiseEvent` method as follows:

```csharp
MessageReceived?.Invoke(this, new MessageEventArgs(message));
```

This code will raise the `MessageReceived` event and pass in the message as an argument. Other objects that are listening for this event can then handle it and take appropriate action.

## Combining Delegates and Events

Now that we understand both delegates and events, let's look at how they can be combined to create a powerful event-driven system. To do this, we'll use the `+=` and `-=` operators to add or remove event handlers from an event.

For example, consider the following code:

```csharp
public delegate void MessageReceivedHandler(string message);

public event MessageReceivedHandler MessageReceived;

public void OnMessageReceived(string message)
{
    MessageReceived?.Invoke(message);
}

public void AddMessageReceivedHandler(MessageReceivedHandler handler)
{
    MessageReceived += handler;
}

public void RemoveMessageReceivedHandler(MessageReceivedHandler handler)
{
    MessageReceived -= handler;
}
```

The code above defines a delegate type called `MessageReceivedHandler`, an event of that type called `MessageReceived` and two methods for adding and removing event handlers. We can then use the `AddMessageReceivedHandler` method to add event handlers to the event.

For example, consider the following code:

```csharp
MessageReceivedHandler handler = (message) => Console.WriteLine(message);
AddMessageReceivedHandler(handler);
```

This code adds an event handler to the `MessageReceived` event which will print the message to the console. We can then use the `OnMessageReceived` method to raise the event as follows:

```csharp
OnMessageReceived("Hello World!");
```

The above code will raise the `MessageReceived` event and the event handler will print the message to the console.

## Conclusion

In this article, we explored what delegates and events are and how to use them in C#. We saw how to declare delegates and events and how to combine them to create a powerful event-driven system. We also saw how to add and remove event handlers using the `+=` and `-=` operators.
