# NDEF Library for Arduino

Read and Write NDEF messages on NFC Tags with Arduino.

NFC Data Exchange Format (NDEF) is a common data format that operates across all NFC devices, regardless of the underlying tag or device technology.

Modified to only include Ndef functionality without any NFC reader or tag specific code

### NfcTag

Reading a tag with the shield, returns a NfcTag object. The NfcTag object contains meta data about the tag UID, technology, size. When an NDEF tag is read, the NfcTag object contains a NdefMessage.

### NdefMessage

A NdefMessage consist of one or more NdefRecords.

The NdefMessage object has helper methods for adding records.

    ndefMessage.addTextRecord("hello, world");
    ndefMessage.addUriRecord("http://arduino.cc");

The NdefMessage object is responsible for encoding NdefMessage into bytes so it can be written to a tag. The NdefMessage also decodes bytes read from a tag back into a NdefMessage object.

### NdefRecord

A NdefRecord carries a payload and info about the payload within a NdefMessage.

### Specifications

This code is based on the "NFC Data Exchange Format (NDEF) Technical Specification" and the "Record Type Definition Technical Specifications" that can be downloaded from the [NFC Forum](http://www.nfc-forum.org/specs/spec_license).

## Warning

This software is in development. It works for the happy path. Error handling could use improvement. It runs out of memory, especially on the Uno board. Use small messages with the Uno. The Due board can write larger messages. Please submit patches.

## License

[BSD License](https://github.com/don/Ndef/blob/master/LICENSE.txt) (c) 2013-2014, Don Coleman
