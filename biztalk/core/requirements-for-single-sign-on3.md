---
title: TIBCO Rendevous アダプターの SSO の要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61b456def74ee76d887fa42149ee95b9ca3cbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013739"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="8d225-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="8d225-102">Requirements for Single Sign-On</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d225-103">前提条件</span><span class="sxs-lookup"><span data-stu-id="8d225-103">Prerequisites</span></span>
<span data-ttu-id="8d225-104">シングル サインオン (SSO) を使用するために必要なものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d225-104">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="8d225-105">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8d225-105">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="8d225-106">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8d225-106">Visual Studio</span></span>  
  
-   <span data-ttu-id="8d225-107">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8d225-107">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="8d225-108">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="8d225-108">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="8d225-109">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d225-109">The isolated host should be configured as Authentication Trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="8d225-110">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8d225-110">Enable SSO</span></span>  
  
1. <span data-ttu-id="8d225-111">**トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="8d225-111">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2. <span data-ttu-id="8d225-112">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d225-112">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
   <span data-ttu-id="8d225-113">詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications1.md)します。</span><span class="sxs-lookup"><span data-stu-id="8d225-113">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d225-114">作業が完了したら、SSO を使用してへの任意の Web 共有フォルダーに戻してください**を共有しない**します。</span><span class="sxs-lookup"><span data-stu-id="8d225-114">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="8d225-115">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="8d225-115">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d225-116">参照</span><span class="sxs-lookup"><span data-stu-id="8d225-116">See Also</span></span>  
[<span data-ttu-id="8d225-117">Security</span><span class="sxs-lookup"><span data-stu-id="8d225-117">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)