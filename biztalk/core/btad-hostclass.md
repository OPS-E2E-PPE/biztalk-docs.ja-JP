---
title: BTAD_HostClass | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_HostClass [environment variable]
ms.assetid: 068a19e9-2566-4c8e-a8b4-fd2fa614e8ed
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e5c0bc56c07f85b9965c31febb8c30f6ea1db57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357825"
---
# <a name="btadhostclass"></a><span data-ttu-id="5219a-102">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="5219a-102">BTAD_HostClass</span></span>
<span data-ttu-id="5219a-103">BTAD_HostClass は、処理が BizTalk 管理データベースとローカル コンピューターのどちらで実行されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="5219a-103">BTAD_HostClass indicates whether the operation is being performed on the BizTalk Management database or the local computer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5219a-104">コメント</span><span class="sxs-lookup"><span data-stu-id="5219a-104">Remarks</span></span>  
 <span data-ttu-id="5219a-105">BTAD_HostClass で使用できる値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="5219a-105">The following table describes the possible values for BTAD_HostClass.</span></span>  
  
|<span data-ttu-id="5219a-106">値</span><span class="sxs-lookup"><span data-stu-id="5219a-106">Value</span></span>|<span data-ttu-id="5219a-107">説明</span><span class="sxs-lookup"><span data-stu-id="5219a-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5219a-108">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="5219a-108">ConfigurationDb</span></span>|<span data-ttu-id="5219a-109">インポート処理が、グループの BizTalk 管理データベースで実行されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5219a-109">Specifies that the import operation is being performed on the BizTalk Management database for the group</span></span>|  
|<span data-ttu-id="5219a-110">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="5219a-110">BizTalkHostInstance</span></span>|<span data-ttu-id="5219a-111">インストールまたはアンインストール処理が、ローカル コンピューターで実行されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5219a-111">Specifies that the install or uninstall operation is being performed on the local computer</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5219a-112">参照</span><span class="sxs-lookup"><span data-stu-id="5219a-112">See Also</span></span>  
 <span data-ttu-id="5219a-113">[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="5219a-113">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="5219a-114">環境変数と展開状態の対応関係</span><span class="sxs-lookup"><span data-stu-id="5219a-114">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)