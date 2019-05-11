---
title: シングル サインオン:イベント 10517 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9febc85f554b8736d75c9315a37214c8a81ca16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279807"
---
# <a name="single-sign-on-event-10517"></a>シングル サインオン:イベント 10517
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                  エンタープライズ シングル サインオン                                                                                                                                                  |
| 製品バージョン |                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                  |
|    イベント ID     |                                                                                                                                                            10517                                                                                                                                                            |
|  イベント ソース   |                                                                                                                                                           ENTSSO                                                                                                                                                            |
|    コンポーネント    |                                                                                                                                                             該当なし                                                                                                                                                             |
|  シンボル名  |                                                                                                                                                   SSO_ERROR_BAD_SSO_ADMIN                                                                                                                                                   |
|  メッセージ テキスト   | SSO 管理者アカウントが無効です。 このアカウントは、サーバーに存在するローカル アカウント チェックの場合。 場合はドメイン アカウントには、ドメイン管理者に問い合わせてください。 アカウントが valid.%r 場合は、SSO を有効にします。<br /><br /> SSO 管理者: % 1 %r<br /><br /> 無効なアカウント: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、エンタープライズ シングル サインオン用に指定された SSO 管理者アカウントが有効な Windows アカウントではないことを示します。 エンタープライズ シングル サインオン サービスを実行するサービス アカウントは、このアカウントのメンバーである必要があります。 SSO 管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。 SSO 管理者アカウントは、ドメインまたはローカル グループ アカウントにもできます。 個々 のアカウントを使用する場合は、別の単独アカウントをこのアカウントを変更することはできません。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- SSO 管理者アカウントが存在することを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO ユーザー グループ](../core/sso-user-groups.md)
