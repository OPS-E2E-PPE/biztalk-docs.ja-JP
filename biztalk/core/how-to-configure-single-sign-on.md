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
# <a name="how-to-configure-single-sign-on"></a>シングル サインオンを構成する方法
エンタープライズ シングル サインオン アクセスをする前に、エンタープライズ シングル サインオンが正しく設定されている現在のユーザーの確認する必要があります。 ほとんどの構成には、2 つのインターフェイスのいずれかを使用します。 `ISSOAdmin` 新しい関連アプリケーションを作成することができる一般的な管理インターフェイスです。 ただし、ISSOAdmin.GetGlobalInfo と ISSOAdmin.UpdateGlobalInfo を使用すると、さまざまなフラグや管理値を設定できます。 1 つの可能なタスクの次の手順に従って SSO チケットが有効であることを確認するのには。  
  
### <a name="to-enable-ticketing"></a>チケットを有効にするには  
  
1. 新しいインスタンスを作成`ISSOAdmin`です。  
  
2. 現在の設定を取得`ISSOAdmin.GetGlobalInfo`します。  
  
    必要に応じて、フラグがこの時点で設定、適切な値にすることを確認したい場合があります。  
  
3. 使用して、関連フラグを変更する`ISSOAdmin.UpdateGlobalInfo`します。  
  
    このケースで検証し、チケットを有効にする、すべてのフラグは設定されています。  
  
   次の例では、シングル サインオンを使用してチケットを有効にする方法を示します。  
  
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