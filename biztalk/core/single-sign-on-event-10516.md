---
title: シングル サインオン:イベント 10516 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85f7d5069ede9653187c7c3af8bf79bc7bc11ca4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243455"
---
# <a name="single-sign-on-event-10516"></a>シングル サインオン:イベント 10516
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                 |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                            エンタープライズ シングル サインオン                                                                                                                                                            |
| 製品バージョン |                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                            |
|    イベント ID     |                                                                                                                                                                      10516                                                                                                                                                                      |
|  イベント ソース   |                                                                                                                                                                     ENTSSO                                                                                                                                                                      |
|    コンポーネント    |                                                                                                                                                                       該当なし                                                                                                                                                                       |
|  シンボル名  |                                                                                                                                                           SSO_ERROR_BAD_SSO_APP_ADMIN                                                                                                                                                           |
|  メッセージ テキスト   | SSO 関連管理者アカウントが無効です。 このアカウントは、サーバーに存在するローカル アカウント チェックの場合。 場合はドメイン アカウントには、ドメイン管理者に問い合わせてください。 アカウントが valid.%r 場合は、SSO を有効にします。<br /><br /> SSO 関連管理者: % 1 %r<br /><br /> 無効なアカウント: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、こと、SSO 関連管理者アカウントまたはエンタープライズ シングル サインオンによって作成されたグループが有効な Windows アカウントを示します。 SSO 関連管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。 SSO 関連管理者アカウントは、ドメインまたはローカル グループ アカウントにもできます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- SSO 関連管理者アカウントが存在することを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO ユーザー グループ](../core/sso-user-groups.md)  

- [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)
