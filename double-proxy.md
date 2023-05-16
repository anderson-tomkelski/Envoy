# Configuring SPIRE Envoy

```
wget https://github.com/spiffe/spire/releases/download/v1.6.3/spire-1.6.3-linux-x86_64-glibc.tar.gz
tar -xvzf spire-1.6.3-linux-x86_64-glibc.tar.gz
rm spire-1.6.3-linux-x86_64-glibc.tar.gz

# Change SPIRE Agent and Server configuration files

# Run SPIRE Server
./spire-server run -config ../conf/server/server.conf

# Run SPIRE Agent
TOKEN=$((./spire-server token generate -spiffeID spiffe://example.org/agent)| awk '{print $2}')
./spire-agent run -joinToken $TOKEN -config ../conf/agent/agent.conf

# Create entry register for envoy server
./spire-server entry create     -selector unix:uid:${UID}     -socketPath /tmp/spire-server/private/api.sock     -spiffeID spiffe://example.org/server     -parentID spiffe://example.org/agent

# Run envoy server

envoy -c server.yaml

# Create entry register for envoy client

./spire-server entry create     -selector unix:uid:${UID}     -socketPath /tmp/spire-server/private/api.sock     -spiffeID spiffe://example.org/client     -parentID spiffe://example.org/agent

# Run envoy client
envoy -c client.yaml --base-id 1 # --base-id 1??


# Run service

python3 server.py


```