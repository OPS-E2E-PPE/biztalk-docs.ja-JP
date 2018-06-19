---
title: リモート ユーザー、ローカルのアプリケーションにログオンする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6f638007c3c4eb1f85a5b5a701dd2b456c2d220d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254218"
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a>リモート ユーザー、ローカルのアプリケーションにログオンする方法
エンタープライズ シングル サインオン (ENTSSO) サービスの他の主要な機能は、ホスト側開始処理 (HIP) のサポートです。 リモート ユーザーがローカルの Windows リソースへのアクセスを試行するときに、ENTSSO は HIP と連携します。 ENTSSO を使用して、ホスト ユーザーからの要求を受け取り、ローカル Windows アプリケーションへのアクセスを要求することができます。  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a>リモート ユーザーによるローカル Windows アプリケーションにログオン  
  
1.  リモート ユーザーからの要求を受け取ります。  
  
     リモート ユーザーから要求を受け取る方法は、適切に決定してください。  
  
2.  `ISSOLookup2.LogonExternalUser` を使用して、特定の関連アプリケーションに対するリモート ユーザーのアクセス許可を要求します。  
  
     `LogonExternalUser` は、外部ユーザーがアクセスするアプリケーションの名前、外部ユーザー名、外部ユーザーに関連する資格情報、および関連フラグを渡します。 成功すると、`LogonExternalUser` は、Windows のアクセス トークンにハンドルを返します。  
  
     リモート ユーザーをシングル サインオン データベースで識別し、そのユーザーの資格情報をデータベースに格納し、関連アプリケーションに関連付けておく必要があります。 これを行わないと、`LogonExternalUser` はエラーを返します。 パスワード同期を使用して、ユーザー名および資格情報を常に最新にすることができます。  
  
     さらに、プロトコル遷移を有効にする必要があります。  
  
3.  `LogonExternalUser` から返される Windows ハンドルを使用して、トークンが表すユーザーの権限を借用します。  
  
## <a name="see-also"></a>参照  
 [ローカル ユーザー、Windows 以外のアプリケーションにログオンする方法](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md)   
 **ISSOLookup2.LogonExternalUser メソッド**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]