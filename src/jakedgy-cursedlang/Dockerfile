# ============================================================================
# JAKEDGY CODEC - CURSEDLANG EDITION
# ============================================================================
# This Dockerfile builds the jakedgy compression algorithm implemented in
# CURSED - an esoteric programming language that combines Go-like semantics
# with Gen Z slang keywords, featuring Among Us pointer syntax.
#
# https://github.com/ghuntley/cursed
# ============================================================================

FROM debian:bookworm-slim AS builder

# Install dependencies for building (no cap fr fr)
RUN apt-get update && apt-get install -y \
    curl \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# Download the precompiled CURSED compiler (this is giving bestie)
RUN curl -L -o /usr/local/bin/cursed-compiler \
    https://github.com/ghuntley/cursed/releases/download/v0.0.1/cursed-compiler-linux-x64 \
    && chmod +x /usr/local/bin/cursed-compiler

# Copy source files
COPY codec.💀 .

# Compile the CURSED codec to native executable
RUN cursed-compiler --compile codec.💀 -o codec

# ============================================================================
# Runtime stage - keeping it minimal like our attention spans
# ============================================================================

FROM debian:bookworm-slim

WORKDIR /app

# Copy the compiled binary from builder
COPY --from=builder /app/codec /app/codec

ENTRYPOINT ["/app/codec"]
