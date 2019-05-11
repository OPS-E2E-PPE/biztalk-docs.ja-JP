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
ms.openlocfilehash: 781fde1a4b7af82c851fb80a9df32a6eb93d8ce7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338586"
---
# <a name="how-to-determine-current-single-sign-on-access"></a>現在のシングル サインオン アクセスを確認する方法
ユーザーに対して実行する必要があります最初のタスクの 1 つは、どのような関連アプリケーションが既に設定されて現在のユーザーを決定します。 ISSOMapper.GetApplications への呼び出しでは、このクエリを実行することができます。  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a>現在のユーザーに使用可能なアプリケーションのシングル サインオン データベースに照会するには  
  
1. 新しいインスタンスを作成`ISSOMapper`です。  
  
    一般に、`ISSOMapper`はからシングル サインオン (SSO) の情報を取得するためのインターフェイスです。 使用するほとんどの場合`ISSOMapper`で同様な照会します。  
  
2. GetApplications を呼び出して、現在のユーザーに関連しているすべてのアプリケーションを取得します。  
  
    GetApplications は、自動的に現在のユーザーの関連アプリケーションのみを返します。  
  
   次のコード例では、シングル サインオン データベースに照会する方法を示します。  
  
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