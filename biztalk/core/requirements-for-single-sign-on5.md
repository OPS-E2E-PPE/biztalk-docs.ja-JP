---
title: "シングル サインオン On5 の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], Single Sign-On
- SSO, requirements [JD Edwards OneWorld adapters]
- Single Sign-On, enabling [JD Edwards OneWorld adapters]
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b186eca2c24ef9c2731b66194a0543aba14e8bf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="8d191-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="8d191-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="8d191-103">シングル サインオン (SSO) を使用するのには、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d191-103">To use Single Sign-On (SSO), you must have:</span></span>  
  
-   <span data-ttu-id="8d191-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d191-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="8d191-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8d191-105">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="8d191-106">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="8d191-106">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="8d191-107">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d191-107">The isolated host should be configured as authentication trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="8d191-108">SSO を有効にするには</span><span class="sxs-lookup"><span data-stu-id="8d191-108">To enable SSO</span></span>  
  
1.  <span data-ttu-id="8d191-109">**トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="8d191-109">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="8d191-110">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d191-110">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="8d191-111">関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。</span><span class="sxs-lookup"><span data-stu-id="8d191-111">For information about creating affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8d191-112">作業を実行した後、SSO の使用に注意してくださいをリセットする**Web 共有**フォルダー**を共有しない**です。</span><span class="sxs-lookup"><span data-stu-id="8d191-112">After performing work using SSO, remember to reset any **Web-Sharing** folder to **Do not share**.</span></span> <span data-ttu-id="8d191-113">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="8d191-113">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d191-114">参照</span><span class="sxs-lookup"><span data-stu-id="8d191-114">See Also</span></span>  
 [<span data-ttu-id="8d191-115">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d191-115">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)