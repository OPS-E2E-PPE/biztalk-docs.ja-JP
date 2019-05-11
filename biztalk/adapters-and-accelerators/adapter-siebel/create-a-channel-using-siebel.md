---
title: Siebel を使用してチャネルを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- channel programming, creating a channel
- how to, create a channel
- creating a channel
ms.assetid: 5587cf51-7101-4035-b958-3fe070ba6252
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5efe7a5e20c2526bf944b18ee87d7afd4f88bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371817"
---
# <a name="create-a-channel-using-siebel"></a><span data-ttu-id="28a09-102">Siebel を使用してチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="28a09-102">Create a channel using Siebel</span></span>
<span data-ttu-id="28a09-103">このセクションでは、提供する XML メッセージを使用する Siebel と直接メッセージング チャネルを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="28a09-103">This section demonstrates how to create a channel for direct messaging with Siebel by providing and consuming XML messages.</span></span>  
  
```  
//create a channel factory, capable of sending a request to Siebel and receiving a reply (IRequestChannel)  
IChannelFactory<IRequestChannel> factory = binding.BuildChannelFactory<IRequestChannel>(new BindingParameterCollection());  
  
//open factory  
factory.Open();  
  
//obtain a channel from the factory by specifying the address you want to connect to  
IRequestChannel irc = factory.CreateChannel(address);  
  
//open the channel  
irc.Open();  
  
//perform operations  
…………  
…………  
…………  
  
//close the channel  
irc.Close();  
  
//close the factory  
factory.Close();  
```  
  
 <span data-ttu-id="28a09-104">チャネルを作成した後は、Siebel の操作を実行するのにそのチャネルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="28a09-104">Once you have created the channel, you can use that channel to perform operations on Siebel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a09-105">参照</span><span class="sxs-lookup"><span data-stu-id="28a09-105">See Also</span></span>  
 <span data-ttu-id="28a09-106">[WCF チャネル モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md) </span><span class="sxs-lookup"><span data-stu-id="28a09-106">[Develop Siebel Applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md) </span></span>  
 [<span data-ttu-id="28a09-107">WCF チャネル モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="28a09-107">Run Operations on Business Components with the Siebel adapter using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md)