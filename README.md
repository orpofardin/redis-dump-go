# redis-dump-go

Backing up Redis gives you a copy of your data to restore later. redis-dump-go is a Redis backup and restore tool written in Go, for developers who need to dump Redis data from the command line.

## Features

- Export Redis data to a backup file.
- Restore exported data to a Redis server.
- Build a command-line executable with Go.

## Installation

Install Go, then run these commands from the root of your redis-dump-go checkout:

```sh
go build -o redis-dump-go .
```

The executable will be created in the current directory. The restore example below also requires `redis-cli`.

## Usage

Example: dump a local Redis server to a file using explicit host and port arguments:

```sh
./redis-dump-go -host 127.0.0.1 -port 6379 > backup.resp
```

Restore the RESP commands with `redis-cli`:

```sh
redis-cli -h 127.0.0.1 -p 6379 --pipe < backup.resp
```

**Restore into a separate Redis instance first.** Replaying a backup can change existing data. Keep the backup file private if your Redis data contains credentials or other sensitive values.

## License

MIT. This project is based on [yannh/redis-dump-go](https://github.com/yannh/redis-dump-go). Retain the upstream copyright notice and MIT license text when redistributing its code.

## Related projects

The following repositories were supplied as other projects from the same author. Their functionality was not documented in the available source material.

- [RedZinXL/warc-gpt](https://github.com/RedZinXL/warc-gpt): consult its README for its purpose and usage.
- [Songraf/stagerag](https://github.com/Songraf/stagerag): consult its README for its purpose and usage.
- [mellyyup789-collab/java-microservice](https://github.com/mellyyup789-collab/java-microservice): consult its README for its purpose and usage.

