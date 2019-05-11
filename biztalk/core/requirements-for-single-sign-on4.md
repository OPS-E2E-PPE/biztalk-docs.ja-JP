---
title: TIBCO EMS アダプターの SSO の要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a07e4ecf344b06c9d1f98297acb3b3a851283e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399121"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="ec6ab-102">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="ec6ab-102">Requirements for Single Sign-On</span></span>

## <a name="overview"></a><span data-ttu-id="ec6ab-103">概要</span><span class="sxs-lookup"><span data-stu-id="ec6ab-103">Overview</span></span>
<span data-ttu-id="ec6ab-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) ではシングル サインオン (SSO) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="ec6ab-105">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO EMS などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-105">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="ec6ab-106">シングル サインオンを使用するために必要なものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-106">To use Single Sign-On, you must have:</span></span>  
  
- <span data-ttu-id="ec6ab-107">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ec6ab-107">Microsoft BizTalk Server</span></span>
  
- <span data-ttu-id="ec6ab-108">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ec6ab-108">Visual Studio</span></span>  
  
- <span data-ttu-id="ec6ab-109">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ec6ab-109">Enterprise Single Sign-On</span></span>  
  
- <span data-ttu-id="ec6ab-110">SSO をサポートするサーバー システム</span><span class="sxs-lookup"><span data-stu-id="ec6ab-110">A server system that supports SSO</span></span>  
  
  <span data-ttu-id="ec6ab-111">分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-111">The isolated host should be configured as authentication trusted.</span></span>
  
## <a name="enable-sso"></a><span data-ttu-id="ec6ab-112">SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-112">Enable SSO</span></span>  
  
1.  <span data-ttu-id="ec6ab-113">**トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-113">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="ec6ab-114">トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-114">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="ec6ab-115">関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications5.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-115">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec6ab-116">作業が完了したら、SSO を使用してへの任意の Web 共有フォルダーに戻してください**を共有しない**します。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-116">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="ec6ab-117">フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="ec6ab-117">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6ab-118">参照</span><span class="sxs-lookup"><span data-stu-id="ec6ab-118">See Also</span></span>  
[<span data-ttu-id="ec6ab-119">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ec6ab-119">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)