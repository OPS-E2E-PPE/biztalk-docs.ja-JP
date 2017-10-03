---
title: "シングル サインオン On3 の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 005f095ae09b3018b9c8fe796520205103c7961a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="c9819-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="c9819-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="c9819-103">シングル サインオン (SSO) を使用するために必要なものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9819-103">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="c9819-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9819-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="c9819-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c9819-105">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="c9819-106">SSO をサポートするサーバーのシステム</span><span class="sxs-lookup"><span data-stu-id="c9819-106">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="c9819-107">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9819-107">The isolated host should be configured as Authentication Trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="c9819-108">SSO を有効にするには</span><span class="sxs-lookup"><span data-stu-id="c9819-108">To enable SSO</span></span>  
  
1.  <span data-ttu-id="c9819-109">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="c9819-109">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="c9819-110">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9819-110">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="c9819-111">詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications1.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9819-111">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9819-112">作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="c9819-112">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="c9819-113">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="c9819-113">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9819-114">参照</span><span class="sxs-lookup"><span data-stu-id="c9819-114">See Also</span></span>  
 [<span data-ttu-id="c9819-115">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9819-115">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)