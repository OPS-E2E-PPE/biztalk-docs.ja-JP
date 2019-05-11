---
title: シングル サインオンの要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03d043ef526957cd4590edc2a5d74396c1225a8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395282"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="e1c49-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="e1c49-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="e1c49-103">シングル サインオン (SSO) を使用するには、が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1c49-103">To use Single Sign-On (SSO), you must have:</span></span>  
  
- <span data-ttu-id="e1c49-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e1c49-104">Microsoft BizTalk Server</span></span> 
  
- <span data-ttu-id="e1c49-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e1c49-105">Visual Studio</span></span>  
  
- <span data-ttu-id="e1c49-106">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e1c49-106">Enterprise Single Sign-On</span></span>  
  
- <span data-ttu-id="e1c49-107">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="e1c49-107">A Server System that supports SSO</span></span>  
  
  <span data-ttu-id="e1c49-108">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1c49-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="e1c49-109">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e1c49-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="e1c49-110">**トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="e1c49-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="e1c49-111">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c49-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="e1c49-112">関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications3.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1c49-112">For information about creating affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1c49-113">作業が完了したら、SSO を使用していずれかに戻してください**Web 共有**フォルダー**を共有しない**します。</span><span class="sxs-lookup"><span data-stu-id="e1c49-113">After performing work using SSO, remember to reset any **Web-Sharing** folder to **Do not share**.</span></span> <span data-ttu-id="e1c49-114">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="e1c49-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c49-115">参照</span><span class="sxs-lookup"><span data-stu-id="e1c49-115">See Also</span></span>  
 [<span data-ttu-id="e1c49-116">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="e1c49-116">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)