---
title: パーティの解決用の証明書を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 060101c1-14f3-4600-a18e-48a160d59bca
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad5a25799599c668011e9ef2e322a016f649b198
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253493"
---
# <a name="how-to-configure-certificates-for-party-resolution"></a><span data-ttu-id="5af53-102">パーティの解決用の証明書を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5af53-102">How to Configure Certificates for Party Resolution</span></span>
<span data-ttu-id="5af53-103">BizTalk エクスプ ローラーを使用してパーティを構成する場合は、デジタル署名を使用して、パーティが解決されるように、パーティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5af53-103">When you use BizTalk Explorer to configure a party, you can configure the party so that the party is resolved by using its digital signature.</span></span> <span data-ttu-id="5af53-104">この方法で、パーティを構成する場合と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がメッセージを受信メッセージの送信者を判断し、送信者に既知のパーティに解決には公開キー証明書を使用、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="5af53-104">If you configure the party this way, when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it will use the public key certificate to determine who sent the message, and to resolve the sender to a known party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5af53-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="5af53-105">Prerequisites</span></span>  
 <span data-ttu-id="5af53-106">このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="5af53-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a><span data-ttu-id="5af53-107">証明書を使用するパーティの解決を構成するには</span><span class="sxs-lookup"><span data-stu-id="5af53-107">To configure party resolution to use a certificate</span></span>  
  
1.  <span data-ttu-id="5af53-108">開く、**パーティ プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5af53-108">Open the **Party Properties** dialog box.</span></span>  
  
2.  <span data-ttu-id="5af53-109">をクリックして、**証明書**タブをクリックし、をクリックし、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="5af53-109">Click the **Certificate** tab, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="5af53-110">証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="5af53-110">Select a certificate.</span></span>  
  
4.  <span data-ttu-id="5af53-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5af53-111">Click **OK**.</span></span>