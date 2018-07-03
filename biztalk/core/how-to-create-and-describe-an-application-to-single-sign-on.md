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
ms.openlocfilehash: 874f3c0235d4a0a84d98905796de6db8b544b1bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990259"
---
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a>作成して、シングル サインオンにアプリケーションを記述する方法
一般的な管理タスクとして、関連アプリケーションをエンタープライズ シングル サインオン (SSO) データベースに追加することが挙げられます。 関連アプリケーションをエンタープライズ SSO データベースに追加することによって、ユーザーおよび資格情報を関連アプリケーションに関連付けることができます。  
  
> [!NOTE]
>  関連アプリケーションを作成するには、"SSO 関連管理者" 以上の権限を持つアカウントが必要です。  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a>SSO データベースに対してアプリケーションを作成および記述するには  
  
1. `ISSOAdmin` オブジェクトを新規作成します。  
  
2. `ISSOAdmin.CreateApplication` を呼び出し、新しいアプリケーションを作成します。  
  
3. `ISSOAdmin.CreateFieldInfo` を呼び出し、アプリケーションについて記述するフィールドを追加します。  
  
    この手順で、アプリケーションのユーザーとパスワードがデータベースに伝達されます。  
  
4. `ISSOAdmin.UpdateApplication` または `ISSOAdmin2.UpdateApplication2` を呼び出し、新たに作成された情報をサーバーにプッシュします。  
  
    この 2 つのメソッドの違いは、アプリケーションの更新を記述する際の手段にあります。`UpdateApplication2` では `IPropertyBag` が使用されるのに対し、`UpdateApplication` では複数のパラメーターが使用されます。  
  
5. `ISSOAdmin.PurgeCacheForApplication` を呼び出して、変更内容のローカル キャッシュを削除します。  
  
    ローカル キャッシュはセキュリティ上、決して安全な場所ではありません。手順 3. で記述した名前とパスワードを、ローカル キャッシュから確実に削除する必要があります。  
  
   次の例は、アプリケーションを作成して、フィールド情報を追加する方法を示しています。  
  
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