Adding Devices
==============

Adding devices within UH VPN can be done by clicking the "Add New Device" button
at the bottom of a person's page within a UH VPN group. After clicking, one will then
be presented with a list of fields to fill in as follows:

* **Name** : Name for the device in question, e.g. macOS, iOS, Android or Windows.
* **Expiry Date** : If device expiry is desired, one can specify an expiry date here.
  If a date is not specified, the device will never expire until manual revocation
  occurs via deletion.
* **Expiry Time** : If an expiry date is specified, the time can also be specified
  to provide an increased granularity with respect to expiry. All times should be entered
  in 24 hour format and will be taken as GMT.

Upon device submission, the above fields will be validated and submitted. If submission
succeeds, the person in question will be sent an email containing a one-time-passcode (OTP)
for entry into a UH VPN client application. Once this code is entered, all relevant configurations
such as server information, cryptography and app branding information is securely sent to the device.
Secure dynamic updates will occur automatically for UH VPN clients allowing administrators to change
server settings, group parameters and more without any impact to end clients, thus simplifying VPN
deployments hugely.

Once a user has redeemed their OTP code, the OTP field for the device in question on the person's page
will change from |pending_otp| to |ok_otp|. If redemption fails to occur within the time period
set by the group's "device registration timeout", the OTP icon will change to |failed_otp| and the device
will need to be deleted and a new one created.

.. note::
    If using custom branding on enterprise groups, UH VPN device enrollment emails are custom branded
    to your specification.

.. |pending_otp| image:: /_static/icons/primitive-dot-orange.svg
  :alt: Pending OTP

.. |ok_otp| image:: /_static/icons/check_green.svg
  :alt: Redeemed OTP

.. |failed_otp| image:: /_static/icons/x_red.svg
  :alt: Failed OTP