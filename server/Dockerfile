# ============================================================================
# OpenBare Server Dockerfile
#
# Build context is this directory: `docker build -t openbare ./server`
#
# The npm lockfile lives at the repo root because `server` is an npm workspace,
# so it is not present in this build context and `npm ci` cannot run here.
# `npm install --omit=dev` resolves the same semver ranges from package.json.
# ============================================================================

FROM node:20-alpine AS production

# Add labels
LABEL org.opencontainers.image.title="OpenBare Server"
LABEL org.opencontainers.image.description="A decentralized, censorship-resistant web proxy server"
LABEL org.opencontainers.image.source="https://github.com/nirholas/openbare"
LABEL org.opencontainers.image.licenses="SEE LICENSE IN LICENSE"

# Create non-root user for security
RUN addgroup -g 1001 -S openbare && \
    adduser -S openbare -u 1001

WORKDIR /app

# Install production dependencies only
COPY package.json ./
RUN npm install --omit=dev --no-audit --no-fund && \
    npm cache clean --force

# Copy source files
COPY *.js ./

# Change ownership to non-root user
RUN chown -R openbare:openbare /app

# Switch to non-root user
USER openbare

# Expose port (default 8080)
EXPOSE 8080

# Health check
HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 \
    CMD wget --no-verbose --tries=1 --spider http://localhost:8080/health || exit 1

# Environment variables with defaults
ENV NODE_ENV=production \
    PORT=8080 \
    HOST=0.0.0.0 \
    LOG_LEVEL=info

# Start server
CMD ["node", "index.js"]
