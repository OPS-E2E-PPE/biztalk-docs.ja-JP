---
title: シングル サインオン資格情報をマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e847bde9-7a4c-4b81-8ad6-6a7cf23d19a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95a56da0d30ec0f30c556dcab01b3789f3e1fb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336268"
---
# <a name="how-to-map-single-sign-on-credentials"></a>シングル サインオン資格情報をマップする方法
エンタープライズ シングル サインオン データベースに関連があるアプリケーションの場合は、そのアプリケーションにユーザーの資格情報をマップできます。 関連アプリケーションへの現在のユーザーの資格情報のマッピングの組み合わせを使用することが必要です、`ISSOMapper`と`ISSOMapping`インターフェイス。  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a>関連アプリケーションとユーザーの資格情報の間にマップするには  
  
1. 新しいインスタンスを作成`ISSOMapper`と`ISSOMapping`します。  
  
2. 設定、`ISSOMapping`プロパティを関連する値。  
  
    関連するプロパティを`ISSOMapping`はユーザーの Microsoft Windows ドメイン名、Windows ユーザー名、関連のアプリケーションの名前、および外部ユーザー名。  
  
3. ISSOMapping.Create を呼び出して、マッピングを作成します。  
  
    呼び出す`ISSOMapping.Create`をエンタープライズ シングル サインオン サーバーへのマッピングのローカル コピーを伝達します。  
  
4. 呼び出して、マッピングの資格情報を設定`ISSOMapper.SetExternalCredentials`します。  
  
5. 呼び出して、マッピングを有効にする`ISSOMapping.Enable`します。  
  
   次の例では、指定されたエンタープライズ シングル サインオン アプリケーションとユーザー間のマッピングを追加する方法を示します。  
  
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
 [Enterprise Single Sign-On によるプログラミング](../core/programming-with-enterprise-single-sign-on.md)