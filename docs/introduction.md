# Introduction

The Transaction Access Point (TAP) is a persistently connected "peer" capable of sending and
receiving business documents, such as invoices. It interacts with other TAPs following the
protocol specified in this document. The TAP is an autonomous agent in business-to-business
document exchange.

A TAP might be provided by a commercial ledger service, or maintained as part of an
independent business system. 

The TAP specification has two parts. The main part (ausdigital-tap/2) defines the protocol all peers
must follow (and interfaces they must provide) to send and receive business documents. The
second part is an optional gateway specification (ausdigital-tapgw/1), which defines a client-server
protocol for trusted business system components (e.g. ledger services) to interact with independent TAP service providers in a generic way.


## Dependencies

The messages sent between TAPs carry semantic payloads. Currently, these include
ausdigital-bill/1.
That specification is maintained independently in the
[https://github.com/ausdigital/ausdigital-bill](https://github.com/ausdigital/ausdigital-bill)
repository. Future semantic payloads may be supported without change to the protocol.

All TAPs depend on the following Services:

 * ausdigital-dcl/1 
 * ausdigital-dcp/1 
 * ausdigital-nry/1 

TAPGW providers also depend on the
ausdigital-idp/1. TAPs do not need to
authenticate when they interact with each other, due to use of well known cryprograpic keys
and service endpoint addresses.


## TAP Protocol Overview

In this protocol, a Transaction Access Point (TAP) is a business system component that sends and receives business messages. The TAP Protocol describes how one TAP sends the message, and how the other TAP responds when a message is received.

The message is sent to the receiving TAP using HTTP POST operation, with a `Content-Type: multipart/form-data` body. This body contains two parts, `message` and `signature`.

The `message` part is a mixture of cleartext metadata (used by TAPs) and enciphered payload (used by trusted business system components). The cleartext metadata does not contain sensitive business information, whereas access to the business-sensitive information within the payload is not necessary for participating in the TAP protocol.

The `signature` part is created by a business system component trusted by the sender (with access to the sender's private key material). The signature can be used as a unique identifier of the message contents (e.g. transmitted document id).

![Illustration of POST body](./tap_overview_post.png "Business document sent to TAP")

Receiving TAPs may also use the signature as a filter (messages with invalid signatures MAY be dropped by receiving TAPs, rather than delivered). This allows TAPs to buffer trusted components from anonymous denial of service attacks.

When a valid message is received, the TAP issues an HTTP 200 status and returns a response body with `Content-Type: text/json`, containing a HATEOS-style list of callback URLs.

![Illustration of HTTP 200 response](./tap_overview_response.png "Response 200 OK")

See the TAP Protocol Details chapter for more information.
