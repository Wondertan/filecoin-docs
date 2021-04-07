---
title: Store and retrieve
description: This tutorial covers how to store data using the Filecoin network, and how to get that data back again. While there are other methods to store and retrieve data using Filecoin, this is the recommended path. 
---

# Set up

<!-- TODO: Explain all the steps we're going to do in this section. -->

## Get access to a Lotus full-node

A Lotus full-node is a computer running the `lotus daemon`. Full-nodes are special because they have complete access to the Filecoin blockchain. The computer specifications required to run a Lotus full-node are fairly high, and might be out of reach for most end-user laptops and PCs. 

For this tutorial, we're going to be using a Lotus full-node provided by Protocol Labs. This node, called `api.chain.love` is only for practice sessions like this tutorial, and should not be relied upon for any production purposes.

## Create a Lotus lite-node

### Dependencies

To install a Lotus lite-node on your computer you must have the tools required to _build_ a Lotus binary from the GitHub repository.

1. Open a terminal window.
1. Clone the [Lotus GitHub repository](https://github.com/filecoin-project/lotus) and create the executable, but do not run anything yet:

    ```shell
    git clone https://github.com/filecoin-project/lotus
    cd lotus
    make clean all
    sudo make install
    ```

1. Copy this command and enter your information:

    ```shell
    FULLNODE_API_INFO=<API_TOKEN>:/ip4/<YOUR_FULL_NODE_IP_ADDRESS>/tcp/1234 lotus daemon --lite
    ```

    Replace `<API_TOKEN>` with your API token, if you have one. Replace `<YOUR_FULL_NODE_IP_ADDRESS>` with the IP address of your Lotus full-node:

    ```shell
    FULLNODE_API_INFO=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBbGxvdyI6WyJyZWFkIiwid3JpdGUiXX0.FfTKDJEy7yuSMDNXIsF292rRKNe6F8hWodX2r9g1T_8:/ip4/134.122.35.130/tcp/1234 lotus daemon --lite
    ```

    The Lotus daemon will continue to run. Further commands must be ran from a seperate terminal window.

## Get a FIL address

1. Create an address using the `wallet new` command:

    ```shell
    lotus wallet new 

    > f1fwavjcfb32nxbczmh3kgdxhbffqjfsfby2otloi
    ```

    Lotus outputs your public address. Public addresses always start with `f1`.

1. Make a note of this address. We'll use it in an uncoming section.

## Sign up to Filecoin+

Filecoin Plus is a layer of social trust on top of the Filecoin network to help incentivize the storage of real data. Essentially, all Filecoin+ users who want to upload something to the Filecoin network can become a _verfied client_ by signing up to Filecoin+ using their GitHub account. All _verified clients_ get an allowance of 8GB per month to upload their data to the Filecoin network! 

1. Go to [plus.fil.org](https://plus.fil.org).
1. Under **Clients**, click **Proceed**.
1. Under **Get verified**, click **Get Verified**.
1. Click **Automatic Verification**.
1. In the `Request` field, enter the address you got in the previous section.

<!-- TODO: Get someone to follow this workflow and grab screenshots. --> 

## Next steps

Now that we've got all the set up out of the way, we can move onto storing data with the Filecoin network. 
