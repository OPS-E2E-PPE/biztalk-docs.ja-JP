---
title: "シングル サインオン資格情報をマップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e847bde9-7a4c-4b81-8ad6-6a7cf23d19a1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2717a990cf6ac2bac92067354afd42931c9a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-single-sign-on-credentials"></a>シングル サインオン資格情報をマップする方法
エンタープライズ シングル サインオン データベース内に関連アプリケーションがあれば、ユーザーの資格情報をそのアプリケーションにマップできます。 現在のユーザーの資格情報を関連アプリケーションにマップする場合、`ISSOMapper` インターフェイスおよび `ISSOMapping` インターフェイスを組み合わせて使用する必要があります。  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a>関連アプリケーションとユーザーの資格情報をマップするには  
  
1.  `ISSOMapper` および `ISSOMapping` の新しいインスタンスを作成します。  
  
2.  `ISSOMapping` プロパティを適切な値に設定します。  
  
     `ISSOMapping` に指定できるプロパティは、ユーザーの Microsoft Windows ドメイン名、Windows ユーザー名、関連アプリケーションの名前、または外部ユーザー名です。  
  
3.  ISSOMapping.Create を呼び出して、マッピングを作成します。  
  
     `ISSOMapping.Create` を呼び出すと、エンタープライズ シングル サインオン サーバーにマップするローカル コピーに反映されます。  
  
4.  `ISSOMapper.SetExternalCredentials` を呼び出して、マッピングの資格情報を設定します。  
  
5.  `ISSOMapping.Enable` を呼び出して、マッピングを有効にします。  
  
 次の例は、指定されたエンタープライズ シングル サインオン アプリケーションとユーザーのマッピングを追加する方法を示しています。  
  
```  
public static bool AddMapping(string application, string user, string XU, string XP)  
{  
   try  
   {  
      // Set mapping.  
      ISSOMapper mapper=new ISSOMapper();  
      ISSOMapping mapping=new ISSOMapping();  
     string username=user.Substring(user.IndexOf('\\')+1);  
      string userdomain=user.Substring(0, user.IndexOf('\\'));  
      mapping.WindowsDomainName=userdomain;  
      mapping.WindowsUserName=username;  
      mapping.ApplicationName=application;  
      mapping.ExternalUserName=XU;  
      mapping.Create(0);  
      // Set credentials.  
      string[] credentials=new string[]{XP};  
      mapper.SetExternalCredentials(application, XU, ref credentials);  
      mapping.Enable(0);  
   }  
   catch  
   {  
      return false;  
   }  
   return true;  
      }  
```  
  
## <a name="see-also"></a>参照  
 [エンタープライズ シングル サインオンを使用したプログラミング](../core/programming-with-enterprise-single-sign-on.md)