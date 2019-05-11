---
title: 構成の X12 フォールバック アグリーメントのプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.x12fallback.properties
ms.assetid: fb780b54-e65c-4e85-852e-032e0af39654
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d43b8b2dc833f2c59ebd994aa6ba59bf6326994
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355024"
---
# <a name="configuring-x12-fallback-agreement-properties"></a><span data-ttu-id="7d26e-102">X12 フォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7d26e-102">Configuring X12 Fallback Agreement Properties</span></span>
<span data-ttu-id="7d26e-103">ここで説明するプロパティは、X12 でエンコードされたインターチェンジ (HIPAA を含みます) が交換されるたびに適用されます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、そのインターチェンジ (受信または送信) が解決されるアグリーメントを判断できません。</span><span class="sxs-lookup"><span data-stu-id="7d26e-103">The properties described in this section apply whenever X12-encoded interchanges (including HIPAA) are exchanged and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement that the interchanges (inbound or outbound) resolve to.</span></span> <span data-ttu-id="7d26e-104">ここでは、X12 と EDIFACT 両方のエンコード メッセージに共通する一般的なフォールバック設定についても説明します。</span><span class="sxs-lookup"><span data-stu-id="7d26e-104">This section also describes general fallback settings common to both X12 and EDIFACT encoded messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d26e-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7d26e-105">In This Section</span></span>  
  
-   [<span data-ttu-id="7d26e-106">X12 および EDIFACT でエンコードされたメッセージの共通フォールバック プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7d26e-106">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>](../core/configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages.md)  
  
-   [<span data-ttu-id="7d26e-107">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7d26e-107">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)  
  
-   [<span data-ttu-id="7d26e-108">トランザクション セットの設定の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7d26e-108">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d26e-109">参照</span><span class="sxs-lookup"><span data-stu-id="7d26e-109">See Also</span></span>  
 [<span data-ttu-id="7d26e-110">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7d26e-110">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)