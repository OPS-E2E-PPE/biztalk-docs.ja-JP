---
title: "シングル サインオン On2 の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling SSO
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c886792f36808152c4a27733544b09015c68f061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="3f0b9-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="3f0b9-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="3f0b9-103">シングル サインオン (SSO) を使用するのには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-103">To use Single Sign-On (SSO), you need:</span></span>  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="3f0b9-104">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3f0b9-104">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="3f0b9-105">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="3f0b9-105">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="3f0b9-106">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-106">The isolated host should be configured as authentication trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="3f0b9-107">SSO を有効にするには</span><span class="sxs-lookup"><span data-stu-id="3f0b9-107">To enable SSO</span></span>  
  
1.  <span data-ttu-id="3f0b9-108">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-108">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="3f0b9-109">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-109">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="3f0b9-110">関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications2.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-110">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f0b9-111">作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-111">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="3f0b9-112">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-112">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0b9-113">参照</span><span class="sxs-lookup"><span data-stu-id="3f0b9-113">See Also</span></span>  
 <span data-ttu-id="3f0b9-114">[SSO プロジェクトの実行](../core/running-sso-projects1.md) </span><span class="sxs-lookup"><span data-stu-id="3f0b9-114">[Running SSO Projects](../core/running-sso-projects1.md) </span></span>  
 [<span data-ttu-id="3f0b9-115">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f0b9-115">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)