# Events

- [Introduction](#introduction)
- [Available Events](#available-events)

<a name="introduction"></a>
## Introduction

ZEDx includes a variety of events.

Whenever something of importance is about to happen, is happening, or has just happened, ZEDx fires an `Event`. As an Extension developer, your job is pretty simple: `listen` for the events you're interested in, and react accordingly.

For example:

<div class="content-list" markdown="1">
- When an `Ad` is validated by an Administrator, ZEDx fires the `AdWasValidated` event. A "Twitter Feed" Extension could listen for this event and react by sending a tweet with the ad's title and URL.
- When an `Ad` is about to be created by a user, ZEDx fires the `AdWillBeCreated` event. A "NoSpam" Extension could listen for this event and react by checking the Ad content.
</div>

Get the idea? Great!

<a name="available-events"></a>
## Available Events

<style>
    .collection-method-list > p {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
    }

    .collection-method-list a {
        display: block;
    }
</style>

### Ad

<div class="collection-method-list" markdown="1">
[AdRenewRequested](#AdRenewRequested)
[AdWasBanned](#AdWasBanned)
[AdWasCreated](#AdWasCreated)
[AdWasDeleted](#AdWasDeleted)
[AdWasExpired](#AdWasExpired)
[AdWasHold](#AdWasHold)
[AdWasUpdated](#AdWasUpdated)
[AdWasValidated](#AdWasValidated)
[AdWillBeCreated](#AdWillBeCreated)
[AdWillBeDeleted](#AdWillBeDeleted)
[AdWillBeDisplayed](#AdWillBeDisplayed)
[AdWillBeModerated](#AdWillBeModerated)
[AdWillBePreviewed](#AdWillBePreviewed)
[AdWillBeUpdated](#AdWillBeUpdated)
</div>

### Admin

<div class="collection-method-list" markdown="1">
[AdminWasLoggedIn](#AdminWasLoggedIn)
[AdminWasUpdated](#AdminWasUpdated)
[AdminWillBeLoggedOut](#AdminWillBeLoggedOut)
[AdminWillBeUpdated](#AdminWillBeUpdated)
</div>

### Adtype

<div class="collection-method-list" markdown="1">
[AdtypeWasCreated](#AdtypeWasCreated)
[AdtypeWasDeleted](#AdtypeWasDeleted)
[AdtypeWasPurchased](#AdtypeWasPurchased)
[AdtypeWasUpdated](#AdtypeWasUpdated)
[AdtypeWillBeCreated](#AdtypeWillBeCreated)
[AdtypeWillBeDeleted](#AdtypeWillBeDeleted)
[AdtypeWillBeUpdated](#AdtypeWillBeUpdated)
</div>

### Cache

<div class="collection-method-list" markdown="1">
[CacheAdminWasUpdated](#CacheAdminWasUpdated)
[CacheAdtypeWasUpdated](#CacheAdtypeWasUpdated)
[CacheAdWasUpdated](#CacheAdWasUpdated)
[CacheCategoryWasUpdated](#CacheCategoryWasUpdated)
[CacheFieldWasUpdated](#CacheFieldWasUpdated)
[CacheIpWasUpdated](#CacheIpWasUpdated)
[CacheMenuWasUpdated](#CacheMenuWasUpdated)
[CachePageWasUpdated](#CachePageWasUpdated)
[CacheSettingWasUpdated](#CacheSettingWasUpdated)
[CacheSubscriptionWasUpdated](#CacheSubscriptionWasUpdated)
[CacheTemplateWasUpdated](#CacheTemplateWasUpdated)
[CacheUserWasUpdated](#CacheUserWasUpdated)
</div>

### Category

<div class="collection-method-list" markdown="1">
[CategoryWasCreated](#CategoryWasCreated)
[CategoryWasDeleted](#CategoryWasDeleted)
[CategoryWasMoved](#CategoryWasMoved)
[CategoryWasUpdated](#CategoryWasUpdated)
</div>

### Field

<div class="collection-method-list" markdown="1">
[FieldWasCreated](#FieldWasCreated)
[FieldWasDeleted](#FieldWasDeleted)
[FieldWasUpdated](#FieldWasUpdated)
[FieldWillBeCreated](#FieldWillBeCreated)
[FieldWillBeUpdated](#FieldWillBeUpdated)
</div>

### Ip

<div class="collection-method-list" markdown="1">
[IpWillBeBlacklisted](#IpWillBeBlacklisted)
[IpWillBeRemovedFromBlacklist](#IpWillBeRemovedFromBlacklist)
[IpWillBeRemovedFromWhitelist](#IpWillBeRemovedFromWhitelist)
[IpWillBeWhitelisted](#IpWillBeWhitelisted)
</div>

### Menu

<div class="collection-method-list" markdown="1">
[MenuWasCreated](#MenuWasCreated)
[MenuWasDeleted](#MenuWasDeleted)
[MenuWasMoved](#MenuWasMoved)
[MenuWasUpdated](#MenuWasUpdated)
[MenuWillBeCreated](#MenuWillBeCreated)
[MenuWillBeUpdated](#MenuWillBeUpdated)
</div>

### Page

<div class="collection-method-list" markdown="1">
[PageTemplateWasSwitched](#PageTemplateWasSwitched)
[PageThemeelementWasAttached](#PageThemeelementWasAttached)
[PageThemeelementWasDetached](#PageThemeelementWasDetached)
[PageWasCreated](#PageWasCreated)
[PageWasDeleted](#PageWasDeleted)
[PageWasUpdated](#PageWasUpdated)
[PageWillBeCreated](#PageWillBeCreated)
[PageWillBeUpdated](#PageWillBeUpdated)
</div>

### Payment

<div class="collection-method-list" markdown="1">
[PaymentWasReceived](#PaymentWasReceived)
</div>

### Search Engine

<div class="collection-method-list" markdown="1">
[SearchEngineRequested](#SearchEngineRequested)
[SearchEngineWillRender](#SearchEngineWillRender)
</div>

### Setting

<div class="collection-method-list" markdown="1">
[SettingWasUpdated](#SettingWasUpdated)
[SettingWillBeUpdated](#SettingWillBeUpdated)
</div>

### Subscription

<div class="collection-method-list" markdown="1">
[SubscriptionWasCreated](#SubscriptionWasCreated)
[SubscriptionWasDeleted](#SubscriptionWasDeleted)
[SubscriptionWasPurchased](#SubscriptionWasPurchased)
[SubscriptionWasSwaped](#SubscriptionWasSwaped)
[SubscriptionWasUpdated](#SubscriptionWasUpdated)
[SubscriptionWillBeCreated](#SubscriptionWillBeCreated)
[SubscriptionWillBeUpdated](#SubscriptionWillBeUpdated)
</div>

### Template

<div class="collection-method-list" markdown="1">
[TemplateWasCreated](#TemplateWasCreated)
[TemplateWasDeleted](#TemplateWasDeleted)
[TemplateWasUpdated](#TemplateWasUpdated)
[TemplateWillBeCreated](#TemplateWillBeCreated)
[TemplateWillBeUpdated](#TemplateWillBeUpdated)
</div>

### User

<div class="collection-method-list" markdown="1">
[UserWasCreated](#UserWasCreated)
[UserWasDeleted](#UserWasDeleted)
[UserWasUpdated](#UserWasUpdated)
[UserWillBeCreated](#UserWillBeCreated)
[UserWillBeDeleted](#UserWillBeDeleted)
[UserWillBeUpdated](#UserWillBeUpdated)
</div>
