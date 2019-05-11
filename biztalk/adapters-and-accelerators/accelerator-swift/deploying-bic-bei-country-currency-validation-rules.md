---
title: BIC BEI 国通貨の検証ルールの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5526f96b9f60a53bb86b2aed1fc70352f71b57f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378333"
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a><span data-ttu-id="be022-102">BIC BEI/国/通貨の検証規則を展開します。</span><span class="sxs-lookup"><span data-stu-id="be022-102">Deploying BIC/BEI/Country/Currency Validation Rules</span></span>
<span data-ttu-id="be022-103">**BIC BEI/国/通貨の検証ルールを展開します。**</span><span class="sxs-lookup"><span data-stu-id="be022-103">**To deploy the BIC/BEI/Country/Currency Validation rules:**</span></span>  
  
1.  <span data-ttu-id="be022-104">次の一連のポリシー、% プログラム files%\Microsoft BizTalk Accelerator for 発行され、個別に展開されているジェネリックとないメッセージの特定、必要である SWIFT\SDK\MX Messages\Base ポリシーでは、ビジネス ルール エンジン展開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="be022-104">The following set of policies, %program files%\Microsoft BizTalk Accelerator for SWIFT\SDK\MX Messages\Base Policies, which are generic and not message-specific, need to be published and deployed separately using the Business Rule Engine Deployment Wizard.</span></span>  
  
    -   <span data-ttu-id="be022-105">MX_BIC_Master_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="be022-105">MX_BIC_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="be022-106">MX_BIC_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="be022-106">MX_BIC_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="be022-107">MX_BEI_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="be022-107">MX_BEI_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="be022-108">MX_DBConnection_Master_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="be022-108">MX_DBConnection_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="be022-109">MX_BICPlusIBAN_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="be022-109">MX_BICPlusIBAN_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="be022-110">MX_SEPA_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="be022-110">MX_SEPA_Validation_Policy.xml</span></span>  
  
2.  <span data-ttu-id="be022-111">これらのポリシーを展開する前に MX_DBConnection_Master_Policy.xml と MX_BIC_Master_Policy.xml 必要があります、データベース サーバー名とデータベース名、国/通貨の値が格納されています。</span><span class="sxs-lookup"><span data-stu-id="be022-111">Before deploying these policies, MX_DBConnection_Master_Policy.xml and MX_BIC_Master_Policy.xml should have the database server name and database name where the Country/Currency values have been stored.</span></span>  
  
3.  <span data-ttu-id="be022-112">すべて発行マスタ ポリシーが変更されていると、ビジネス ルール エンジン展開ウィザードを使用してポリシーします。</span><span class="sxs-lookup"><span data-stu-id="be022-112">Once the master policies have been modified, publish all polices using the Business Rule Engine Deployment Wizard.</span></span> <span data-ttu-id="be022-113">次のオプションを使用します。ポリシー/ボキャブラリ ファイルをデータベースにインポートします。</span><span class="sxs-lookup"><span data-stu-id="be022-113">Use the following option: Import the policy/vocabulary file to database.</span></span>  
  
4.  <span data-ttu-id="be022-114">[プログラム]、[BizTalk サーバー] をクリックして\<バージョン\>をビジネス ルール作成ツールをクリックし、発行、6 つを展開し、ポリシーします。</span><span class="sxs-lookup"><span data-stu-id="be022-114">Click Programs, click BizTalk Server \<version\>, click Business Rule Composer, and then deploy the six published polices.</span></span>