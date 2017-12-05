---
title: "手順 3: 編集 Partner Interface Process |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b6300c12e7bc28de0dc81af9eae23699338ed3d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-edit-the-partner-interface-process"></a><span data-ttu-id="a9be2-102">手順 3: Partner Interface Process を編集します。</span><span class="sxs-lookup"><span data-stu-id="a9be2-102">Step 3: Edit the Partner Interface Process</span></span>
<span data-ttu-id="a9be2-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® インターネット インフォメーション サービス (IIS) に SSL (Secure Sockets Layer) 証明書が構成されていない場合に、PIP (Partner Interface Process) 構成設定を編集してセキュリティで保護されたトランスポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a9be2-103">In this step, you edit the Partner Interface Process (PIP) configuration settings to disable secure transport if you do not have a Secure Sockets Layer (SSL) certificate configured in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Internet Information Services (IIS).</span></span> <span data-ttu-id="a9be2-104">ループバック シナリオでは着信メッセージと送信メッセージの署名はサポートされていないため、チュートリアルを続行するには既定の設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9be2-104">Because the loopback scenario does not support signing for both incoming and outgoing messages, you must change the default settings to continue with the tutorial.</span></span> <span data-ttu-id="a9be2-105">STD_0C1_R01.02 PIP を変更します。</span><span class="sxs-lookup"><span data-stu-id="a9be2-105">You modify the STD_0C1_R01.02 PIP.</span></span>  
  
### <a name="to-edit-the-std0c1r0102-pip"></a><span data-ttu-id="a9be2-106">STD_0C1_R01.02 PIP を編集するには</span><span class="sxs-lookup"><span data-stu-id="a9be2-106">To edit the STD_0C1_R01.02 PIP</span></span>  
  
1.  <span data-ttu-id="a9be2-107"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**プロセス構成設定**を右クリックして**STD_0C1_R01.02**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="a9be2-107">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand **BizTalk \<version\> Accelerator for RosettaNet**, click **Process Configuration Settings**, right-click **STD_0C1_R01.02**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a9be2-108">STD_0C1_R01.02Properties ダイアログ ボックスで、**アクティビティ** タブで、設定、**はセキュリティで保護されたトランスポートに必要な**オプションを`False`です。</span><span class="sxs-lookup"><span data-stu-id="a9be2-108">In the STD_0C1_R01.02Properties dialog box, on the **Activity** tab, set the **Is Secure Transport Required** option to `False`.</span></span> <span data-ttu-id="a9be2-109">この手順は、IIS Web サーバーに SSL 証明書がない場合にのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="a9be2-109">Perform this step only if you do not have a SSL certificate on your IIS Web server.</span></span>  
  
3.  <span data-ttu-id="a9be2-110">設定、**否認不可のために必要な**に`False`設定、**承認が必要**に`False`設定、**発信元とコンテンツの否認**に`False`、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a9be2-110">Set the **Non-Repudiation Required** to `False`, set **Is Authorization Required** to `False`, set **Non-Repudiation of Origin and Content** to `False`, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a9be2-111">これによって、否認不可と、メッセージに署名するための証明書の使用が無効になります。</span><span class="sxs-lookup"><span data-stu-id="a9be2-111">This disables non-repudiation and the use of certificates for signing messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9be2-112">参照</span><span class="sxs-lookup"><span data-stu-id="a9be2-112">See Also</span></span>  
 <span data-ttu-id="a9be2-113">[手順 4: 取引先アグリーメントを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="a9be2-113">[Step 4: Create a Trade Agreement](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md) </span></span>  
 [<span data-ttu-id="a9be2-114">承認プロパティと否認不可プロパティ</span><span class="sxs-lookup"><span data-stu-id="a9be2-114">Authorization and Non-Repudiation Properties</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)