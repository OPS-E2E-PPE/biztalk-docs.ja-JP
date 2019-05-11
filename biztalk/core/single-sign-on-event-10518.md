---
title: シングル サインオン:イベント 10518 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 274e29f9-1933-4e40-83c0-2e84c6708315
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e675204d73731502080f8ae168e5ca8458d50a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279748"
---
# <a name="single-sign-on-event-10518"></a>シングル サインオン:イベント 10518
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                                                                エンタープライズ シングル サインオン                                                                                                                                                                                                                                 |
| 製品バージョン |                                                                                                                                                                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                                                                |
|    イベント ID     |                                                                                                                                                                                                                                          10518                                                                                                                                                                                                                                           |
|  イベント ソース   |                                                                                                                                                                                                                                          ENTSSO                                                                                                                                                                                                                                          |
|    コンポーネント    |                                                                                                                                                                                                                                           該当なし                                                                                                                                                                                                                                            |
|  シンボル名  |                                                                                                                                                                                                                                 SSO_WARN_BAD_USER_GROUP                                                                                                                                                                                                                                  |
|  メッセージ テキスト   | このアプリケーションのアプリケーション ユーザー アカウントが無効です。 このアカウントは、サーバーに存在するローカル アカウント チェックの場合。 場合はドメイン アカウントには、ドメイン管理者に問い合わせてください。 アカウントが有効な場合は、アプリケーションを有効にします。 この computer.%r でこのアプリケーションの使用を続けない場合は、このメッセージを無視できます。<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション ユーザー: % 2 %r<br /><br /> 無効なアカウント: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション ユーザー グループ アカウントが有効な Windows アカウントではないことを示します。 関連アプリケーションごとに 1 つのアプリケーション ユーザー アカウント グループがあります。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- 指定したアプリケーション ユーザー アカウントが存在することを確認します。  

- 指定された関連アプリケーションが適切なアプリケーションのユーザー アカウントを使用するのによう構成を確認するのにには、SSO 管理ユーティリティを使用します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO ユーザー グループ](../core/sso-user-groups.md)  

- [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)  

- [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)
