---
title: "シングル サインオン On4 の要件 |Microsoft ドキュメント"
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
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15d7bdbf52869e5b13ae113716689bbb5b7ffec3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="4607a-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="4607a-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="4607a-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) ではシングル サインオン (SSO) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4607a-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="4607a-104">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO EMS などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="4607a-104">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="4607a-105">シングル サインオンを使用するために必要なものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4607a-105">To use Single Sign-On, you must have:</span></span>  
  
-   <span data-ttu-id="4607a-106">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4607a-106">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="4607a-107">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4607a-107">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="4607a-108">SSO をサポートするサーバーのシステム</span><span class="sxs-lookup"><span data-stu-id="4607a-108">A server system that supports SSO</span></span>  
  
 <span data-ttu-id="4607a-109">分離ホストは、信頼された認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4607a-109">The isolated host should be configured as authentication trusted</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="4607a-110">SSO を有効にするには</span><span class="sxs-lookup"><span data-stu-id="4607a-110">To enable SSO</span></span>  
  
1.  <span data-ttu-id="4607a-111">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="4607a-111">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="4607a-112">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4607a-112">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="4607a-113">関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。</span><span class="sxs-lookup"><span data-stu-id="4607a-113">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4607a-114">作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="4607a-114">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="4607a-115">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="4607a-115">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4607a-116">参照</span><span class="sxs-lookup"><span data-stu-id="4607a-116">See Also</span></span>  
 [<span data-ttu-id="4607a-117">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="4607a-117">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)