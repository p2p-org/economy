---
title: "Kusama network delegation guide"
description: "Step by step explanation of KSM delegation procedure"
date: 2019-09-23
thumbnail: 'http://url-to-thumbnail.jpg'
heroImage: 'https://imgur.com/jpbF7jU.jpg'
layout: Post
category:
  - kusama
authors:
  - AlexBond
company:
 - p2p

---

*If you participated in a Polkadot fundraiser and received your DOT indicator tokens you can claim KSM with your original Ethereum address.* 

[TOC]

# Create an account on Kusama network

First, you need to create a Kusama account. Visit [Polkadot UI](https://polkadot.js.org/apps/#/accounts), go to `Settings` tab and select `address prefix`.



![img](https://lh6.googleusercontent.com/yOXRvelBb7P4Trlvucw7RWRKkbUBBwBDhFoYYAkciquAyce-o-kyay1iqNdTWM68dXpjqUVKN0HhuiR8xcts8YMh9IIN6yCUak13wdGXCvF77Aq-2rane3k1A3E4rYE0sKky3bDg)



In a dropdown menu select Kusama (canary) and click `Save`.



![img](https://lh5.googleusercontent.com/Hz6d5vO3ztSMgIAqLkEMUavT547BRT4hCpb3B2SZuDd-bZjGkhGGt4ObrjRLND1gn2jHsOzmbo-jGLC89elbtQ5PGx0FAJ9GyZHyutvxCxTMr9QwZ1KFzoubUfjZRzBaSh-4ezcA)



Go to `Account` tab and press `Add account` button



![img](https://lh6.googleusercontent.com/Ayq2IcXdwBppb0p8yUxgOpMVcDgae-mpLUvRfeaGKPHN4tK-0D-hn75ZUUA9rt2Ej6reRxNbcAQnmkL5qkJHXn6kdCrmEVSoogVIlVYIzVcu-NElXEosOasQMDZ3cZLPoHLbSRDl)



Complete all the required fields and save all information in a secure place. For future ease add in the name of the account “stash” to identify it easily in the future or add a tag after creation. You will be able to download and store your encrypted keystore locally. 



![img](https://lh6.googleusercontent.com/CfHs8QHJuwfSuMXPzGg03NS1nRj2imojhn8osiGpLZq1D5pfsJePwhwxIWAMRkCI4ITrMOi4zJV7Ow0G7_EO_MUdRkj1fQH28HBl3NgNd_x9_p3tATrhrA473IUVHt0LjrekAK7V)



Press `Save` and backup your account



![img](https://lh3.googleusercontent.com/M8ToaoPn_OEEfY6ERmsmTJoaRhpmKolqRGzkLISTNWwMI19DAzJQ-0FhJQdXd-dFzheHmStoBdXubnFrJh7XPjEhdBpFkY7GAdPhL5IRVkBUjUWYQ3ltlRo1T75RE-jpzKX1GjZe)



For secure staking you will need to have at least two accounts:

**Stash** - the primary account that holds the funds. The funds can be kept in a cold wallet and all bonded KSM are locked. After unbonding, users must wait  for a time before they can access the locked funds. 

**Controller** - a separate account to control and perform commands for stash account, like changing nominations, starting or stopping nominating and so on. It needs to have sufficient funds  in KSM to send transactions when actions are taken.

Now you have created one account that initially will perform both functions. It will appear in your `Accounts` tab. After enablement of transactions, it is recommended to create a separate account, send 1 KSM to it and use it as a controller.

# Claim your KSM

After account registration you need to claim your KSM. Go to the [claim app](https://polkadot.js.org/apps/#/claims) on Polkadot UI,  select your account and press `Continue`.



![img](https://lh4.googleusercontent.com/wqRrPNre1Kyo50JLy9E7VKC2HfldgIn9A8OzVvjC7r8tK-npy9aioDTAMpD_1-ZHsJKCECegT5yqJf0HD55eBIkrtGq2MOec92DnGhk956J3ry2M-tG9b8PvrkV04myg2BLhp-5k)

To connect Kusama address with Ethereum fundraiser address you will need to sign the message with the ETH address that has DOT indicator tokens and paste the transaction signature in the  empty box below.



![img](https://lh5.googleusercontent.com/5hdkI1-FgPdqT26lWuVR1xJjPXz5uKxaKhT-Nps2Ya6L6fZ3VXiqv1Sx0HIu_4nclqWdTdlsv4McAlqlzmoYlsoZwLeTvsEnPu0myCc6Crfvgx4xlqCNlXMZeKHNeCb1hecofUoI)



To sign a transaction you can use MyCrypto (MC) or MyEtherWallet (MEW). For increased security, you can run one of the preferred applications on your local computer. Make sure you have downloaded the latest version for your operating system.

In MC go to `Sign & Verify Message`, in MEW go to `Message` tab. Copy text from the dotted box in the Polkadot claim app you used at the start and paste it into the empty message box in the MC or MEW and click `Sign`.

After that you will get an output. Copy and paste it into the empty box in the Polkadot claim app and press `Confirm claim`.



![img](https://lh6.googleusercontent.com/_ehoutURX8uG_6jkS8UQAHorpx717MV444wm-Aj6-gYrizW_WrrdI7gxvSz4-E383Dfq-vRJU_J2LvIgo9wv9nYi0lV0jvJ0uE3Z6YO2vgE-cg5OIwqnTIKjkcMRgYJ2XP4PQLg-)



If you have a valid claim you will see a green box. This means that you are able to take part in staking and governance. Token transfers are prohibited at the moment.

# Delegate your KSM



**a)** First you need to bond your KSM that are in the stash account. 

Visit the[ Polkadot UI](https://polkadot.js.org/apps) and select `Staking` tab.



![img](https://lh5.googleusercontent.com/IcZLpaUOtlqde_-PI-EfymXNWKI4q3hSsgvbzFiP60K00rp52F1Xl0w8C2koYzZ4yvD5lPCSv_FnuGIbBgVqU_NoBAuWl_4QDQ2hVT1PWirhqkcsVTUYlgI8J0-tQIGPH5RwzvF2)



Then choose `Account actions` tab at the top of the screen



![img](https://lh5.googleusercontent.com/hBXVGhnDzUawd78lb3mTPcnEvRaO8f4dSK13EKE3Sor29bD52WiE2dvUFq06kIJLcA2U9a558-iEJUo-ptNcWX1u2i2wl5p0mJR_dX4HiLfAwJqiNdPescm_Szeab6s7FyG93fRX)



Press `New stake` button



![img](https://lh3.googleusercontent.com/f4xsl16QMerLAZrpn4DZtoRijg6tJoAsREJ74cMDuoMFcaNBAOXY3JRdTajNG9uS_wCEm_Wn_vAIkGk22Av6xBMs76kgmbl-OeZQMXNsI4CL_QYzIzPRTxrSHukLhcT-Hn-WAOS7)



In the modal window choose your stash account and a controller account (in our case they are the same and their names and addresses will match). Put the number of KSM you are willing to bond. 

**This amount should be less than the total amount in your stash** to pay fees or set a separate controller account for your stash account in future. 



![img](https://lh5.googleusercontent.com/YTSIScc1l3YwzXtO5vcfDUtJtmAx58S6i7_Fo7SIYtizdAKT0144a8r-YV-MPwabgsaeO6oy3ttgZ5cIZobScIU_3SVqT8gO1ofr-eWOpGoeSG33UZBvyVPWMv9QiJJ6Egxv6sO9)



**b)** After your KSM are bonded you will be able to nominate up to 16 validators. Bonded tokens will be automatically delegated to chosen validators in a proportion that will be defined by the algorithm. If you want to delegate a specific number of tokens to a particular validator you have to select only one validator for your stash account. The number of tokens bonded in this stash account will be delegated to this validator. 

Go to `Staking overview` tab. In the left-hand column are the initial Proof-of-Authority validators that do not accept nominations. To nominate P2P Validator find us in the right-hand column.

![img](https://lh3.googleusercontent.com/ACdyDPFsxUJh7Z6Ob4savNVjJ0SgyFO_kWrTQEf6ft2dLuGs-i-4nXX0DTIpMnQev54BhNLKvxgX8UonrEt3nX09llqASAxuQ9h8hjB2w8FRVXfnxfEHMFBbWdDH4uoCKepII9V6)



**Copy our address:** 

`EUwcW86EFGDoDfUP2UJYuBwhCWC7cW9SdFH9cPh6UPBvBHj`



![img](https://lh3.googleusercontent.com/LmYBUjTJyX9Bim841K847QHMPjTptrsKYlKZodrSm79gBiNXj6lM1aO_CvT9-dtzHDgqc1SL95Q8GKm_CmTqvNrHulJODosRjbqYdaJMq9ZF7kvlpb6feqK9U9MYho90NVFAuqQA)



After that scroll up to `Account Actions` tab that is above the `Staking` tab and you will see your bonded account. 

Press the `Nominate` button and paste the copied address in the blank field. 

Sign and submit the transaction. 

------

*Hooray, now you can  officially call yourself a nominator and are fully prepared to earn rewards immediately after the launch of public network.*

------

**P2P Validator** offers high-quality staking facilities and provides up to date information for educational purposes. Stay tuned for updates and new blog posts.

**Web:**[ https://p2p.org](https://p2p.org)

**Stake KSM with us:** https://p2p.org/kusama

**Twitter:**[ @p2pvalidator](https://twitter.com/p2pvalidator)

**Telegram:**[ https://t.me/kusama_p2pvalidator](https://t.me/kusama_p2pvalidator)