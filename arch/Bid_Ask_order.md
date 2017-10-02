| Name | Type | Description |
|-----|------|-------|
| ID | string | UUID |
| start_time | DATETIME | Virtual computer start of life (hour grained) |
| end_time | DATETIME | Virtual computer end of life (hour grained) |
| rating_buyer | MONEY | Buyer’s rating. Got from Buyer’s profile for BID orders |
| rating_supplier | MONEY | Supplier’s rating. Got from Supplier’s profile for ASK orders |
| id_buyer | EthereumID | Buyer’s ID. Got from Buyer’s profile for BID orders |
| id_supplier | EthereumID | Supplier’s ID. Got from Supplier’s profile for ASK orders |
| geo | REF(Geo) | Resource's location |
| price | NUMERIC | Order price per hour |
| order_type | Bid/Ask | |
| cpu | NUMERIC | CPU core count |
| ram | NUMERIC | Virtual computer RAM, in GB |
| storage | NUMERIC | Storage size, in GB |
| network | NUMERIC | Inbound or outbound traffic (the higher value), in GB |
| gpu | NUMERIC | GPU count |
| connections | INTEGER	| 0 - None, 1 - Outbound connections, 2 - Incoming connections |
| resProps | map[STRING] NUMERIC | Other properties/benchmarks. The higher means better |
