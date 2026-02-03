# ============================================================================
# JAKEDGY CODEC - CURSEDLANG EDITION
# ============================================================================
# This Dockerfile runs the jakedgy codec using the CURSED interpreter.
# Using interpreter mode since --compile causes segfaults in v0.0.1.
#
# https://github.com/ghuntley/cursed
# ============================================================================

FROM debian:bookworm-slim

# Install dependencies
RUN apt-get update && apt-get install -y \
    curl \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# Download the precompiled CURSED compiler
RUN curl -L -o /usr/local/bin/cursed-compiler \
    https://github.com/ghuntley/cursed/releases/download/v0.0.1/cursed-compiler-linux-x64 \
    && chmod +x /usr/local/bin/cursed-compiler

# Copy source file
COPY codec.💀 .

# Use interpreter mode (more stable than --compile in v0.0.1)
ENTRYPOINT ["cursed-compiler", "codec.💀"]
