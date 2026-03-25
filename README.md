# Orchard Systematic — Contracts

Shared Protobuf message definitions and gRPC service interfaces for the Orchard Systematic trading platform.

## Structure

```
proto/orchard/
├── common/v1/        # Shared types: InstrumentId, Side, DecimalValue, enums
├── marketdata/v1/     # MarketDataTick, OhlcvBar, ForwardCurve, MarketDataService
├── signals/v1/        # Signal, SignalCommand, StrategyState, SignalService
└── execution/v1/      # Order, Fill, Position, PortfolioSummary, ExecutionService
```

## Usage

### Install Buf CLI

```bash
# macOS / Linux
curl -sSL https://buf.build/docs/installation | sh
```

### Lint

```bash
buf lint
```

### Generate code for all languages

```bash
buf generate
```

Generated stubs are output to:
- `gen/csharp/` — for the OMS (.NET)
- `gen/python/` — for the strategy-engine
- `gen/typescript/` — for the dashboard (Next.js)
- `gen/cpp/` — for grove (C++ numerics)

### Breaking change detection

```bash
buf breaking --against '.git#branch=main'
```

## Consuming Generated Code

| Language | Package | Install |
|----------|---------|---------|
| C# | `OrchardSystematic.Contracts` | NuGet via GitHub Packages |
| Python | `orchard-contracts` | `uv add` from GitHub Packages |
| TypeScript | `@orchard-systematic/contracts` | npm from GitHub Packages |
| C++ | CMake FetchContent | Direct from this repo |
