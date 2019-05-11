---
title: シングル サインオンを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 511edc1d-de82-4d17-88ea-6cacfccde10d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5175b0bec313246cb9de8d85869029053469327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341245"
---
# <a name="how-to-configure-single-sign-on"></a><span data-ttu-id="bc2e7-102">シングル サインオンを構成する方法</span><span class="sxs-lookup"><span data-stu-id="bc2e7-102">How to Configure Single Sign-On</span></span>
<span data-ttu-id="bc2e7-103">エンタープライズ シングル サインオン アクセスをする前に、エンタープライズ シングル サインオンが正しく設定されている現在のユーザーの確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-103">Before accessing Enterprise Single Sign-On, you should make sure that Enterprise Single Sign-On is set correctly for the current user.</span></span> <span data-ttu-id="bc2e7-104">ほとんどの構成には、2 つのインターフェイスのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-104">For most configurations, you use one of two interfaces.</span></span> <span data-ttu-id="bc2e7-105">`ISSOAdmin` 新しい関連アプリケーションを作成することができる一般的な管理インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-105">`ISSOAdmin` is the general administration interface that enables you to create new affiliation applications.</span></span> <span data-ttu-id="bc2e7-106">ただし、ISSOAdmin.GetGlobalInfo と ISSOAdmin.UpdateGlobalInfo を使用すると、さまざまなフラグや管理値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-106">However, by using ISSOAdmin.GetGlobalInfo and ISSOAdmin.UpdateGlobalInfo, you can set a variety of flags and administration values.</span></span> <span data-ttu-id="bc2e7-107">1 つの可能なタスクの次の手順に従って SSO チケットが有効であることを確認するのには。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-107">One possible task, as described in the following procedure, is to ensure that SSO ticketing has been enabled.</span></span>  
  
### <a name="to-enable-ticketing"></a><span data-ttu-id="bc2e7-108">チケットを有効にするには</span><span class="sxs-lookup"><span data-stu-id="bc2e7-108">To enable ticketing</span></span>  
  
1. <span data-ttu-id="bc2e7-109">新しいインスタンスを作成`ISSOAdmin`です。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-109">Create a new instance of `ISSOAdmin`.</span></span>  
  
2. <span data-ttu-id="bc2e7-110">現在の設定を取得`ISSOAdmin.GetGlobalInfo`します。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-110">Retrieve the current settings through `ISSOAdmin.GetGlobalInfo`.</span></span>  
  
    <span data-ttu-id="bc2e7-111">必要に応じて、フラグがこの時点で設定、適切な値にすることを確認したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-111">If necessary, you may want to confirm that the flags are set to the correct values at this point.</span></span>  
  
3. <span data-ttu-id="bc2e7-112">使用して、関連フラグを変更する`ISSOAdmin.UpdateGlobalInfo`します。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-112">Change any relevant flags using `ISSOAdmin.UpdateGlobalInfo`.</span></span>  
  
    <span data-ttu-id="bc2e7-113">このケースで検証し、チケットを有効にする、すべてのフラグは設定されています。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-113">In this particular case, all the flags are being set to validate and enable tickets.</span></span>  
  
   <span data-ttu-id="bc2e7-114">次の例では、シングル サインオンを使用してチケットを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bc2e7-114">The following example shows how to enable ticketing using Single Sign-On.</span></span>  
  
```  
public static bool EnableTickets()  
{  
   try  
   {  
      ISSOAdmin admin=new ISSOAdmin();  
      int flags=0;  
      int appDeleteMax=1000;  
      int mappingDeleteMax=1000;  
      int ntpLookupMax=-1000;  
      int xplLookupMax=-1000;  
      int ticketTimeout=2;  
      int cacheTimeout=60;  
      string secretServer=null;  
      string ssoAdminGroup=null;  
      string affiliateAppMgrGroup=null;  
      // Get current default settings.  
      admin.GetGlobalInfo(out flags, out appDeleteMax, out mappingDeleteMax, out ntpLookupMax, out xplLookupMax, out ticketTimeout, out cacheTimeout, out secretServer, out ssoAdminGroup, out affiliateAppMgrGroup);  
      // Update global settings.  
      admin.UpdateGlobalInfo(SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, ref appDeleteMax, ref mappingDeleteMax, ref ntpLookupMax, ref xplLookupMax, ref ticketTimeout, ref cacheTimeout, null, null, null);   
   }  
   catch  
   {  
      return false;  
   }  
return true;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc2e7-115">参照</span><span class="sxs-lookup"><span data-stu-id="bc2e7-115">See Also</span></span>  
 [<span data-ttu-id="bc2e7-116">Enterprise Single Sign-On によるプログラミング</span><span class="sxs-lookup"><span data-stu-id="bc2e7-116">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)