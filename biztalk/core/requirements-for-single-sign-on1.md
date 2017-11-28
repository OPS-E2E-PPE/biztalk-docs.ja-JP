---
title: "シングル サインオンの要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 437bc9d744e20b14e21d0e9d2ebe33e7b2e8a62a
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="9e95b-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="9e95b-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="9e95b-103">シングル サインオン (SSO) を使用するには、以下のソフトウェアがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e95b-103">To use Single Sign-On (SSO), you must have the following software installed:</span></span>  
  
-   <span data-ttu-id="9e95b-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9e95b-104">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="9e95b-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9e95b-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="9e95b-106">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9e95b-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="9e95b-107">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="9e95b-107">A Server System that supports SSO</span></span>  
  
-   <span data-ttu-id="9e95b-108">分離ホストとして構成しなければならない**信頼されている認証**です。</span><span class="sxs-lookup"><span data-stu-id="9e95b-108">The isolated host should be configured as **Authentication Trusted**.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="9e95b-109">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e95b-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="9e95b-110">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="9e95b-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="9e95b-111">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e95b-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="9e95b-112">関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications4.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e95b-112">For information about creating an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications4.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e95b-113">作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="9e95b-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="9e95b-114">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="9e95b-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e95b-115">参照</span><span class="sxs-lookup"><span data-stu-id="9e95b-115">See Also</span></span>  
 [<span data-ttu-id="9e95b-116">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e95b-116">Using Single Sign-On</span></span>](../core/using-single-sign-on1.md)