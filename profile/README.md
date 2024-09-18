# Table of contents

[The product data network buildingenvelopedata.org](#the-product-data-network-buildingenvelopedata.org)

[Repositories and websites](#repositories-and-websites)

[Video introduction to the product data network](#video-introduction-to-the-product-data-network)

[Acknowledgements](#acknowledgements)

# The product data network buildingenvelopedata.org

The GitHub organization `building-envelope-data` contains several repositories. All of them relate to the product data network buildingenvelopedata.org. The aim of the network is that planning software for building envelopes can directly access product data servers from manufacturers of components. The planners / architects / engineers should not have to search for the product data manually and handle them manually. The product data network can make the planning of energy-efficient buildings faster, easier and better. It connects a large amount of product data with many software applications and the architects / planners / engineers who use them.

![simple_overview_product_data_network_d70](https://user-images.githubusercontent.com/33456252/231476911-b97ef636-0c1e-4d80-9828-a82a9f1faac5.png)

# Repositories and websites

The repository [api](https://github.com/building-envelope-data/api) contains the specification of the application programming interface of the product data network.

The repository [database](https://github.com/building-envelope-data/database) is a reference implementation of a product data server. It can be used to create additional product data servers easily.

The repository [metabase](https://github.com/building-envelope-data/metabase) contains the code of the metabase. The metabase manages unique identifiers for components and institutions. It can also receive queries which is forwards to all product data servers and returns their responses. The backend of the metabase can be accessed by its [GraphQL endpoint](https://www.buildingenvelopedata.org/graphql/). The frontend of the metabase is the website [buildingenvelopedata.org](https://www.buildingenvelopedata.org/). It is based on the [GraphQL endpoint](https://www.buildingenvelopedata.org/graphql/). The frontend is helpful for human beings to understand the product network. Software applications will directly use the GraphQL endpoints of the metabase and of the product data servers.

The repository [machine](https://github.com/building-envelope-data/machine) can be used to prepare a server. Then, an instance of the repository [database](https://github.com/building-envelope-data/database) can run on this server.

# Video introduction to the product data network

[![Watch the video introduction](https://img.youtube.com/vi/QsulJnpvuh0/maxresdefault.jpg)](https://www.youtube.com/watch?v=QsulJnpvuh0)

# Acknowledgements

This work was funded by the German Federal Ministry for Economic Affairs and Climate Action under Grants 03ET1560A and 03EN1070A, based on a decision by the German Bundestag, by a Fraunhofer ICON Grant and by the Assistant Secretary for Energy Efficiency and Renewable Energy, Building Technologies Program, of the U.S. Department of Energy, under Contract No. DE-AC02-05CH11231.

<img src="https://user-images.githubusercontent.com/33456252/231481868-cd122279-287d-4928-9f24-71172c1fefda.png" width="250">
