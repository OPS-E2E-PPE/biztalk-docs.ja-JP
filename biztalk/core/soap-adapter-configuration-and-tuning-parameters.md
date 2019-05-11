---
title: SOAP アダプターの構成およびチューニング パラメータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], tuning
- SOAP adapters, tuning
ms.assetid: 73c175aa-16b9-4620-b303-9092ae29af21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 170743f3bd352856fa5c26acabb71f9c9261f2ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314559"
---
# <a name="soap-adapter-configuration-and-tuning-parameters"></a><span data-ttu-id="595d4-102">SOAP アダプターの構成およびチューニング パラメーター</span><span class="sxs-lookup"><span data-stu-id="595d4-102">SOAP Adapter Configuration and Tuning Parameters</span></span>
<span data-ttu-id="595d4-103">SOAP アダプターは BizTalk Server のインストール ディレクトリのルートにある BTSNTSvc.exe.config ファイルにエントリを加えることによって、特定の移行先サーバーが表示されますが、同時接続数を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="595d4-103">You can configure the number of concurrent connections that the SOAP adapter opens for a particular destination server by making an entry in the BTSNTSvc.exe.config file that is located in the root BizTalk Server installation directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="595d4-104">このプロパティから同じ HTTP サーバーにメッセージを送信する場合、HTTP および SOAP の両方のアダプターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="595d4-104">This property will be applied to both HTTP and SOAP adapters if they send messages to the same destination HTTP server.</span></span> <span data-ttu-id="595d4-105">"Maxconnnection"プロパティの既定値は 2、すべての Uri の"maxconnection"プロパティを設定できる最大値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="595d4-105">The default value for the “maxconnnection” property is 2, the maximum value that can be set for the “maxconnection” property for all URIs is 20.</span></span>  
  
 <span data-ttu-id="595d4-106">"最大接続数" プロパティの構成例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="595d4-106">The following is an example of the configuration for the maximum connections property:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="595d4-107">参照</span><span class="sxs-lookup"><span data-stu-id="595d4-107">See Also</span></span>  
 <span data-ttu-id="595d4-108">[SOAP アダプターの構成](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="595d4-108">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="595d4-109">HTTP アダプターの構成およびチューニング パラメーター</span><span class="sxs-lookup"><span data-stu-id="595d4-109">HTTP Adapter Configuration and Tuning Parameters</span></span>](../core/http-adapter-configuration-and-tuning-parameters.md)