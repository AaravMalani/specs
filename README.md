# NowPower Design
This repository contains the specifications and designs for our app

## Structure
```
.
├── flows       # Contains MD files with user flows
│   ├── TEMPLATE.md  # Contains a template of user flows
│   ├── README.md    # Contains the specification of user flows
│   └── ...
├── design      # Contains MD files with app designs
│   ├── TEMPLATE.md  # Contains a template of screen designs
│   ├── README.md    # Contains the specification of screen designs 
│   └── ...
├── api         # Contains YAML files which describe the API details using the OpenAPI specification
│   ├── README.md   
│   ├── openapi.yaml # The root OpenAPI document which imports all other YAML documents
│   ├── auth.yaml    # Contains the auth-related API endpoint documentation
│   └── ...   
└── infra       # Contains MD files which describe an aspect of the future infrastructure deployment
    ├── README.md    # Contains the infrastructure specifications
    └── ...
```

The repository consists of 4 subdirectories, each describing a facet of the app's design
- The [`flows/`](./flows/) directory consists of the [user flows](https://www.figma.com/resource-library/user-flow/) which describe the usage of a certain aspect of the app. Progress can be viewed [here](https://github.com/theWatchMasters/specs/issues/1)
- The [`design/`](./design/) directory contains the designs of crucial views and screens.
- The [`api/`](./api/) directory contains the OpenAPI documents which store the interface details between the frontend and backend. Progress can be viewed [here](https://github.com/theWatchMasters/specs/issues/14)
- The [`infra/`](./infra/) directory consists of future deployment and infrastructure plans.