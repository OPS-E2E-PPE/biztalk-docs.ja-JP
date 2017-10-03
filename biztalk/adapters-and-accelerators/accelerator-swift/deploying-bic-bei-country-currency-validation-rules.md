---
title: "BIC BEI 国通貨検証規則を展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f1786b37194db25f0e38db7491538857f3406b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a><span data-ttu-id="dad64-102">BIC、BEI、国/通貨検証規則を展開します。</span><span class="sxs-lookup"><span data-stu-id="dad64-102">Deploying BIC/BEI/Country/Currency Validation Rules</span></span>
<span data-ttu-id="dad64-103">**BIC、BEI、国/通貨の検証ルールを展開します。**</span><span class="sxs-lookup"><span data-stu-id="dad64-103">**To deploy the BIC/BEI/Country/Currency Validation rules:**</span></span>  
  
1.  <span data-ttu-id="dad64-104">% プログラム files%\Microsoft BizTalk Accelerator for、SWIFT\SDK\MX Messages\Base ポリシーで発行および個別に展開されているように汎用的なメッセージに固有ではない、必要であり、ポリシーの次のセットでは、ビジネス ルール エンジン展開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dad64-104">The following set of policies, %program files%\Microsoft BizTalk Accelerator for SWIFT\SDK\MX Messages\Base Policies, which are generic and not message-specific, need to be published and deployed separately using the Business Rule Engine Deployment Wizard.</span></span>  
  
    -   <span data-ttu-id="dad64-105">MX_BIC_Master_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="dad64-105">MX_BIC_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="dad64-106">MX_BIC_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="dad64-106">MX_BIC_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="dad64-107">MX_BEI_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="dad64-107">MX_BEI_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="dad64-108">MX_DBConnection_Master_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="dad64-108">MX_DBConnection_Master_Policy.xml</span></span>  
  
    -   <span data-ttu-id="dad64-109">MX_BICPlusIBAN_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="dad64-109">MX_BICPlusIBAN_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="dad64-110">MX_SEPA_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="dad64-110">MX_SEPA_Validation_Policy.xml</span></span>  
  
2.  <span data-ttu-id="dad64-111">これらのポリシーを展開する前に MX_DBConnection_Master_Policy.xml と MX_BIC_Master_Policy.xml 指定してください、データベース サーバー名とデータベース名、国/通貨の値が格納されています。</span><span class="sxs-lookup"><span data-stu-id="dad64-111">Before deploying these policies, MX_DBConnection_Master_Policy.xml and MX_BIC_Master_Policy.xml should have the database server name and database name where the Country/Currency values have been stored.</span></span>  
  
3.  <span data-ttu-id="dad64-112">マスターのポリシーが変更されている発行すべてビジネス ルール エンジン展開ウィザードを使用してポリシーします。</span><span class="sxs-lookup"><span data-stu-id="dad64-112">Once the master policies have been modified, publish all polices using the Business Rule Engine Deployment Wizard.</span></span> <span data-ttu-id="dad64-113">次のオプションを使用します。 ポリシー/ボキャブラリ ファイルをデータベースにインポートします。</span><span class="sxs-lookup"><span data-stu-id="dad64-113">Use the following option: Import the policy/vocabulary file to database.</span></span>  
  
4.  <span data-ttu-id="dad64-114">[プログラム]、[BizTalk サーバー] をクリックして\<バージョン >、[ビジネス ルール作成ツール] をクリックし、発行、6 つのポリシーします。</span><span class="sxs-lookup"><span data-stu-id="dad64-114">Click Programs, click BizTalk Server \<version>, click Business Rule Composer, and then deploy the six published polices.</span></span>