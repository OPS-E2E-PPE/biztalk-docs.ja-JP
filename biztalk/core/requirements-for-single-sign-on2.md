---
title: シングル サインオンの要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96a4101dc5380168db60e687ddc450f98f9192f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987315"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="c6c14-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="c6c14-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="c6c14-103">シングル サインオン (SSO) を使用するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c14-103">To use Single Sign-On (SSO), you need:</span></span>  
  
- <span data-ttu-id="c6c14-104">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c6c14-104">BizTalk Server</span></span>
  
- <span data-ttu-id="c6c14-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c6c14-105">Visual Studio</span></span>  
  
- <span data-ttu-id="c6c14-106">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c6c14-106">Enterprise Single Sign-On</span></span>  
  
- <span data-ttu-id="c6c14-107">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="c6c14-107">A Server System that supports SSO</span></span>  
  
  <span data-ttu-id="c6c14-108">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6c14-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="c6c14-109">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c6c14-109">Enable SSO</span></span>  
  
1. <span data-ttu-id="c6c14-110">**トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="c6c14-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2. <span data-ttu-id="c6c14-111">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6c14-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
   <span data-ttu-id="c6c14-112">関連アプリケーションを作成する方法については、[関連アプリケーションを作成する](../core/creating-affiliate-applications2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6c14-112">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6c14-113">作業が完了したら、SSO を使用してへの任意の Web 共有フォルダーに戻してください**を共有しない**します。</span><span class="sxs-lookup"><span data-stu-id="c6c14-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="c6c14-114">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="c6c14-114">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c14-115">参照</span><span class="sxs-lookup"><span data-stu-id="c6c14-115">See Also</span></span>  
 <span data-ttu-id="c6c14-116">[SSO プロジェクトの実行](../core/running-sso-projects1.md) </span><span class="sxs-lookup"><span data-stu-id="c6c14-116">[Running SSO Projects](../core/running-sso-projects1.md) </span></span>  
 [<span data-ttu-id="c6c14-117">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c6c14-117">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)