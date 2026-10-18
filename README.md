
# twilio-csharp

This [SDK](https://github.com/sdk-fabric/twilio-csharp) is managed by the [SDK Fabric](https://sdk-fabric.org/) project, a global infrastructure to
automatically generate SDKs for every API.

You can find more information about this SDK at [TypeHub](https://typehub.cloud/):
https://app.typehub.cloud/d/sdkfabric/twilio

## Usage

```csharp
using SdkFabric.Twilio.Client;

Client client = Client.Build("[access_token]")

// Delete the Media resource.
object response = client.Media().delete("accountSid", "messageSid", "sid");

// Fetch a single Media resource associated with a specific Message resource.
Media response = client.Media().get("accountSid", "messageSid", "sid");

// Read a list of Media resources associated with a specific Message resource.
Media_Collection response = client.Media().getAll("DateCreated", 1, 1, "PageToken", "accountSid", "messageSid");

// Send a message (SMS, MMS, WhatsApp or other channel).
Message response = client.Messages().create("accountSid", new object());

// Deletes a Message resource from your account.
object response = client.Messages().delete("accountSid", "sid");

// Fetch a specific Message.
Message response = client.Messages().get("accountSid", "sid");

// Retrieve a list of Message resources associated with a Twilio Account.
Message_Collection response = client.Messages().getAll("DateSent", "From", 1, 1, "PageToken", "To", "accountSid");

// Update a Message resource (used to redact Message `body` text and to cancel not-yet-sent messages).
Message response = client.Messages().update("accountSid", "sid", new object());
```
