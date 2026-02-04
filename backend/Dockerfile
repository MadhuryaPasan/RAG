FROM python:3.13.11-trixie

# Copy uv from the official image
# Install uv via pip to avoid registry auth issues
RUN pip install uv

# Install curl for healthcheck
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

# Create a non-root user with a home directory
RUN useradd -m -u 1000 appuser

# Set working directory
WORKDIR /app

# Change ownership of the working directory to the non-root user
RUN chown appuser:appuser /app

# Switch to the non-root user
USER appuser

# Copy dependency files with correct ownership
COPY --chown=appuser:appuser pyproject.toml uv.lock ./

# Install dependencies using a cache mounted for the specific user
RUN --mount=type=cache,target=/home/appuser/.cache/uv,uid=1000,gid=1000 \
    uv sync

# Copy the rest of the application code with correct ownership
COPY --chown=appuser:appuser . .

# Install the project
RUN --mount=type=cache,target=/home/appuser/.cache/uv,uid=1000,gid=1000 \
    uv sync

# Run the application
CMD ["uv", "run", "fastapi", "dev", "app/main.py", "--port", "8000", "--host", "0.0.0.0"]