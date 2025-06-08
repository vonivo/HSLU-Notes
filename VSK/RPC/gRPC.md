gRPC ist eine Implementation von Google von [[VSK/RPC/RPC|RPC]].
gRPC ist:
- Plattform- und Sprachübergreifend
- Verwendet Google Protoco Buffers
- Basiert auf HTTP/2

Eine Nachricht in GRPC wird über Protocol Buffers definiert:
```proto
syntax = "proto3";

message SearchRequest {
	string query = 1;
	int32 page_number = 2;
	int32 result_per_page = 3;
}

message SearchResult {
// weitere Message-Definitionen
}
```
Jedem Attribute muss eine eindeutige ID für das Binäre Format vergeben werden.

Mithilfe von `protoc` werden die Definierten Messages in der Zielsprache generiert.

Ebenso werden die Schnitstellen in Proto definiert:
```
syntax = "proto3";

service EchoService {
	rpc echo(EchoRequest) returns (EchoResponse);
}
```

