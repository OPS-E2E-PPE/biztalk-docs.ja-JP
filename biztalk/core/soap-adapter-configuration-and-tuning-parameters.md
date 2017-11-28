---
title: "SOAP アダプターの構成およびチューニング パラメータ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], tuning
- SOAP adapters, tuning
ms.assetid: 73c175aa-16b9-4620-b303-9092ae29af21
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be6a71938876ad932a58d369abe40d7c8b073f72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="1e47a-102">SOAP アダプタの構成およびチューニング パラメータ</span><span class="sxs-lookup"><span data-stu-id="1e47a-102">SOAP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="1e47a-103">BizTalk Server をインストールしたルート ディレクトリに存在する BTSNTSvc.exe.config ファイルにエントリを作成することで、SOAP アダプタから特定の接続先サーバーへの同時接続の数を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1e47a-103">You can configure the number of concurrent connections that the SOAP adapter opens for a particular destination server by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e47a-104">このプロパティは、HTTP アダプタと SOAP アダプタから同じ HTTP サーバーにメッセージを送信する場合に、両方のアダプタに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1e47a-104">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="1e47a-105">"Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="1e47a-105">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="1e47a-106">"最大接続数" プロパティの構成例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1e47a-106">The following is an example of the configuration for the maximum connections property:</span></span>  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e47a-107">参照</span><span class="sxs-lookup"><span data-stu-id="1e47a-107">See Also</span></span>  
 <span data-ttu-id="1e47a-108">[SOAP アダプターの構成](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1e47a-108">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="1e47a-109">HTTP アダプタの構成およびチューニング パラメータ</span><span class="sxs-lookup"><span data-stu-id="1e47a-109">HTTP Adapter Configuration and Tuning Parameters</span></span>](../core/http-adapter-configuration-and-tuning-parameters.md)