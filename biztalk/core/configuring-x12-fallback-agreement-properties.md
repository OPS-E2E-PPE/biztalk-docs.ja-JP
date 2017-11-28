---
title: "設定の X12 フォールバック アグリーメント プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.x12fallback.properties
ms.assetid: fb780b54-e65c-4e85-852e-032e0af39654
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83b5f98b68cd3576e36293173acd6757e815b77e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-x12-fallback-agreement-properties"></a><span data-ttu-id="a9a46-102">X12 フォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="a9a46-102">Configuring X12 Fallback Agreement Properties</span></span>
<span data-ttu-id="a9a46-103">ここで説明するプロパティは、X12 でエンコードされたインターチェンジ (HIPAA を含みます) が交換されるたびに適用されます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、そのインターチェンジ (受信または送信) が解決されるアグリーメントを判断できません。</span><span class="sxs-lookup"><span data-stu-id="a9a46-103">The properties described in this section apply whenever X12-encoded interchanges (including HIPAA) are exchanged and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement that the interchanges (inbound or outbound) resolve to.</span></span> <span data-ttu-id="a9a46-104">ここでは、X12 と EDIFACT 両方のエンコード メッセージに共通する一般的なフォールバック設定についても説明します。</span><span class="sxs-lookup"><span data-stu-id="a9a46-104">This section also describes general fallback settings common to both X12 and EDIFACT encoded messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9a46-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a9a46-105">In This Section</span></span>  
  
-   [<span data-ttu-id="a9a46-106">エンコードされたメッセージの共通フォールバック プロパティの X12 および EDIFACT の構成</span><span class="sxs-lookup"><span data-stu-id="a9a46-106">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>](../core/configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages.md)  
  
-   [<span data-ttu-id="a9a46-107">設定の X12 インターチェンジ処理のためのフォールバック アグリーメント プロパティ</span><span class="sxs-lookup"><span data-stu-id="a9a46-107">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)  
  
-   [<span data-ttu-id="a9a46-108">設定の X12 フォールバック アグリーメントのプロパティをトランザクション セットの設定</span><span class="sxs-lookup"><span data-stu-id="a9a46-108">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9a46-109">参照</span><span class="sxs-lookup"><span data-stu-id="a9a46-109">See Also</span></span>  
 [<span data-ttu-id="a9a46-110">グローバルまたはフォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="a9a46-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)