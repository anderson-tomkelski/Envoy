# Create entry register

```
bin/spire-server run -config conf/server/server.conf
bin/spire-server token generate -spiffeID spiffe://fiveg.org/myagent
bin/spire-agent run -config conf/agent/agent.conf -joinToken "1a1e4d51-e640-4a8f-9f8a-d0951ab56476"

bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/nrf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/amf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/ausf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/nssf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/udm -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/udr -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/pcf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/smf -selector unix:uid:$(id -u)
bin/spire-server entry create -parentID spiffe://fiveg.org/myagent     -spiffeID spiffe://fiveg.org/upf -selector unix:uid:$(id -u)
```