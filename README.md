# pyevtx-rs

Python bindings for `https://github.com/omerbenamram/evtx/`.

## Installation

Available on PyPi - https://pypi.org/project/evtx/.

Wheels are currently built for:
- macOS (python 3.7)
- `manylinux1` (python3.5, python3.6, python3.7) 

And also sources are available, so having `setuptools-rust` and a recent nightly compiler should suffice for building it from sources.

To install from PyPi - `pip install evtx`


## Usage

The API surface is currently fairly limited (only yields events as XML documents), but is planned to be expanded in the future.

```python
from evtx.parser import PyEvtxParser


def main():
    parser = PyEvtxParser("./samples/Security_short_selected.evtx")
    for record in parser:
        print(f'Event Record ID: {record["event_record_id"]}')
        print(f'Event Timestamp: {record["timestamp"]}')
        print(record['data'])
        print(f'------------------------------------------')
```

This will print each record as an XML string.