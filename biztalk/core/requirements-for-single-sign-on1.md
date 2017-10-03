---
title: "シングル サインオン On1 の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- SSO, requirements [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
- Single Sign-On, requirements [JD Edwards EnterpriseOne adapters]
- Single Sign-On, enabling [JD Edwards EnterpriseOne adapters]
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfab6d6cfea2ddef3b953d3fb3bb15900420fdcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="2a874-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="2a874-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="2a874-103">シングル サインオン (SSO) を使用するには、以下のソフトウェアがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a874-103">To use Single Sign-On (SSO), you must have the following software installed:</span></span>  
  
-   <span data-ttu-id="2a874-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a874-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="2a874-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2a874-105">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="2a874-106">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="2a874-106">A Server System that supports SSO</span></span>  
  
-   <span data-ttu-id="2a874-107">分離ホストとして構成しなければならない**信頼されている認証**です。</span><span class="sxs-lookup"><span data-stu-id="2a874-107">The isolated host should be configured as **Authentication Trusted**.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="2a874-108">SSO を有効にするには</span><span class="sxs-lookup"><span data-stu-id="2a874-108">To enable SSO</span></span>  
  
1.  <span data-ttu-id="2a874-109">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="2a874-109">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="2a874-110">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a874-110">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="2a874-111">関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications4.md)です。</span><span class="sxs-lookup"><span data-stu-id="2a874-111">For information about creating an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications4.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a874-112">作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="2a874-112">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="2a874-113">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="2a874-113">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a874-114">参照</span><span class="sxs-lookup"><span data-stu-id="2a874-114">See Also</span></span>  
 [<span data-ttu-id="2a874-115">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a874-115">Using Single Sign-On</span></span>](../core/using-single-sign-on1.md)