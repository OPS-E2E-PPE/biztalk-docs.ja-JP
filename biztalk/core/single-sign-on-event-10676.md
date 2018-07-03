---
title: 'シングル サインオン: イベント 10676 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec0e86fb-921d-4505-b458-51b565123ea7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63228e82546e100c81bf01c301d7d9507f147671
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991931"
---
# <a name="single-sign-on-event-10676"></a>シングル サインオン: イベント 10676
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                             エンタープライズ シングル サインオン                                                                                             |
| 製品バージョン |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    イベント ID     |                                                                                                       10676                                                                                                       |
|  イベント ソース   |                                                                                                      ENTSSO                                                                                                       |
|    コンポーネント    |                                                                                                        N\A                                                                                                        |
|  シンボル名  |                                                                                          SSO_ERROR_REQUIRE_OLD_PASSWORD                                                                                           |
|  メッセージ テキスト   | 外部パスワードが変更されています。 外部アカウントのパスワードを変更するとき、アダプターで古いパスワードを指定する必要があります。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、パスワード同期アダプターは外部システムの古いパスワードを必要とするように構成されていましたが、古いパスワードが指定されなかったことを示します。 外部システム (外部パスワード同期アダプター) が意図したように構成されていない、または動作していないか、またはパスワード同期アダプターが正しく構成されていません。 このエラーからはエラー コード シンボリック名 ENTSSO_E_REQUIRE_OLD_PASSWORD も返される場合があります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

-   SSO 管理ツールを使用して、ユーザー構成可能なプロパティを設定する**古いパスワードの確認**パスワード同期アダプターのオプションのプロパティ タブ。このプロパティは、アダプターを作成するときにコマンド ライン ツール (ssops.exe) と `verifyOldPassword` という名前のフラグを使用して、およびパスワード同期アダプター ウィザードを使用して新しいパスワード同期アダプターを作成するときに、設定することもできます。  

## <a name="more-info"></a>詳細

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
