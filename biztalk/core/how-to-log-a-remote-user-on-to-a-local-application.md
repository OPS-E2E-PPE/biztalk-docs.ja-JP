---
title: リモート ユーザー アプリケーションをローカルにログオンする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fa3e3251961cb4d58d07026948a09fee94c2942
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336812"
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a>リモート ユーザー アプリケーションをローカルにログオンする方法
エンタープライズ シングル サインオン サービス (ENTSSO) の他の主な機能がサポートしているホスト側開始処理 (HIP)。 ENTSSO は HIP と連携リモート ユーザーはローカルの Windows リソースにアクセスしようとしています。 ENTSSO を使用してから受信できる要求ホストのユーザーと要求のアクセスをローカルの Windows アプリケーション。  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a>リモート ユーザーをローカルの Windows アプリケーションにログオン  
  
1.  リモート ユーザーから要求を受け取ります。  
  
     適切に、リモート ユーザーから要求を取得する方法を決定することをお勧めします。  
  
2.  リモート ユーザーが、指定された関連アプリケーションへのアクセス権を付与することを要求を使用して`ISSOLookup2.LogonExternalUser`します。  
  
     `LogonExternalUser` 外部ユーザーをアプリケーションの名前のパスにアクセスする外部のユーザーと関連するフラグのいずれかの外部ユーザーは、関連付けられている資格情報の名前に希望しています。 成功した場合、 `LogonExternalUser` Windows アクセス トークンへのハンドルを返します。  
  
     リモート ユーザーが既にありますでシングル サインオン データベースで識別される、データベース内の資格情報があるし、関連アプリケーションに関連付けます。 それ以外の場合、`LogonExternalUser`エラーが返されます。 ユーザー名とパスワード同期を使用して資格情報を保持することができます。  
  
     さらに、プロトコル遷移を有効にする必要があります。  
  
3.  返される Windows ハンドルを使用して`LogonExternalUser`トークンを表すユーザーを偽装します。  
  
## <a name="see-also"></a>参照  
 [ローカル ユーザー非 Windows アプリケーションにログオンする方法](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md)   
 **ISSOLookup2.LogonExternalUser メソッド** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]