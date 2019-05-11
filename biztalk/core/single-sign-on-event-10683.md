---
title: シングル サインオン:イベント 10683 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c280011ab792c87d3062ec99954734845eea63f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397445"
---
# <a name="single-sign-on-event-10683"></a>シングル サインオン:イベント 10683
## <a name="details"></a>詳細  

|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
|  製品名   |                        エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]        |
|    イベント ID     |                                  10683                                   |
|  イベント ソース   |                                  ENTSSO                                  |
|    コンポーネント    |                                   該当なし                                    |
|  シンボル名  |                   SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD                   |
|  メッセージ テキスト   | すぎたため、再生ファイルが削除された old.%r<br />再生ファイル: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、再生ファイルが古すぎるため、削除されたことを示します。 再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。 ここで、パスワードの変更は一時的な暗号化ファイルに格納され、再び使用可能になったときに、SSO データベースに再生されます。 ですが古すぎるファイルが検出された場合、SSO データベースにファイルを再生するときに、破棄されます。 すべての古いパスワードの変更は、SSO パスワード同期システムによって破棄されます。`password sync age`パスワードの最大有効期間の変更要求およびコマンド ライン ツールを使用して制御できるパラメーターを決定します**ssoconfig-syncage**または SSO 管理 MMC。  

## <a name="user-action"></a>ユーザーの操作  

- ユーザー操作は必要ありません。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  

- [パスワード同期](../core/password-synchronization2.md)
