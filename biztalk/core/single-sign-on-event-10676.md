---
title: シングル サインオン:イベント 10676 |Microsoft Docs
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
ms.openlocfilehash: d1779d8f30d4e82d9c63dacc503cbd9dfab555a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397476"
---
# <a name="single-sign-on-event-10676"></a>シングル サインオン:イベント 10676
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                             エンタープライズ シングル サインオン                                                                                             |
| 製品バージョン |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    イベント ID     |                                                                                                       10676                                                                                                       |
|  イベント ソース   |                                                                                                      ENTSSO                                                                                                       |
|    コンポーネント    |                                                                                                        該当なし                                                                                                        |
|  シンボル名  |                                                                                          SSO_ERROR_REQUIRE_OLD_PASSWORD                                                                                           |
|  メッセージ テキスト   | 外部パスワード変更。 外部アカウントのパスワードを変更するときに、アダプターが古い password.%r を指定する必要があります。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、古いパスワードが指定されていませんが、パスワード同期アダプターは、外部のシステムからの古いパスワードが構成されたを示します。 外部システム (外部パスワード同期アダプター) が構成されていないか、正常に動作またはパスワード同期アダプターが正しく構成されていません。 このエラーは、エラー コード シンボリック名 ENTSSO_E_REQUIRE_OLD_PASSWORD を返すも可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

-   SSO 管理ツールを使用して、ユーザー構成可能なプロパティを設定する**古いパスワードの確認**パスワード同期アダプターのオプションのプロパティ タブ。このプロパティは、フラグの名前を持つツール (ssops.exe) のコマンドラインを使用してアダプターを作成するときにも設定できます`verifyOldPassword`と新しいパスワードを作成する同期も、パスワード同期アダプター ウィザードを使用してアダプターとします。  

## <a name="more-info"></a>詳細情報

- [パスワード同期](../core/password-synchronization2.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
