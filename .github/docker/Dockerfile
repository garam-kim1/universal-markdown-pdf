
FROM pandoc/extra:3.6.4-ubuntu

# Run all the installation commands ONCE during the image build
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    fonts-noto-cjk \
    nodejs \
    npm \
    libnss3 \
    libatk1.0-0 \
    libatk-bridge2.0-0 \
    libcups2 \
    libdrm2 \
    libxkbcommon0 \
    libxcomposite1 \
    libxdamage1 \
    libxfixes3 \
    libxrandr2 \
    libgbm1 \
    libpango-1.0-0 \
    libcairo2 \
    libasound2t64 && \
    # Clean up apt cache to keep the image small
    rm -rf /var/lib/apt/lists/*

# Install Node.js packages for pandoc filters
RUN npm install --global mermaid-filter pandoc-plantuml

# Configure puppeteer for mermaid-filter
RUN echo '{"args": ["--no-sandbox", "--disable-setuid-sandbox"]}' > /root/.puppeteer.json