Apple Push Notification
=====================

This plugin helps you using the Apple Push Notification system.

Once you have the certificate from Apple for your application, export your key
and the apple certificate as p12 files and run :

    openssl pkcs12 -in cert.p12 -out apple_push_notification.pem -nodes -clcerts
    put apple_push_notification.pem in config/

Example
=======

    $ rake apn:migrate
    $ ./script/console
    >> a = ApplePushNotification.new
    >> a.device_token = "c079040a 7d78c3de a68c813e 6b0c1fc1 e5d03d38 b661f715 XXXXXXXX XXXXXXXX"
    >> a.badge = 5
    >> a.sound = true
    >> a.alert = "foobar"
    >> a.send_notification
    => nil

Copyright (c) 2009 Fabien Penso.

Will be released under the MIT license once Apple release its SDK.