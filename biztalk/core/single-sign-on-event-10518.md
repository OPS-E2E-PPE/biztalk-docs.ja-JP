---
title: 'シングル サインオン: イベント 10518 |Microsoft Docs'
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
ms.openlocfilehash: 76b267950d734f6a0935ed22e27782e8a6bcd1f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011411"
---
# <a name="single-sign-on-event-10518"></a>シングル サインオン: イベント 10518
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                                                                エンタープライズ シングル サインオン                                                                                                                                                                                                                                 |
| 製品バージョン |                                                                                                                                                                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                                                                |
|    イベント ID     |                                                                                                                                                                                                                                          10518                                                                                                                                                                                                                                           |
|  イベント ソース   |                                                                                                                                                                                                                                          ENTSSO                                                                                                                                                                                                                                          |
|    コンポーネント    |                                                                                                                                                                                                                                           N\A                                                                                                                                                                                                                                            |
|  シンボル名  |                                                                                                                                                                                                                                 SSO_WARN_BAD_USER_GROUP                                                                                                                                                                                                                                  |
|  メッセージ テキスト   | このアプリケーションのアプリケーション ユーザー アカウントは有効ではありません。 これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。 ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。 アカウントが有効である場合は、アプリケーションを有効にします。 このコンピューターでこのアプリケーションを使用しない場合、このメッセージは無視して構いません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション ユーザー: % 2 %r<br /><br /> 無効なアカウント: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション ユーザー グループ アカウントが有効な Windows アカウントではないことを示します。 アプリケーション ユーザー アカウント グループは、関連アプリケーションごとに 1 つ存在します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   

- 指定したアプリケーション ユーザー アカウントが存在することを確認します。  

- SSO 管理ユーティリティを使用して、指定した関連アプリケーションが適切なアプリケーション ユーザー アカウントを使用するように構成されていることを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO ユーザー グループ](../core/sso-user-groups.md)  

- [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)  

- [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)
