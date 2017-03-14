---
title: Testing an event with the events manager
categories:
- event data
layout: articles
---

# How to test an event in the event manager

Vero is designed to send automated campaigns when a customer triggers specific events. Usually these events are fired from your website or application using the Vero Javascript API or one of the many other methods you can read about on the [Vero Developers API documentation]({{site.data.links.vero_api}}). 

Test an automated email workflow means firing an event which in turn triggers a campaign or makes the customer enter a specific segment. You can do this by emulating a customer on your website or application **or** you can use the event manager to manually fire an event inside Vero. This can be used before or after you have installed the Vero library. 

## Testing an event

In the [events manager]({{site.data.links.event-manager}}), choose the event you would like to test. You can see which events have campaigns associated with them in the list or event details view. 

1. Click on the **Test** button in the details view of the chosen event.

2. Choose a customer you would like to test this event for by searching for their customer ID or email address. You can also fire a test event for a new customer by choosing **New customer**.

3. Add event properties (optional) - If you want to pass a particular property to a campaign that requires it, you can add those properties by selecting the ‘Inclode event properties’ option.

4. Hit the **Send** button to send this event.

## *Warning* 

*Remember that even though you are testing the event, it will show up in the logs for the chosen customer, and will affect the actual campaigns and segments you have setup. If you are testing this event on a **Live mode** project, this may result in real customers receiving emails.*

*We recommend you test events in a **Test mode** project to avoid accidentally sending emails to customers. Note that when testing in a test mode project, the customer may receive emails when the project is later changed to live mode due to those events being treated as real events.*