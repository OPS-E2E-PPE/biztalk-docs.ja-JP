---
title: シングル サインオンを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 3203be74b21fa742e8e1ec2972e40f0212c4d1bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247770"
---
# <a name="how-to-configure-single-sign-on"></a><span data-ttu-id="520d9-102">シングル サインオンを構成する方法</span><span class="sxs-lookup"><span data-stu-id="520d9-102">How to Configure Single Sign-On</span></span>
<span data-ttu-id="520d9-103">エンタープライズ シングル サインオンにアクセスする前に、エンタープライズ シングル サインオンが現在のユーザーに正しく設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="520d9-103">Before accessing Enterprise Single Sign-On, you should make sure that Enterprise Single Sign-On is set correctly for the current user.</span></span> <span data-ttu-id="520d9-104">ほとんどの構成には、2 つのインターフェイスのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="520d9-104">For most configurations, you use one of two interfaces.</span></span> <span data-ttu-id="520d9-105">`ISSOAdmin`一般的な管理インターフェイス新しい関連アプリケーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="520d9-105">`ISSOAdmin` is the general administration interface that enables you to create new affiliation applications.</span></span> <span data-ttu-id="520d9-106">一方、ISSOAdmin.GetGlobalInfo と ISSOAdmin.UpdateGlobalInfo を使用すると、さまざまなフラグや管理値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="520d9-106">However, by using ISSOAdmin.GetGlobalInfo and ISSOAdmin.UpdateGlobalInfo, you can set a variety of flags and administration values.</span></span> <span data-ttu-id="520d9-107">次の手順で説明するように、たとえば SSO チケットが有効であることを保証するタスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="520d9-107">One possible task, as described in the following procedure, is to ensure that SSO ticketing has been enabled.</span></span>  
  
### <a name="to-enable-ticketing"></a><span data-ttu-id="520d9-108">チケットを有効にするには</span><span class="sxs-lookup"><span data-stu-id="520d9-108">To enable ticketing</span></span>  
  
1.  <span data-ttu-id="520d9-109">新しいインスタンスを作成する`ISSOAdmin`です。</span><span class="sxs-lookup"><span data-stu-id="520d9-109">Create a new instance of `ISSOAdmin`.</span></span>  
  
2.  <span data-ttu-id="520d9-110">`ISSOAdmin.GetGlobalInfo` を使用して現在の設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="520d9-110">Retrieve the current settings through `ISSOAdmin.GetGlobalInfo`.</span></span>  
  
     <span data-ttu-id="520d9-111">必要に応じて、この時点で現在の値にフラグが設定されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="520d9-111">If necessary, you may want to confirm that the flags are set to the correct values at this point.</span></span>  
  
3.  <span data-ttu-id="520d9-112">`ISSOAdmin.UpdateGlobalInfo` を使用して、関連フラグを変更します。</span><span class="sxs-lookup"><span data-stu-id="520d9-112">Change any relevant flags using `ISSOAdmin.UpdateGlobalInfo`.</span></span>  
  
     <span data-ttu-id="520d9-113">この場合、チケットを検証して有効にするため、すべてのフラグが設定されています。</span><span class="sxs-lookup"><span data-stu-id="520d9-113">In this particular case, all the flags are being set to validate and enable tickets.</span></span>  
  
 <span data-ttu-id="520d9-114">次の例は、シングル サインオンを使用してチケットを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="520d9-114">The following example shows how to enable ticketing using Single Sign-On.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="520d9-115">参照</span><span class="sxs-lookup"><span data-stu-id="520d9-115">See Also</span></span>  
 [<span data-ttu-id="520d9-116">エンタープライズ シングル サインオンを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="520d9-116">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)