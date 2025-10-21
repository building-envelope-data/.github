# Table of contents

[The product data network buildingenvelopedata.org](#the-product-data-network-buildingenvelopedata.org)

[Repositories and websites](#repositories-and-websites)

[Video introduction to the product data network](#video-introduction-to-the-product-data-network)

[How can I add my product data to the product data network?](#how-can-i-add-my-product-data-to-the-product-data-network)

[How can I use the product data network with my software application?](#how-can-i-use-the-product-data-network-with-my-software-application)

[Do you have any other question?](#do-you-have-any-other-question)

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

# How can I add my product data to the product data network?

When you are a manufacturer of building envelope components and part of an association, you can ask your association if they provide a database which is connected to the product data network.

If you have your own product database, you can ask your software developers to add an API according to the specification https://github.com/building-envelope-data/api . There are [many open-source frameworks](https://graphql.org/community/tools-and-libraries/) which make it easy to create such an API. The software developers need to take your product data and to return the datasets in the format defined by https://github.com/building-envelope-data/api/tree/develop/schemas . For example, optical datasets must be valid against https://github.com/building-envelope-data/api/blob/develop/schemas/opticalData.json . An example of such a dataset is https://github.com/building-envelope-data/api/blob/develop/tests/valid/opticalData/solarTransmittanceReflectance.json . Please also [raise an issue](https://github.com/building-envelope-data/api/issues/new) so that we know what you are planning.

The next important step is to synchronize the manufacturers (institutions) and products (components) of your database with the metabase. Please check for each institution and component, if they are already registered in the metabase. The [example queries of the repository](https://github.com/building-envelope-data/api/blob/develop/requests/metabase/tutorial.graphql) `api` are helpful for this. If an institution or component is not yet registered in the metabase, please use the mutations [`createInstitution`](https://github.com/building-envelope-data/api/blob/d73de92209c51c17ba146b01e734e38abc9b3ef8/apis/metabase.graphql#L1381) and [`createComponent`](https://github.com/building-envelope-data/api/blob/d73de92209c51c17ba146b01e734e38abc9b3ef8/apis/metabase.graphql#L1372) to register them in the metabase. Please establish a process that institutions and components are synchronized with the metabase if there are changes in the metabase or your database.

When your database with the new API is ready, we can connect them easily to the product data network. Your product data can then be accessed by all software applications which use the product data network. As part of the [access right management](https://github.com/building-envelope-data/metabase?tab=readme-ov-file#access-right-management-single-sign-on), you can restrict the access to certain application, institutions or users.

# How can I use the product data network with my software application?

Your planning application needs to send a GraphQL query to the metabase https://www.buildingenvelopedata.org/graphql/ . The API of the metabase is specified by https://github.com/building-envelope-data/api . At https://github.com/building-envelope-data/api/blob/develop/requests/metabase/tutorial.graphql , you find example queries to the metabase.

The GraphQL queries are used fo the metadata of datasets to find suitable datasets. The GraphQL querie to the metabase must be valid against https://github.com/building-envelope-data/api/blob/develop/apis/metabase.graphql . A dataset itself is a JSON blob which must be valid against the JSON schemas https://github.com/building-envelope-data/api/tree/develop/schemas . Optical datasets must be valid against https://github.com/building-envelope-data/api/blob/develop/schemas/opticalData.json .

The screenshot shows an example of a GraphQL query to the metabase for all optical data. The field “locator” returns the URL of the optical dataset. A GET HTTPS request to the URL returns the optical dataset. In order to access datasets from IGSDB, you can register and login at https://igsdb-v2.herokuapp.com/ .

![screenshot_allOpticalData](https://github.com/user-attachments/assets/f96ef4ec-f415-4f49-a27f-c731b62c6fb2)

# Do you have any other question?

Please send us your questions as an "issue" with https://github.com/building-envelope-data/api/issues/new . We want to support you as good as we can.

# Acknowledgements

This work was funded by the German Federal Ministry for Economic Affairs and Climate Action under Grants 03ET1560A and 03EN1070A, based on a decision by the German Bundestag, by a Fraunhofer ICON Grant and by the Assistant Secretary for Energy Efficiency and Renewable Energy, Building Technologies Program, of the U.S. Department of Energy, under Contract No. DE-AC02-05CH11231.

<img src="https://user-images.githubusercontent.com/33456252/231481868-cd122279-287d-4928-9f24-71172c1fefda.png" width="250">
