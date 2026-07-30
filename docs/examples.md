# openbare examples

A decentralized, censorship-resistant web proxy network

## Example 1

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                            YOUR APPLICATION                             │
│                    (SperaxOS, Ultraviolet, etc.)                        │
└─────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                         OPENBARE CLIENT                                 │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐                      │
│  │ Server Pool │──│  Failover   │──│  Discovery  │                      │
│  │  Manager    │  │   Logic     │  │   Client    │                      │
│  └─────────────┘  └─────────────┘  └─────────────┘                      │
└─────────────────────────────────────────────────────────────────────────┘
                                    │
                    ┌───────────────┼───────────────┐
                    ▼               ▼               ▼
            ┌───────────┐   ┌───────────┐   ┌───────────┐
            │  Node 1   │   │  Node 2   │   │  Node 3   │
            │  (US)     │   │  (EU)     │   │  (Asia)   │
            │  Vercel   │   │ Cloudflare│   │  Railway  │
            └───────────┘   └───────────┘   └───────────┘
                    │               │               │
                    └───────────────┼───────────────┘
                                    ▼
                    ┌───────────────────────────────┐
                    │      OPENBARE REGISTRY        │
                    │   (Optional - Node Discovery) │
                    └───────────────────────────────┘
```

## Example 2

```bash
# Clone the repo
git clone https://github.com/nirholas/openbare.git
cd openbare

# Start the server
cd server
npm install
npm start

# Server running at http://localhost:8080
# Bare endpoint at http://localhost:8080/bare/
```

## Example 3

```bash
cd edge
npm install
npx wrangler login
npx wrangler deploy
```

## Example 4

```bash
docker build -t openbare ./server
docker run -d \
  -p 8080:8080 \
  -e NODE_ID=my-node \
  -e REGION=us-east \
  -e NODE_URL=https://your-public-url.example \
  openbare
```

## Example 5

```bash
cd server
npm install
npm start
```

## Example 6

```bash
# Node Identification
NODE_ID=my-bare-node          # Unique node ID
REGION=us-east                # Geographic region
NODE_URL=https://example.com  # Public URL

# Rate Limiting
RATE_LIMIT_MAX=100            # Requests per minute
RATE_LIMIT_WINDOW_MS=60000    # Window size

# Registry (Optional)
REGISTRY_URL=http://localhost:3000  # your own registry; no public one is hosted

# Logging
LOG_LEVEL=info                # trace/debug/info/warn/error
```

## Example 7

```bash
# Clone the repo
git clone https://github.com/nirholas/openbare.git
cd openbare

# Install all workspace dependencies
npm install

# Start server in dev mode
npm run dev:server

# Run tests
npm test
```


Every snippet above is taken from the [repository documentation](https://github.com/nirholas/openbare#readme).
