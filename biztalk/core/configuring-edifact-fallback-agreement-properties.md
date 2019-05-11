---
title: EDIFACT フォールバック アグリーメント プロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.edifactfallback.properties
ms.assetid: fee588db-9ae8-44be-8a8f-9be624dec825
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b304b0856c27525e1b72f2ceebebddae3631948
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391304"
---
# <a name="configuring-edifact-fallback-agreement-properties"></a><span data-ttu-id="5a334-102">EDIFACT フォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="5a334-102">Configuring EDIFACT Fallback Agreement Properties</span></span>
<span data-ttu-id="5a334-103">ここで説明するプロパティは、EDIFACT でエンコードされたインターチェンジが交換されるたびに適用されます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、そのインターチェンジ (受信または送信) が解決されるアグリーメントを判断できません。</span><span class="sxs-lookup"><span data-stu-id="5a334-103">The properties described in this section apply whenever EDIFACT-encoded interchanges are exchanged and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement that the interchanges (inbound or outbound) resolve to.</span></span> <span data-ttu-id="5a334-104">ここでは、X12 と EDIFACT 両方のエンコード メッセージに共通する一般的なフォールバック設定についても説明します。</span><span class="sxs-lookup"><span data-stu-id="5a334-104">This section also describes general fallback settings common to both X12 and EDIFACT encoded messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a334-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a334-105">In This Section</span></span>  
  
-   [<span data-ttu-id="5a334-106">X12 および EDIFACT でエンコードされたメッセージの共通フォールバック プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="5a334-106">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>](../core/configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages.md)  
  
-   [<span data-ttu-id="5a334-107">インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="5a334-107">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)  
  
-   [<span data-ttu-id="5a334-108">トランザクション セット設定の EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="5a334-108">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)  
  
## <a name="see-also"></a><span data-ttu-id="5a334-109">参照</span><span class="sxs-lookup"><span data-stu-id="5a334-109">See Also</span></span>  
 [<span data-ttu-id="5a334-110">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="5a334-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)