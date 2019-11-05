---
title: "Kava delegation guide for fundraiser participants"
description: "Step by step guide to stake KAVA tokens with P2P Validator"
date: 2019-11-05
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/B3tFJfK.jpg'
layout: Post
category:
  - kava
authors:
  - AlexBond
company:
 - p2p

---

*To participate in Kava economy you need to restore your fundraiser account using `kvcli` and delegate from there.*

Requirements:

* Go 1.13+
* Make
* Ubuntu 18.04 

**1) First you have to download Make and Go**

*-Download Make and other packets:*

 `sudo apt install build-essential`

*-Download Go:*

`wget https://dl.google.com/go/go1.13.1.linux-amd64.tar.gz`
`sudo tar -C /usr/local -xzf go1.13.1.linux-amd64.tar.gz`
`mkdir -p ~/go/{bin,src,pkg}`

For correct work of Go you will need to define environment variables

Execute following commands by rotation:

 `export PATH=$PATH:/usr/local/go/bin`
 `export GOPATH=$HOME/go`
 `export GOBIN=$GOPATH/bin`
 `export PATH=$PATH:$GOBIN`

For convenience add these strings to the current user profile. In Ubuntu it is: `~/.profile`. Execute `nano ~/.profile` and put strings from the previous step in the end of the file:

  `export PATH=$PATH:/usr/local/go/bin`
  `export GOPATH=$HOME/go`
  `export GOBIN=$GOPATH/bin`
  `export PATH=$PATH:$GOBIN`

![img](https://lh6.googleusercontent.com/z1xgb-QnqfZ13Q2xZqlRYHf2cCpfcj93ikbqdHxX0mdPTISTCv0sg5Ic6RgrEGD-hgPylKsVqUklRnJOIXwRl991czdeUhKRLGjXZt80U-5DFW5RJk3M4ADGmjEhXOxxjPHce8wr)

After that execute:  `source ~/.profile`

**2) Build Kava:**

Go to the folder `cd ~/go/src/`

Execute:

  `git clone https://github.com/kava-labs/kava`
  `cd kava`
  `git checkout v0.3.1
  `make install`

If everything went as it should in the folder `~/go/bin` appeared `- kvd` and `- kvcli` packets

**3) Delegate KAVA tokens**

*In the following instruction all commands sent from a network node in testnet and `chain id` and `validator address` parameters in screenshots differ from the mainnet values. The actual values for mainnet provided below.*

To make actions further you should have:

* Kava account

* Active node

Make sure that account exist and have positive balance:

 `kvcli keys list`

**![img](https://lh3.googleusercontent.com/UFKmCu6hJJlShYNA1w2BnlI9SSI6of8fCtXIgPji5rWvIuss4-bnipPB54pru8Po2RI5a11zmJlQuy4g-xQyfzmBjJbltw-iZiZM6chPW2xaf2VrlOnhKeHZmvmXTt4S9qaqPxDF)**

 `kvcli keys show <your_key_name>`

**![img](https://lh4.googleusercontent.com/B1jrhklOf23BO3q-5cR-XE0gPcU3yGEw9ar1Yn_ktqRh-jTtb_QvLmN5rIGF1qKud4MMltPNDi5wMo1zlbFC5zapipo6ZY75xDgoDYNL4ePKYXdmYcf6yLQxbUwEitEaYJQfhhlA)**

`kvcli query account <your_address> --chain-id kava-1` 

**![img](https://lh6.googleusercontent.com/WqrwmBzoibrVoV_QiJ5cFvTkPY42pX8ojLcqzhEF8IYWqfpnoMfB1pZKKQCwI2b00a7UyX9NGd0exclA0u2WhA382Y7EvUGNNfTsBjuedG3IBem9oDklhAG3n1j3Xcki97-SOm9N)**

 *For assistance with command parameters you can execute `kvcli tx staking delegate --help`*

![img](https://lh6.googleusercontent.com/nCHMstEHBgRP3DTPsGdxpy2dt7Oe4SEwTKfpR8iSIKu-ID0d80gDY1Z6cqcZyxenQHnaapaoIOXNawNyDKD3vAtrwvH8z5mm5ul27sdpLsqoYg0AFe_oad_KsAGvNV21LXNbh4R5)

*Important note*, delegation amount nominated in uKAVA. For instance, if you want to stake 100 KAVA you should enter 100000000 in the amount field.

*P2P Validator address:* **kavavaloper12g40q2parn5z9ewh5xpltmayv6y0q3zs6ddmdg**
*Chain ID:* **kava-1**

For delegation execute:

`kvcli tx staking delegate kavavaloper12g40q2parn5z9ewh5xpltmayv6y0q3zs6ddmdg <amount of KAVA you want to stake>ukava --from  --chain-id kava-1` 

Below is an example of the output you should get after successful delegation.

**![img](https://lh3.googleusercontent.com/gMbO0-AOXN9cvPQ2A6iPrndWd7aDGJxSsA0Z2s7swy_n2P4Q6zL7ICMNVZuNleCOQ6xyqfpfYULIYma5ijhdmGt3cd4YyDHLy-bGNiOxJE1gsmcLi45BuqHfpr8KPzuw3Lh1QqrF)**

If you have any questions or different operational system contact us at p2p.org or schedule a personal call with our development team to guide you through the whole process.

------

*If you have any questions feel free to contact us. We are always open for communication.*

------

**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake KAVA with us:** [ https://p2p.org/kava](https://p2p.org/kava)

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[https://t.me/kava_p2p](https://t.me/kava_p2p)