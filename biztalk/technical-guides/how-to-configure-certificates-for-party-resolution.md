---
title: パーティの解決用の証明書を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 153c8ccce1fafbe32c51b1c048fad4081f5b0b0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297722"
---
# <a name="how-to-configure-certificates-for-party-resolution"></a><span data-ttu-id="8e3b9-102">パーティの解決用の証明書を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8e3b9-102">How to Configure Certificates for Party Resolution</span></span>
<span data-ttu-id="8e3b9-103">BizTalk エクスプ ローラーを使用してパーティを構成するときに、そのデジタル署名を使用してパーティを解決できるように、パーティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8e3b9-103">When you use BizTalk Explorer to configure a party, you can configure the party so that the party is resolved by using its digital signature.</span></span> <span data-ttu-id="8e3b9-104">これにより、パーティを構成する場合と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がメッセージを受信メッセージの送信者を判断し、送信者の既知のパーティを解決するは、公開キー証明書を使用、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="8e3b9-104">If you configure the party this way, when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it will use the public key certificate to determine who sent the message, and to resolve the sender to a known party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e3b9-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="8e3b9-105">Prerequisites</span></span>  
 <span data-ttu-id="8e3b9-106">このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="8e3b9-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-party-resolution-to-use-a-certificate"></a><span data-ttu-id="8e3b9-107">証明書を使用するパーティの解決を構成するには</span><span class="sxs-lookup"><span data-stu-id="8e3b9-107">To configure party resolution to use a certificate</span></span>  
  
1.  <span data-ttu-id="8e3b9-108">開く、**パーティ プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8e3b9-108">Open the **Party Properties** dialog box.</span></span>  
  
2.  <span data-ttu-id="8e3b9-109">クリックして、**証明書** タブをクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="8e3b9-109">Click the **Certificate** tab, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="8e3b9-110">証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e3b9-110">Select a certificate.</span></span>  
  
4.  <span data-ttu-id="8e3b9-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3b9-111">Click **OK**.</span></span>