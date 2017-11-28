---
title: "シングル サインオンの要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98d5164fa194f9a02314b897b267d9873879a9c0
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="12228-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="12228-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="12228-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) ではシングル サインオン (SSO) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="12228-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="12228-104">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO EMS などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="12228-104">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="12228-105">シングル サインオンを使用するために必要なものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="12228-105">To use Single Sign-On, you must have:</span></span>  
  
-   <span data-ttu-id="12228-106">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="12228-106">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="12228-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12228-107">Visual Studio</span></span>  
  
-   <span data-ttu-id="12228-108">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="12228-108">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="12228-109">SSO をサポートするサーバーのシステム</span><span class="sxs-lookup"><span data-stu-id="12228-109">A server system that supports SSO</span></span>  
  
 <span data-ttu-id="12228-110">分離ホストは、信頼された認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12228-110">The isolated host should be configured as authentication trusted</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="12228-111">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="12228-111">Enable SSO</span></span>  
  
1.  <span data-ttu-id="12228-112">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="12228-112">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="12228-113">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="12228-113">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="12228-114">関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。</span><span class="sxs-lookup"><span data-stu-id="12228-114">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12228-115">作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="12228-115">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="12228-116">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="12228-116">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12228-117">参照</span><span class="sxs-lookup"><span data-stu-id="12228-117">See Also</span></span>  
 [<span data-ttu-id="12228-118">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="12228-118">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)