---
title: 作成して、シングル サインオンにアプリケーションを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d717885-b132-4ba0-a93b-03377ac5eb97
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b914cc54e48aaa4a58d3f370f50132265f97def
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385517"
---
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a>作成して、シングル サインオンにアプリケーションを記述する方法
一般的な管理タスクを実行する必要がありますが、エンタープライズ シングル サインオン (SSO) データベースに関連アプリケーションを追加しています。 関連アプリケーション、エンタープライズ SSO データベースを追加するには、ユーザーと資格情報関連のアプリケーションに関連付けることができます。  
  
> [!NOTE]
>  関連アプリケーションを作成するには、「SSO 関連管理者」アカウントまたはの上のメンバーシップが必要です。  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a>作成し、SSO データベース内のアプリケーションを記述するには  
  
1. 新規作成`ISSOAdmin`オブジェクト。  
  
2. 呼び出して、新しいアプリケーションを作成`ISSOAdmin.CreateApplication`です。  
  
3. 呼び出しを使用してアプリケーションを記述するフィールドを追加`ISSOAdmin.CreateFieldInfo`します。  
  
    この手順では、中にすることを伝えるデータベース アプリケーション ユーザーと関連付けられているパスワード。  
  
4. 呼び出しを使用して、サーバーを新しく作成された説明にプッシュ`ISSOAdmin.UpdateApplication`または`ISSOAdmin2.UpdateApplication2`します。  
  
    2 つのメソッド間の差は`UpdateApplication2`を使用して、`IPropertyBag`中にアプリケーションを記述する方法は、更新、`UpdateApplication`は複数のパラメーターがあります。  
  
5. 呼び出すことによって行われた変更のローカル キャッシュを消去`ISSOAdmin.PurgeCacheForApplication`します。  
  
    名とパスワードを安全な場所に存在する 3 の手順で説明することによってのセキュリティ対策は、ローカル キャッシュを消去します。  
  
   次の例では、アプリケーションを作成し、フィールドの情報を追加する方法を示します。  
  
```  
public static bool AddApplication(string name, string admins, string users)  
    {  
       try  
       {  
          ISSOAdmin admin=new ISSOAdmin();  
          // Create application.  
          admin.CreateApplication(name, "SSO Sample Application", "administrator@ssoaffiliateapplication.com", users, admins, SSOFlag.SSO_WINDOWS_TO_EXTERNAL | SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, 2);  
          // Add fields.  
          admin.CreateFieldInfo(name, "User Id", SSOFlag.SSO_FLAG_NONE);  
          admin.CreateFieldInfo(name, "Password", SSOFlag.SSO_FLAG_FIELD_INFO_MASK);  
          // Enable application.  
          admin.UpdateApplication(name, null, null, null, null, SSOFlag.SSO_FLAG_ENABLED, SSOFlag.SSO_FLAG_ENABLED);  
          // Purge changes.  
          admin.PurgeCacheForApplication(name);  
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