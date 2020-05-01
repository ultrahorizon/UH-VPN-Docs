Group Billing
=============

Billing for UH VPN is handled at a group level and not at a user level. As such administrators of groups
can easily control how each group is financed. UH VPN holds card details for premium groups through it's
payment partner, Stripe. All card details are held securely by Stripe, and billing occurs monthly at a
rate of £1 +VAT per device used in a monthly period. For example, if a group contains 3 people each with
2 devices, the bill would be £6 +VAT.

Group billing is handled in the group settings page which can be accessed by clicking the |settings_icon|
icon next to the associated group in the `management page`_. Here, one is able to view their billing period,
card details (shown dynamically in the card image), utilisation rate and pending charges.

Upgrading to Premium
~~~~~~~~~~~~~~~~~~~~

Upgrading to premium can be done by clicking the "Upgrade to Premium" button at the base of the group
settings page. One will then be presented with a card collection modal. Once card details have been
entered and verified, the group will immediately transition onto the premium tier and all associated
features will be unlocked.

Updating Card Details
~~~~~~~~~~~~~~~~~~~~~

If card details need to be updated. For example, card currently used has expired. This can be accomplished
by clicking the "Update Card Details" button at the base of the group settings page. One will then be
presented with a card collection modal. Once card details have been entered and verified, the new card will
overwrite the old card and billing will continue as normal.

Cancelling Subscription
~~~~~~~~~~~~~~~~~~~~~~~

If one wishes to cancel their UH VPN subscription, this can be accomplished by clicking the
"Cancel Subscription" button at the base of the group settings page. Once cancelled, the group
will remain on the premium tier until the end of the billing cycle; at which point a final bill
will be taken and the group will transition back to the free plan.

It is important to note that if any of the below conditions are met, the group will be frozen,
all authentications will fail and actions must be taken either to upgrade back to the premium tier,
or to remedy any of the situations defined below:

* More than one administrator is associated to a group.
* More than two devices are defined within a group.
* A free group is already associated with the user account.


.. |settings_icon| image:: /_static/icons/gear.svg
  :alt: Edit Icon

.. _management page: https://uh-vpn.com/manage