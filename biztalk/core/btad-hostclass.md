---
title: BTAD_HostClass |Microsoft ドキュメント
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
ms.openlocfilehash: b561be31514d354f6079af4161123b365e017079
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="btadhostclass"></a><span data-ttu-id="3092e-102">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="3092e-102">BTAD_HostClass</span></span>
<span data-ttu-id="3092e-103">BTAD_HostClass は、処理が BizTalk 管理データベースとローカル コンピューターのどちらで実行されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="3092e-103">BTAD_HostClass indicates whether the operation is being performed on the BizTalk Management database or the local computer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3092e-104">解説</span><span class="sxs-lookup"><span data-stu-id="3092e-104">Remarks</span></span>  
 <span data-ttu-id="3092e-105">BTAD_HostClass で使用できる値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3092e-105">The following table describes the possible values for BTAD_HostClass.</span></span>  
  
|<span data-ttu-id="3092e-106">値</span><span class="sxs-lookup"><span data-stu-id="3092e-106">Value</span></span>|<span data-ttu-id="3092e-107">Description</span><span class="sxs-lookup"><span data-stu-id="3092e-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3092e-108">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="3092e-108">ConfigurationDb</span></span>|<span data-ttu-id="3092e-109">インポート処理が、グループの BizTalk 管理データベースで実行されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3092e-109">Specifies that the import operation is being performed on the BizTalk Management database for the group</span></span>|  
|<span data-ttu-id="3092e-110">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="3092e-110">BizTalkHostInstance</span></span>|<span data-ttu-id="3092e-111">インストールまたはアンインストール処理が、ローカル コンピューターで実行されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3092e-111">Specifies that the install or uninstall operation is being performed on the local computer</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3092e-112">参照</span><span class="sxs-lookup"><span data-stu-id="3092e-112">See Also</span></span>  
 <span data-ttu-id="3092e-113">[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3092e-113">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="3092e-114">環境変数が展開の状態を指定する方法</span><span class="sxs-lookup"><span data-stu-id="3092e-114">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)