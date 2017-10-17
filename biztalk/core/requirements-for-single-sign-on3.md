---
title: "シングル サインオンの要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61932b44364670515f02f89a1441a5d54030bc94
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="82bca-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="82bca-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="82bca-103">シングル サインオン (SSO) を使用するために必要なものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82bca-103">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="82bca-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="82bca-104">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="82bca-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82bca-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="82bca-106">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="82bca-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="82bca-107">SSO をサポートするサーバーのシステム</span><span class="sxs-lookup"><span data-stu-id="82bca-107">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="82bca-108">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bca-108">The isolated host should be configured as Authentication Trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="82bca-109">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82bca-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="82bca-110">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="82bca-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="82bca-111">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="82bca-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="82bca-112">詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications1.md)です。</span><span class="sxs-lookup"><span data-stu-id="82bca-112">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82bca-113">作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="82bca-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="82bca-114">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="82bca-114">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82bca-115">参照</span><span class="sxs-lookup"><span data-stu-id="82bca-115">See Also</span></span>  
 [<span data-ttu-id="82bca-116">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="82bca-116">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)