---
title: 現在のシングル サインオン アクセスを確認する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cab68dfc-27cd-4f7c-a0df-20c670306358
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c57cfae2c2b7545854fa7891f099a19ff7bb0098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014771"
---
# <a name="how-to-determine-current-single-sign-on-access"></a>現在のシングル サインオン アクセスを確認する方法
ユーザーのために実行する必要のある最初の作業の 1 つは、どの関連アプリケーションが現在のユーザーに対して設定済みであるかを判断することです。 この判断を行うには、ISSOMapper.GetApplications を呼び出します。  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a>現在のユーザーが利用可能なアプリケーションについてシングル サインオン データベースを照会するには  
  
1. 新しいインスタンスを作成`ISSOMapper`です。  
  
    `ISSOMapper` はシングル サインオン (SSO) から情報を取得するために設計されたインターフェイスです。 同様な照会を行う場合は、`ISSOMapper` を使用するのが一般的です。  
  
2. GetApplications を呼び出して、現在のユーザーに関連するアプリケーションをすべて取得します。  
  
    GetApplications は、自動的に、現在のユーザーに関連するアプリケーションのみを返します。  
  
   次のコード例は、シングル サインオン データベースを照会する方法を示しています。  
  
```  
private static string[] Applications=null;  
. . .  
public static string[] GetCurrentUserApplications()  
{  
   if(Applications==null)  
   {  
      string[] descs;  
      string[] contacts;  
      ISSOMapper mapper=new ISSOMapper();  
      mapper.GetApplications(out Applications, out descs, out contacts);  
   }  
   return Applications;  
}  
```  
  
## <a name="see-also"></a>参照  
 [Enterprise Single Sign-On によるプログラミング](../core/programming-with-enterprise-single-sign-on.md)