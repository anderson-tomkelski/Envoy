# Create entry register

```
bin/spire-server run -config conf/server/server.conf
bin/spire-server token generate -spiffeID spiffe://example.org/myagent
bin/spire-agent run -config conf/agent/agent.conf -joinToken "1a1e4d51-e640-4a8f-9f8a-d0951ab56476"

bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/nrf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/amf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/ausf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/nssf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/udm -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/udr -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/pcf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/smf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://example.org/myagent     -spiffeID spiffe://example.org/upf -selector unix:uid:$(id -u)
```