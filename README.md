# OBBB VIN Decoder

A web application that checks whether a vehicle meets the vehicle-related requirements for the federal auto loan interest deduction created by the One Big Beautiful Bill Act (OBBBA).

## Status

**Research Phase Complete**

This repository contains the research findings and data architecture decisions necessary to build the application. Implementation has not yet begun, as per the requirements to first complete thorough research.

## Documents

- [`docs/research.md`](docs/research.md): Research on NHTSA/vPIC data, OBBBA requirements, and feasibility of a $0/client-side architecture
- [`docs/data-architecture.md`](docs/data-architecture.md): Detailed specification of the static dataset extraction, optimization, and lookup architecture

## Next Steps

Upon approval of the research and data architecture, the next phases would be:

1. Implement the data processing pipeline (`scripts/process_nhtsa.py`)
2. Build the React/TypeScript frontend with Vite
3. package static data for client-side use
4. Test VIN validation and rules engine
5. Implement bulk CSV/TXT processing
6. Deploy to Firebase Hosting

## Key Findings

- NHTSA vPIC database provides all necessary data for VIN decoding: make, model, model year, vehicle type, body class, GVWR, and plant location
- The database can be preprocessed into a compact static dataset (~4 MB gzipped) suitable for browser download
- Client-side lookup enables zero-cost bulk processing (no per-VIN API requests)
- Architecture meets all $0/month requirements when hosted on Firebase Hosting
- Application distinguishes between vehicle-related requirements (determinable from VIN) and taxpayer-specific requirements (not determinable from VIN)

## Requirements Met

 Research completed before implementation
 $0 cost architecture prioritized (static files + browser processing)
 No paid services, APIs, or infrastructure required
 Focus on what can actually be determined from VIN/NHTSA data
 Clear separation of vehicle vs. taxpayer requirements
