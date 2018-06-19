---
title: Siebel を使用してチャネルを作成 |Microsoft ドキュメント
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
ms.openlocfilehash: 87524160550cfe84c5e7e94efba1e44bff20c6ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221890"
---
# <a name="create-a-channel-using-siebel"></a><span data-ttu-id="56b38-102">Siebel を使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="56b38-102">Create a channel using Siebel</span></span>
<span data-ttu-id="56b38-103">このセクションでは、によって提供および XML メッセージを消費する Siebel による直接メッセージングのチャネルを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="56b38-103">This section demonstrates how to create a channel for direct messaging with Siebel by providing and consuming XML messages.</span></span>  
  
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
  
 <span data-ttu-id="56b38-104">チャネルを作成した後は、Siebel の操作を実行、そのチャネルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="56b38-104">Once you have created the channel, you can use that channel to perform operations on Siebel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b38-105">参照</span><span class="sxs-lookup"><span data-stu-id="56b38-105">See Also</span></span>  
 <span data-ttu-id="56b38-106">[WCF チャネル モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md) </span><span class="sxs-lookup"><span data-stu-id="56b38-106">[Develop Siebel Applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md) </span></span>  
 [<span data-ttu-id="56b38-107">WCF チャネル モデルを使用して、Siebel アダプターとビジネス コンポーネントでの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="56b38-107">Run Operations on Business Components with the Siebel adapter using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md)