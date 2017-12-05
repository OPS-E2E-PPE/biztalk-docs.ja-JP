---
title: "BizTalk Server の移行のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ddb6d9780a86183de5a09791de44adda5d57dab
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshooting-biztalk-server-migration"></a><span data-ttu-id="bfdf1-102">BizTalk Server の移行のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bfdf1-102">Troubleshooting BizTalk Server Migration</span></span>
<span data-ttu-id="bfdf1-103">このセクションでは、1 か所から BizTalk アプリケーションの移行中に発生する一般的な問題に関する情報の[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Server 2009 です。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-103">This section provides a centralized location for information about common problems encountered while migrating BizTalk applications from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="bfdf1-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bfdf1-104">Known Issues</span></span>  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a><span data-ttu-id="bfdf1-105">アップグレード中、カスタム アプリケーションが動作しない可能性がある</span><span class="sxs-lookup"><span data-stu-id="bfdf1-105">Custom applications might not work while upgrading</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="bfdf1-106">問題</span><span class="sxs-lookup"><span data-stu-id="bfdf1-106">Problem</span></span>  
 <span data-ttu-id="bfdf1-107">アップグレードするときに[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Server 2009 一部のカスタム アプリケーションは動作しません。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-107">While upgrading from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server, some custom applications might not work.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="bfdf1-108">原因</span><span class="sxs-lookup"><span data-stu-id="bfdf1-108">Cause</span></span>  
 <span data-ttu-id="bfdf1-109">BizTalk のマネージ コード コンポーネントはすべて、CLR 4.0 上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-109">All the BizTalk managed code components run on CLR 4.0.</span></span> <span data-ttu-id="bfdf1-110">これらのコンポーネントは [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] に対してコンパイルされるので、CLR 4.0 で実行するための構成ファイルが必要になります。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-110">As these components are compiled against [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)], they need a config file to run in CLR 4.0.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="bfdf1-111">解決方法</span><span class="sxs-lookup"><span data-stu-id="bfdf1-111">Solution</span></span>  
 <span data-ttu-id="bfdf1-112">この問題を解決するには、構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-112">To resolve this issue, update the config file.</span></span>  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfdf1-113">参照</span><span class="sxs-lookup"><span data-stu-id="bfdf1-113">See Also</span></span>  
 [<span data-ttu-id="bfdf1-114">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bfdf1-114">Troubleshooting</span></span>](../core/troubleshooting.md)