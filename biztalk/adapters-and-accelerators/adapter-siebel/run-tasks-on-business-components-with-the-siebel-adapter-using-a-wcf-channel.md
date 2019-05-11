---
title: WCF チャネル モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, perform operations using the channel
- performing operations, using the channel
ms.assetid: bae74013-38fa-413c-ba91-4e4ba096339e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e1399e9da080f09d4426e6e8ab0091ff60a7f85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370960"
---
# <a name="run-operations-on-business-components-with-the-siebel-adapter-using-the-wcf-channel-model"></a><span data-ttu-id="3b019-102">WCF チャネル モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b019-102">Run Operations on Business Components with the Siebel adapter using the WCF Channel Model</span></span>
<span data-ttu-id="3b019-103">このセクションで作成されたチャネルを使用して Siebel での操作を実行する方法を示します[Siebel を使用してチャネルを作成](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b019-103">This section demonstrates how to perform operations on Siebel using the channel created in [Create a Channel using Siebel](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md).</span></span>  
  
```  
// create binding  
SiebelBinding binding = new SiebelBinding();  
  
//set up an endpoint address  
EndpointAddress address = new EndpointAddress("siebel://Username=myuser;Password=mypass@mysiebelserver:1234?SiebelObjectManager=SSEObjMgr&SiebelEnterpriseServer=ent771&Language=enu");  
  
//create request channel factory  
IChannelFactory<IRequestChannel> factory = binding.BuildChannelFactory<IRequestChannel>(new BindingParameterCollection());  
  
//open factory  
factory.Open();  
  
//create request channel using endpoint  
IRequestChannel channel = factory.CreateChannel(address);  
  
//open the channel  
channel.Open();  
  
// send request message and receive reply  
System.Xml.XmlReader readerIn = System.Xml.XmlReader.Create(inputXml);  
System.ServiceModel.Channels.Message messageIn = System.ServiceModel.Channels.Message.CreateMessage(MessageVersion.Default,action,readerIn);  
System.ServiceModel.Channels.Message messageOut = channel.Request(messageIn);  
  
// get response XML from SOAP message  
System.Xml.XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
  
// save output file  
XmlDocument doc = new XmlDocument();  
doc.Load(readerOut);  
doc.Save(outputXml);  
Console.WriteLine("XML written out to {0}", outputXml);  
  
// close the channel and the factory  
channel.Close();  
factory.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b019-104">参照</span><span class="sxs-lookup"><span data-stu-id="3b019-104">See Also</span></span>  
 <span data-ttu-id="3b019-105">[WCF チャネル モデルを使用して Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md) </span><span class="sxs-lookup"><span data-stu-id="3b019-105">[Develop Siebel Applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md) </span></span>  
 [<span data-ttu-id="3b019-106">WCF サービス モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b019-106">Run Operations on Business Components with the Siebel adapter Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)