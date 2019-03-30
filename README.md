# nuc-openfaas
OpenFaaS funcs around NuCypher

-------------------------------------

# Links

## NuCypher  + CoinList hackathon 2019-03

* [NuCypher Hackathon on CoinList Build - CoinList](https://coinlist.co/build/nucypher?utm_campaign=newsletter_mailer-newsletter&utm_medium=email&utm_source=newsletter_mailer-newsletter&utm_term=nucypher_2-png)
* Intro: [nucypher/hackathon](https://github.com/nucypher/hackathon)
* Slides: [nucypher/slides](https://github.com/nucypher/slides/blob/ETHSingapore/slides.pdf)
* Chat: [Join the NuCypher Discord Server!](https://discordapp.com/invite/7rmXa3S)
* Submit Project: [https://coinlist.co/build/nucypher/projects/new](https://coinlist.co/build/nucypher/projects/new)
* Why NuCypher? 
    * NuCypher: Decentralized Key Management System (KMS)
    * It enables the private sharing of data across public consensus networks, without revealing data keys to intermediary entities.
    * [NuCypher on Twitter](https://twitter.com/NuCypher/status/1088545974614519808)
        * [img](https://pbs.twimg.com/media/DxtJcfFXcAArpdz.jpg:large)
    * Sample: [Finnegan’s Wake Demo](https://nucypher.readthedocs.io/en/latest/demos/finnegans_wake_demo.html)
        * Run demo: [nucypher/nucypher](https://github.com/nucypher/nucypher/tree/master/examples/finnegans_wake_demo)
        * Postman demo: [nucypher/nucypher](https://github.com/nucypher/nucypher/tree/master/examples/postman)
            * [Postman - Intro to collections](https://learning.getpostman.com/docs/postman/collections/intro_to_collections)
    * Setup Ursula network: [Ursula Configuration Guide](https://docs.nucypher.com/en/latest/guides/ursula_configuration_guide.html)
* [Hackathon Workshops](https://www.youtube.com/playlist?list=PLZYHxOo6wufiK_mK71CaudyWpJHCJW1Yk)
    * [(@NuCypher) | Twitter](https://twitter.com/NuCypher/media)
    * [MacLane Wilkison, CEO & Co-Founder, NuCypher «Building end-to-end encrypted, decentralized application»](https://www.youtube.com/watch?v=N76-HcQDuhQ&t=3714s)
    * [Justin Myles Holmes hosts a workshop with NuCypher during ETHDenver 2019](https://www.youtube.com/watch?v=om0tew-Z4gE)
    * [NuCypher + CoinList Hackathon: NuCypher Workshop](https://www.youtube.com/watch?v=NeqeyDVse_E)
    * [NuCypher + CoinList Hackathon: Arweave Workshop](https://www.youtube.com/watch?v=YKADcG7xJy4)
    * [NuCypher + CoinList Hackathon: Origin Workshop](https://www.youtube.com/watch?v=p5E5xMo8Lg4)
* So what to build?
    * pyUmbral wrapper
        * Python REST lib [encode/apistar](https://github.com/encode/apistar) around pyUmbral? or
        * OpenFaas for wrapping pyUmbral?
            * Pros: 
                * REST lib not needed
                * OpenFaas can be used in Dev, too: [OpenFaaS Cloud app](./OpenFaaSApp.md)
            * Cons:
                * Difficult to setup at cloud providers
    * In Local OpenShift host containers with
        * OpenFaas container for running pyUmbral
        * Frontend container (running phyton and pyUmbral ?) for 
            * Alice/Enrico to store encrypted data to StoreContainer
            * Alice to send access policy for Bob to Ursula network
            * Bob to fetch encrypted data from StoreContainer
            * Bob to request re-encryption in Ursula network
        * StoreContainer
        * Ursula container-node-1
        * Ursula container-node-2
    * Deploy containers to Azure or AWS

The End