# Send sms

    POST /messages/sms

## Input

*from*
    _Required_ *string* - The phone number from which the message is sent.

*to*
    _Required_ *string* - The phone number to which the message is sent.

*message*
    _Required_ *string* - The sms message that is sent, could be max 160 chars.

*repeat*
    *number* - The sms will be sent this number of times or until an url that
               will be attached to the message is clicked. If repeat is defined
               the message can only be 160-20 characters.

*repeat_interval*
    *number* - If *repeat* is defined the message will be sent every
               *repeat_interval* minute.

    {
        "from": "+46736265400",
        "to": "+46736265449",
        "message": "This is an sms message.",
        "repeat": 10,
        "repeat_interval": 5
    }

## Response

    Status: 201 Created
    Location: https://api.amivono.com/messages/sms/1
    X-RateLimit-Limit: 5000
    X-RateLimit-Remaining: 4999
    {
        "from": "+46736265400",
        "to": "+46736265449",
        "message": "This is an sms message. https://api.amivono.com/xkjskje34di",
        "last_sent_at": null,
        "repeat": 9,
        "repeat_interval": 5
        "created_at": "2011-04-22T13:33:48Z",
        "updated_at": "2011-04-22T13:33:48Z"
    }

# Send a voice message.

The gateway will make a call to a requlare phone and play a voice file.

    POST /messages/voice

## Input

*from*
    _Required_ *string* - The phone number from which the message is sent.

*to*
    _Required_ *string* - The phone number to which the message is sent.

*file*
    _Required_ *string* - The name of the voice file that will be played for
                          the answering person. The file must be uploaded to
                          the server already.

    {
        "from": "+46736265400",
        "to": "+46736265449",
        "file": "emergency.mp3"
    }

## Response

    Status: 201 Created
    Location: https://api.amivono.com/messages/sms/1
    X-RateLimit-Limit: 5000
    X-RateLimit-Remaining: 4999
    {
        "from": "+46736265400",
        "to": "+46736265449",
        "message": "This is an sms message.",
        "sent_at": null,
        "created_at": "2011-04-22T13:33:48Z",
        "updated_at": "2011-04-22T13:33:48Z"
    }
