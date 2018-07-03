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
ms.openlocfilehash: 3b23e2bb61f4549e642bcd9a59f56bc232b40038
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019937"
---
# <a name="how-to-configure-single-sign-on"></a>シングル サインオンを構成する方法
エンタープライズ シングル サインオンにアクセスする前に、エンタープライズ シングル サインオンが現在のユーザーに正しく設定されていることを確認する必要があります。 ほとんどの構成には、2 つのインターフェイスのいずれかを使用します。 `ISSOAdmin` 新しい関連アプリケーションを作成することができる一般的な管理インターフェイスです。 一方、ISSOAdmin.GetGlobalInfo と ISSOAdmin.UpdateGlobalInfo を使用すると、さまざまなフラグや管理値を設定できます。 次の手順で説明するように、たとえば SSO チケットが有効であることを保証するタスクに使用できます。  
  
### <a name="to-enable-ticketing"></a>チケットを有効にするには  
  
1. 新しいインスタンスを作成`ISSOAdmin`です。  
  
2. `ISSOAdmin.GetGlobalInfo` を使用して現在の設定を取得します。  
  
    必要に応じて、この時点で現在の値にフラグが設定されていることを確認できます。  
  
3. `ISSOAdmin.UpdateGlobalInfo` を使用して、関連フラグを変更します。  
  
    この場合、チケットを検証して有効にするため、すべてのフラグが設定されています。  
  
   次の例は、シングル サインオンを使用してチケットを有効にする方法を示しています。  
  
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
  
## <a name="see-also"></a>参照  
 [Enterprise Single Sign-On によるプログラミング](../core/programming-with-enterprise-single-sign-on.md)